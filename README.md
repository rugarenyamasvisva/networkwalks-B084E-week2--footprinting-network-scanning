# Week 2: Footprinting & Network Scanning

**Networkwalks Cybersecurity Internship | Batch B084**
**Modules:** W2-PM1 (Multiple Kali Tools) and W2-PM5 (Zenmap Scanning)
**Intern:** Rugare Nyamasvisva

A penetration testing report covering the first two phases of an engagement: reconnaissance
and footprinting of networkwalks.com using Kali Linux tools, and network discovery of my own
local network using Zenmap.

## Report

- [Report (PDF)](Report/W2-PM-FINAL_Rugare_Nyamasvisva_Report.pdf)
- [Report (Word)](Report/W2-PM-FINAL_Rugare_Nyamasvisva_Report.docx)

## Tools used

| Tool | Purpose |
|------|---------|
| Kali Linux and Windows | Operating systems used for the activities |
| WHOIS | Domain registration details (registrar, dates, name servers) |
| Nslookup | Resolve the domain name to its IP address |
| Curl (-I) | Read the HTTP response headers |
| Wafw00f | Detect a Web Application Firewall |
| DNSRecon | Enumerate DNS records (first attempt failed, see report) |
| Zenmap (Nmap GUI) | Discover live hosts, IP and MAC addresses on the local subnet |

## Key results

- **WHOIS:** registered through GoDaddy.com, LLC on 6 November 2019 and registered until
  6 November 2027. Owner details are hidden by a privacy service, the name servers are HostGator,
  and DNSSEC is unsigned.
- **Nslookup:** networkwalks.com resolves to 192.232.216.135.
- **Curl:** HTTP/2 200 from an Apache server, with caching headers, the WordPress REST API
  endpoint `/wp-json/` and a `__wpdm_client` cookie. No Strict-Transport-Security,
  X-Frame-Options, X-Content-Type-Options or Content-Security-Policy headers were seen in the response.
- **Wafw00f:** the site is behind ModSecurity (SpiderLabs).
- **DNSRecon:** my first attempt failed because I left out `.com`, a reminder that tools need
  exact syntax.
- **Zenmap:** a ping scan of 192.168.100.0/24 found 4 live hosts in 4.23 seconds.

The report turns these observations into a risk table and recommendations. They are
observations, not confirmed vulnerabilities: no exploitation was performed.

## Screenshots

WHOIS domain details:

![WHOIS](screenshots/01-whois-domain.png)

Wafw00f result:

![Wafw00f](screenshots/05-wafw00f.png)

Zenmap ping scan:

![Zenmap ping scan](screenshots/07-zenmap-ping-scan.png)

Zenmap topology:

![Zenmap topology](screenshots/08-zenmap-topology.png)

All eight screenshots are in the [screenshots](screenshots) folder.

## Ethics and scope

I performed these activities only on systems where I had permission or on devices and networks
I own. This material is for education and research. Do not use anything from it to break the law.

## Repository structure

```
.
├── README.md
├── Report/
│   ├── W2-PM-FINAL_Rugare_Nyamasvisva_Report.pdf
│   └── W2-PM-FINAL_Rugare_Nyamasvisva_Report.docx
└── screenshots/
```

## Author

Rugare Nyamasvisva, Harare, Zimbabwe
Networkwalks Cybersecurity Internship, Batch B084
