# Postup analýzy souboru/trafficu

## 1. Přehled zachycených dat
- Velikost souboru: 5,97 MB
- Počet packetů: 9799
- Časové rozmezí: May 29, 2015 14:16:09 UTC - May 29, 2015 14:39:54 UTC (23min 45s)
- Průměrná přenosová rychlost: 4 kB/s

### 1.1 Přehled protokolů
- TCP: 89,3 %
- HTTP: 6,6%
- UDP: 10,5 %
- DNS: 8,8 %

## 2. Prvotní prohlídka dat
- Filtry použité ve Wiresharku
- IP/domény s největší přenosem, komunikací apod
- Zajímavé protokoly nebo neobvyklý provoz

### 2.1 Filtry použité ve Wiresharku
- `http` – zobrazení všech HTTP požadavků/odpovědí
- `dns` – kontrola všech DNS dotazů
- `smtp` – zobrazení e-mailové komunikace
- `ip.addr == 10.3.162.105` – veškerá komunikace oběti
- `frame contains ".zip"` – hledání konkrétního souboru

### 2.2 IP / domény s největším přenosem
| Zdrojová IP   | Cílová IP       | Packety | Data    | Poznámka |
|---------------|-----------------|---------|---------|----------|
| 10.3.162.105  | 74.125.226.85   |  1 125  | 1 MB    | Google |
| 10.3.162.105  | 10.3.162.2      |  864    | 101 KB  | local cisco |
| 10.3.162.105  | 74.125.226.95   |  523    | 370 KB  | www.google.ca |
| 10.3.162.105  | 205.234.186.115 |  520    | 464 kB  | wnnvpim.ddnsking.com |


## 3. Detailní analýza

### 3.1 DNS analýza
| Doména   | IP adresa    | Poznámka |
|------------------|------|-------|
|sciclubtermeeuganee.it|149.3.144.218|zip soubor
|moskalskiybodun.com|91.200.14.95|gate.php
| dkpconsulting.com|46.249.199.41|exe soubor|
|doc.giovanniborsi.it|181.224.142.143|exe soubor|
|dom660000.ru|37.140.192.238|exe soubor|
|domdobleska.ru|178.208.83.15|exe soubor|

### 3.2 Role IP adres

| Ip adresa   | Role  | Poznámka |
|------------------|------|-------|
|10.3.162.105  | Oběť     | owen-PC|
|149.3.144.218 | zdroj malwaru|pdf...zip|
|91.200.14.95|payload |gate.php|

### 3.3 Přenosy souborů

| Název souboru | Směr | Velikost | MD5 hash | Poznámka |
|---------------|------|---------|---------|----------|
|DMR8J1U....|wnnvpim.ddnsking.com -> oběť|393 kB|bad6eb0f62c6cb20f0ac31fb13e60363|infikovaný soubor|
|pdf_efax_message_3537462.zip|sciclubtermeeuganee.it -> oběť|132 kB|002b4e3fc895582b5efed565ca1ffd2f|octet-stream|
|bb.exe|doc.giovanniborsi.it|39 kB|ee6eb31188b1c544bc4a18643b1576be|
|bb.exe|doc.giovanniborsi.it|14 kB|a029381c928cd74975b8039c729f117e|
|bb.exe|doc.giovanniborsi.it|624 bytes|66e41f0c0734cb7f436dfce09ce38073|


## 5. Časová osa 
- May 29, 2015 14:23:44 UTC otevřena stránka mail.google.com
- May 29, 2015 14:24:16 UTC stažen soubor pdf_efax_message_3537462.zip z sciclubtermeeuganee.it
- May 29, 2015 14:30:02 - 14:30:43 stažení malwaru z bb.exe
- May 29, 2015 14:32:49 UTC spuštěn payload z wnnvpim.ddnsking.com

## 6. Závěr
- Otevřen gmail s emailem, který odkázal na malware, který uživatel stáhl. Ten pak stáhl z další části malwaru a na konec payload soubor, který spustil další část malwaru, který není součástí pcap. 










