# Mon HomeLab – Proxmox
Un **HomeLab** moderne, léger et flexible basé sur **Proxmox VE** comme hyperviseur principal et **OpenWrt** comme routeur/firewall virtuel.

## ✨ Objectifs du projet

- Avoir un routeur/firewall puissant et personnalisable → **OpenWrt**  
- Virtualiser un maximum de services sur du matériel abordable → **Proxmox VE**  
- Apprendre la virtualisation, le réseau, la sécurité et l'automatisation  
- Pouvoir tout sauvegarder / restaurer rapidement  
- Consommation électrique raisonnable (~80-150W selon charge)

## 🖥️ Matériel utilisé

***Promox VE***
| Composant          | Modèle / Specs                              | Remarques                              |
|--------------------|---------------------------------------------|----------------------------------------|
| Fabricant          | HP                                          |                                        |
| Model              | EliteDesk G4                                |                                        |
| Processeur         | Intel Core i5-7500 CPU @ 3.40 Ghz           |                                        |
| RAM                | 32 Go DDR4                                  |                                        |
| Stockage principal | 1× NVMe 465.8 Gb (VMs/CTs rapides)          |                                        |
| Stockage données   | 1× SSD 238.5 Go                             |                                        |
| Carte réseau       | Intel I225-V / I226-V ou dual 2.5 GbE       |                                        |


***Routeur***
| Composant          | Modèle / Specs                              | Remarques                              |
|--------------------|---------------------------------------------|----------------------------------------|
| Fabricant          | Linksys                                     |                                        |
| Model              | WRT320ACM (Nom de code Rango)               |                                        |
| Processeur         | Marvell Armada 385 88F6820 CPU @ 1.86 Ghz   | Dual Core                              |
| RAM                | 512 Mb                                      |                                        |
| FLASH MB           | 256 Mo NAND                                 |                                        |
| WLAN Hardware      | Marvell 88W8964                             | 2.4 Ghz (b/g/n) | 5.0 Ghz (a/n/ac)     |
| ETHERNET           | 5 ports (1 Gbit) dont 1 WAN                 |                                        |

## 📡 État actuel du réseau (février 2026)

Internet  
↓  
**Freebox** (modem/routeur FAI – mode bridge ou routeur)  
↓ (WAN)  
**Linksys WRT3200ACM** – OpenWrt (routeur/firewall principal)

Interfaces / réseaux physiques/logiques :

| Interface OpenWrt | Réseau            | Masque         | Utilisation principale                  | Équipements connectés                                      |
|-------------------|-------------------|----------------|-----------------------------------------|-------------------------------------------------------------|
| LAN1 (eth0.?)     | 10.35.37.0/24     | /24            | Réseau principal – serveurs & services  | CD (120), DHC (122), DNS1 (110), DNS2 (115), Web (50), CD secondaire (75), DHC/DNS backup (85), Logs (97) |
| LAN2              | 10.35.38.0/24     | /24            | Réseau secondaire (invités ? tests ?)   | (à détailler)                                               |
| WLAN              | 172.16.37.0/24    | /24            | WiFi principal                          | Téléphones, PC portables, tablettes, IoT légers             |

**Adresses IP statiques notables sur LAN1 (10.35.37.0/24)** :

- 10.35.37.50   → Serveur web (Nginx)
- 10.35.37.110  → DNS primaire (Windows Server 2025)
- 10.35.37.115  → DNS secondaire (Windows Serveur 2025)
- 10.35.37.120  → Contrôleur de domaine (Windows Serveur 2025)
- 10.35.37.122  → Serveur DHCP principal (Windows Serveur 2025)
- 10.35.37.75   → Contrôle de domaine secondaire -> Backup (Windows Serveur 2025)
- 10.35.37.85   → DHCP + DNS de backup
- 10.35.37.97   → Serveur de logs centralisé (Grafana + Loki)

## 🗺️ Architecture réseau globale


