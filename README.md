# Mon HomeLab – Proxmox
Un **HomeLab** moderne, léger et flexible basé sur **Proxmox VE** comme hyperviseur principal et **OpenWrt** comme routeur/firewall virtuel.

## ✨ Objectifs du projet

- Avoir un routeur/firewall puissant et personnalisable → **OpenWrt**  
- Virtualiser un maximum de services sur du matériel abordable → **Proxmox VE**  
- Apprendre la virtualisation, le réseau, la sécurité et l'automatisation  
- Pouvoir tout sauvegarder / restaurer rapidement  
- Consommation électrique raisonnable (~80-150W selon charge)

## 🖥️ Matériel utilisé

### Promox VE
| Composant          | Modèle / Specs                              | Remarques                              |
|--------------------|---------------------------------------------|----------------------------------------|
| Fabricant          | HP                                          |                                        |
| Model              | EliteDesk G4                                |                                        |
| Processeur         | Intel Core i5-7500 CPU @ 3.40 Ghz           |                                        |
| RAM                | 32 Go DDR4                                  |                                        |
| Stockage principal | 1× NVMe 465.8 Gb (VMs/CTs rapides)          |                                        |
| Stockage données   | 1× SSD 238.5 Go                             |                                        |
| Carte réseau       | Intel I225-V / I226-V ou dual 2.5 GbE       |                                        |

<img width="800" height="400" alt="image" src="https://github.com/user-attachments/assets/9de62a1a-f2ce-47e9-9013-6a2ae7d8915d" />

### Routeur
| Composant          | Modèle / Specs                              | Remarques                              |
|--------------------|---------------------------------------------|----------------------------------------|
| Fabricant          | Linksys                                     |                                        |
| Model              | WRT320ACM (Nom de code Rango)               |                                        |
| Processeur         | Marvell Armada 385 88F6820 CPU @ 1.86 Ghz   | Dual Core                              |
| RAM                | 512 Mb                                      |                                        |
| FLASH MB           | 256 Mo NAND                                 |                                        |
| WLAN Hardware      | Marvell 88W8964                             | 2.4 Ghz (b/g/n) | 5.0 Ghz (a/n/ac)     |
| ETHERNET           | 5 ports (1 Gbit) dont 1 WAN                 |                                        |

<img width="600" height="600" alt="image" src="https://github.com/user-attachments/assets/41eb2a18-7d32-4b23-9269-a939c92f8306" />

## 🗺️ Architecture réseau globale


