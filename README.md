# Reconnaissance-and-Packet-Analysis-Project
Project Objective

The purpose of this project is to demonstrate reconnaissance and packet analysis techniques on a safe target (TryHackMe - tryhackme.com).

The project involves:

Collecting publicly available information (OSINT)

Performing network scanning

Capturing and analyzing network packets with Wireshark

Documenting findings for cybersecurity analysis

Tools Used
Tool	Purpose
whois	Domain registration and ownership info
nslookup	Resolve domain names to IP addresses
dig	Detailed DNS queries
ping	Check server availability
traceroute	Identify network path
theHarvester	Collect emails, subdomains, hosts
nmap	Open port scanning
Wireshark	Packet capture and analysis
Browser Dev Tools	Identify web technologies
Target Information

Organization: TryHackMe

Domain: tryhackme.com

Target Type: Safe practice domain for cybersecurity learning

Step 1 — Domain Information (WHOIS)

Command used:

whois tryhackme.com

Findings:

Registrar: Cloudflare

Creation date: YYYY-MM-DD

Name servers: ns1.cloudflare.com, ns2.cloudflare.com

<img width="2719" height="1747" alt="Screenshot 2026-03-08 202427" src="https://github.com/user-attachments/assets/3c662dfa-4c97-4478-b419-2839c7bc2375" />

Step 2 — IP Address Resolution

Command used:

nslookup tryhackme.com

Findings:

IP Address: 104.xx.xx.xx

<img width="2735" height="1735" alt="Screenshot 2026-03-08 202447" src="https://github.com/user-attachments/assets/4beac6b6-df26-4c5c-9bcb-d99ad591f894" />

Step 3 — DNS Enumeration

Command used:

dig tryhackme.com
dig MX tryhackme.com

Findings:

A record → Server IP

MX record → Email server used by domain

NS record → Name servers

<img width="2735" height="1735" alt="Screenshot 2026-03-08 202447" src="https://github.com/user-attachments/assets/850da154-4615-4136-bfc1-061cbdf81cd0" />

Step 4 — Network Connectivity and Path

Commands used:

ping tryhackme.com
traceroute tryhackme.com

Findings:

Server is reachable

Latency and route hops identified
<img width="2735" height="1719" alt="Screenshot 2026-03-08 202513" src="https://github.com/user-attachments/assets/8cc276a9-7c9b-44a8-b09f-fdd3928be50b" />

Step 5 — Subdomain and Email Enumeration

Command used:

theHarvester -d tryhackme.com -b bing

Findings:

Subdomains discovered:

support.tryhackme.com

blog.tryhackme.com

vpn.tryhackme.com

Emails: (none public for privacy reasons)

Step 6 — Open Port Scanning (Nmap)

Command used:

nmap tryhackme.com

Findings:

Port	Service	State
80	HTTP	open
443	HTTPS	open
<img width="2720" height="1708" alt="Screenshot 2026-03-08 205031" src="https://github.com/user-attachments/assets/8ba54067-b356-4c5d-9fea-f36de6857e61" />

Step 7 — Packet Capture with Wireshark

Open Wireshark

Select interface: WiFi

Start capture

Visit tryhackme.com in browser

Stop capture after 30–60 seconds

Filters applied:

Filter	Purpose
dns	DNS requests/responses
tcp	TCP traffic and handshake
tls	Encrypted web traffic
icmp	Ping packets

Findings:

DNS query resolved tryhackme.com → 104.xx.xx.xx

TCP 3-way handshake observed (SYN → SYN/ACK → ACK)

TLS handshake observed (Client Hello → Server Hello → Encrypted session)

Server IP address identified: 104.xx.xx.xx

Full TCP session captured using Follow TCP Stream
<img width="2735" height="1720" alt="Screenshot 2026-03-08 182410" src="https://github.com/user-attachments/assets/676af96a-c194-47e0-a931-283f196740b7" />
<img width="2734" height="1732" alt="Screenshot 2026-03-08 193959" src="https://github.com/user-attachments/assets/894238e7-135d-48dd-9c97-5ebbbfc25488" />
<img width="2720" height="1723" alt="Screenshot 2026-03-08 194529" src="https://github.com/user-attachments/assets/4ec1d7a4-5d97-43a5-9d1c-11ea9c4f0c78" />
<img width="2731" height="1658" alt="Screenshot 2026-03-08 194752" src="https://github.com/user-attachments/assets/689af95d-3e3d-4599-8613-6c6881eb3421" />
<img width="2735" height="1718" alt="Screenshot 2026-03-08 194823" src="https://github.com/user-attachments/assets/733fd7e5-be0a-4d30-a982-d8c4614fff11" />
<img width="2735" height="1728" alt="Screenshot 2026-03-08 195247" src="https://github.com/user-attachments/assets/28a4035d-9e76-438c-ab67-592d33cee111" />
<img width="2735" height="1685" alt="Screenshot 2026-03-08 201307" src="https://github.com/user-attachments/assets/5a46104a-4f37-4b30-a35d-248f90a7d4c0" />

Capture file: tryhackme-capture.pcap

Step 8 — Website Technology Identification

Open browser → Developer Tools → View Page Source

Observed technologies:

Frontend: JavaScript, HTML5

CDN/Hosting: Cloudflare

Backend: Possibly Node.js / API server

Conclusion

The project demonstrates legal reconnaissance and packet analysis on a safe target.

Key skills learned:

OSINT (domain, DNS, IPs, subdomains)

Network scanning (open ports, services)

Packet analysis (TCP/TLS, DNS, ICMP)

These skills are essential for cybersecurity roles like penetration testing, SOC analysis, and threat intelligence.
