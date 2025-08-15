# Malware Traffic Analysis – 2015-05-29

Analýza síťového provozu z [malware-traffic-analysis.net](https://www.malware-traffic-analysis.net/2015/05/29/index.html).  
PCAP byl poskytnut bez popisu incidentu – cílem bylo provést kompletní analýzu a identifikovat povahu útoku.

## Použité nástroje
- [Wireshark](https://www.wireshark.org/)
- [VirusTotal](https://www.virustotal.com/)
- [WHOIS](https://whois.domaintools.com/)  
- [URLscan.io](https://urlscan.io/)

## Struktura repozitáře
- `analysis_steps.md` – detailní postup analýzy krok po kroku
- `analysis_finding.md` – zjištění, IOC a časová osa útoku
- `/images` – screenshoty z Wiresharku a podpůrná vizualizace

## Shrnutí útoku
*Během analýzy byl identifikován škodlivý HTTP provoz vedoucí ke stažení spustitelného souboru. Komunikace obsahovala domény a IP adresy spojené s exploit kitem a následným dropem malwaru XYZ.*
