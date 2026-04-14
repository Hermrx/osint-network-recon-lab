# OSINT & Network Reconnaissance Lab

![Kali Linux](https://img.shields.io/badge/Kali_Linux-557C94?style=for-the-badge&logo=kali-linux&logoColor=white)
![Nmap](https://img.shields.io/badge/Nmap-214478?style=for-the-badge&logo=nmap&logoColor=white)
![Wireshark](https://img.shields.io/badge/Wireshark-1679A7?style=for-the-badge&logo=wireshark&logoColor=white)

> Practical cybersecurity lab covering OSINT, network reconnaissance, fingerprinting, network attacks, and social engineering — completed as part of the MCIS Master's in Cybersecurity at CEUPE European Business School.

---

## 📋 Overview

This lab demonstrates a full offensive reconnaissance and attack cycle against a controlled target, following a structured methodology aligned with real-world penetration testing practices. All exercises were performed in authorized, controlled environments for educational purposes only.

**Target Organization (Footprinting exercise):** Universidad Católica Tecnológica del Cibao (UCATECI) — publicly accessible information only.

---

## 🛠️ Tools Used

| Tool | Purpose |
|------|---------|
| Shodan | Passive reconnaissance, vulnerability identification |
| Hunter.io | Email harvesting |
| Nmap | Port scanning, OS detection, service enumeration |
| NetScanTools | LAN fingerprinting, SMB scanning |
| Ettercap | ARP Poisoning / MiTM attack |
| Arpspoof | ARP spoofing |
| Wireshark | Packet capture and traffic analysis |
| MitmProxy | HTTP/HTTPS traffic interception |
| SET (Social-Engineer Toolkit) | Social engineering attacks |
| DNSdumpster / CRT.sh | Subdomain enumeration |
| IntoDNS | DNS infrastructure analysis |

---

## 📁 Lab Structure

### Exercise 1 — Footprinting (OSINT)
Passive reconnaissance against a real public target:
- **IP & Infrastructure:** Identified host IP `149.56.108.184`, ISP (OVH Hosting), ASN (AS16276), and hosting location (Montréal, Canada) via Shodan
- **Domain Admin:** Identified domain administrator via WHOIS lookup
- **Email Harvesting:** Collected organizational email addresses using Hunter.io, identifying key IT and management contacts
- **Geolocation:** Located two physical campus sites using Google Maps
- **Exposed Vulnerabilities:** Identified active CVEs on the web server (Apache httpd 2.4.52) including CVE-2022-22720 (CVSS 9.8) via Shodan passive scan
- **Subdomains:** Enumerated subdomains via DNSdumpster and CRT.sh (portal, catalogo, virtual, vpn, proelem, prueba, etc.)
- **DNS Analysis:** Full DNS record mapping via IntoDNS including NS, MX, SOA, TXT, and SPF records

### Exercise 2 — Fingerprinting
Active and passive identification of systems on a local LAN:
- **Passive LAN Scan:** Identified all active devices, MAC addresses, manufacturers, and hostnames using NetScanTools ARP scan
- **SMB Enumeration:** Detected shared network resources and NetBIOS node type using SMB scanner
- **Nmap Port Scan:** Performed TCP SYN, service version, and full aggressive scans (`-sT`, `-sV`, `-A -v`) against two LAN targets
- **OS Detection:** Successfully identified Windows OS via service fingerprints (msrpc, netbios-ssn, microsoft-ds) and confirmed via Nmap service info
- **Router
