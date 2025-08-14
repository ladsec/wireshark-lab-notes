# Postup analýzy souboru/trafficu

## 1. Přehled zachycených dat
- Popis PCAP/log souboru (velikost, délka záznamu, počet paketů...)

## 2. Prvotní prohlídka dat
- Filtry použité ve Wiresharku
- IP/domény s největší přenosem, komunikací apod
- Zajímavé protokoly nebo neobvyklý provoz

## 3. Detailní analýza
- **DNS analýza:** seznam podezřelých domén
- **IP adresy:** určení rolí IP adres v záznamu
- **HTTP/HTTPS provoz:** požadavky, hlavičky
- **SMB/Kerberos:** uživatelská jména, názvy počítačů
- **E-mail provoz:** hlavičky, přílohy
- **Souborové přenosy:** názvy souborů, hashe
- **Command & Control komunikace:** identifikace C2 serverů

## 4. Korelace a OSINT
- WHOIS a geolokace IP
- Kontrola domén/IP na VirusTotal, AbuseIPDB, URLhaus
- Kontrola hashů souborů

## 5. Časová osa útoku
- Vytvoř časovou osu s časem a popisem událostí

## 6. Závěr
- Shrnutí zjištění
