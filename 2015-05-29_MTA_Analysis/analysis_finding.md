# Nalezené informace a podrobnosti z traficu

## Klíčové indikátory kompromitace (IOC)
### IP adresy
| IP adresa       | Role           | Poznámka          |
|-----------------|----------------|-------------------|
| 10.3.162.105    | Oběť           | owen-PC           |
| 149.3.144.218   | Zdroj malwaru  | pdf_efax_message_3537462.zip |
| 91.200.14.95    | Payload server | gate.php          |

### Domény
| Doména                      | Popis                   |
|-----------------------------|-------------------------|
| sciclubtermeeuganee.it      | Hostování ZIP souboru   |
| moskalskiybodun.com         | Command & Control (C2)  |
  
### Hash souborů
| Název souboru                               | MD5                                  |
|---------------------------------------------|--------------------------------------|
| pdf_efax_message_3537462.zip                | 002b4e3fc895582b5efed565ca1ffd2f     |
| DMR8J1U... (payload)                        | bad6eb0f62c6cb20f0ac31fb13e60363     |

## Shrnutí útoku
Uživatel pc 10.3.162.105 (owen-PC), navštívil 29.05 2015 14:23:44 gmail, kde otevřel email s infikovaným obsahem, který ho přesměroval na falešnou stránku. Z ní stáhl soubor pdf_efax_message_3537462.zip, ve kterém byl malware a ten pak spustil stahování dalších součástí všetně payload z wnnvpim.ddnsking.com, který mohl spustit další kod/malware, který již není součástí pcap.
