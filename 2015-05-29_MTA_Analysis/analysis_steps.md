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
