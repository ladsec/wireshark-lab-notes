# Analysis Steps – 2015-07-11

## 1. Přehled dat
- Velikost souboru: 3,36 MB
- Počet paketů: 3965
- Časové rozmezí: 2015-07-10 17:29:10 – 2015-07-10 17:46:14 (17:04)
- Přehled protokolů: TCP 94.98%, HTTP 0.5%, TLS 5%, UDP 4.36%, DNS 2,8%

## 2. Prvotní prohlídka
- Otevření PCAP ve Wiresharku
- Statistiky → Protocol Hierarchy pro základní orientaci
- Zobrazení všech konverzací (Statistics → Conversations) pro odhalení nejčastějších IP

## 3. Použité filtry ve Wiresharku
- `dns` – kontrola všech DNS dotazů a odpovědí
- `http` – analýza všech HTTP požadavků a odpovědí
- `ip.addr == [IP]` – izolace komunikace
- `frame contains ".exe"` – hledání stahovaných spustitelných souborů
- `smb || smb2` – kontrola SMB komunikace (uživatelská jména, sdílené soubory)
- `kerberos` – kontrola Kerberos autentizace (možné uživatelské účty)
- `nbns` - zjištění názvů počítačů v záznamu

## 4. Postup analýzy
1. Identifikace IP oběti přes `Statistics → Endpoints`.
2. Izolace provozu oběti pomocí filtru `ip.addr == [IP oběti]`.
3. Analýza DNS dotazů pro zjištění komunikace s externími doménami (výběr podezřelých – viz Findings).
4. Kontrola HTTP komunikace – hledání požadavků na soubory, podezřelých stránek.
5. Kontrola SMB a Kerberos paketů – identifikace možných uživatelských účtů nebo názvů počítačů.
6. Vyhledání přenášených souborů a extrakce jejich hashů.
7. Ověření domén, IP a hashů pomocí VirusTotal, WHOIS a URLscan.io.
8. Sestavení časové osy incidentu (viz Findings).

