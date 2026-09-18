<div align="center">

# 🔐 Footprinting, Reconnaissance & Network Scanning

**Networkwalks Cybersecurity Internship — Batch B082 | Week 2**

</div>

<p align="center">
  <img src="https://img.shields.io/badge/Skill-Cybersecurity-404040?style=flat-square&labelColor=C00000" />
  <img src="https://img.shields.io/badge/Kali%20Linux-v2026.2-E87500?style=flat-square&labelColor=000000&logo=kalilinux&logoColor=white" />
  <img src="https://img.shields.io/badge/Tools-Kali%20%7C%20Maltego%20%7C%20Zenmap%20%7C%20theHarvester%20%7C%20GHDB-238F89?style=flat-square&labelColor=000000" />
  <img src="https://img.shields.io/badge/Ethical%20Hacking-C00000?style=flat-square&labelColor=000000&logo=kalilinux&logoColor=white" />
  <img src="https://img.shields.io/badge/GitHub-404040?style=flat-square&labelColor=0070C0&logo=github&logoColor=white" />
  <img src="https://img.shields.io/badge/Network-10.0.0.0%2F24-238F89?style=flat-square&labelColor=000000" />
  <img src="https://img.shields.io/badge/Networkwalks-B082-404040?style=flat-square&labelColor=C00000" />
</p>

---

## 📌 Project Overview

This repository contains the complete Week 2 project work for the **Networkwalks Cybersecurity Internship (Batch B082)**. The focus of Week 2 is **footprinting, passive reconnaissance, and network scanning** — the first two phases of a penetration test.

Five project modules were completed, covering a range of industry-standard tools and techniques used by cybersecurity professionals to gather intelligence about a target before any active testing begins. All activities were performed strictly within the scope of a written Letter of Authorization issued by Networkwalks.

---

## 🎯 Project Objectives

- Perform passive footprinting using multiple built-in Kali Linux tools
- Use the Google Hacking Database (GHDB) for open-source intelligence gathering
- Use Maltego to visually map and harvest email addresses from a target domain
- Use theHarvester to collect emails and subdomains from public sources
- Use Zenmap (Nmap GUI) to discover and map live hosts on a local network

---

## 🛡️ Authorization

All active reconnaissance and scanning tasks in this project were performed under the **Networkwalks Letter of Authorization** (Ref: NW-LOA-B082-017), issued by Networkwalks Managing Director Sonia John and acknowledged by intern Emmanuel Bafi.

- **Authorization period:** 17 August 2026 — 24 August 2026
- **Authorized scope:**
  - `networkwalks.com` — passive footprinting and DNS reconnaissance
  - Tester's own local area network (LAN) — network scanning only
- **Authorized activities:** Passive footprinting, host discovery (Ping scan on own network)
- **Prohibited:** Exploitation, unauthorized access, denial-of-service, data modification

---

## 🏗️ Lab Architecture

The lab environment consists of a Windows 10 host running VirtualBox with a Kali Linux virtual machine. Both are connected to a private NAT Network (`10.0.0.0/24`), isolating all scanning activity from external networks.

| Component | Configuration |
|---|---|
| 🖥️ Host OS | Windows 10 |
| 🧠 Host RAM | 8 GB |
| ⚡ Processor | Intel Core i7 |
| 🧰 Hypervisor | VirtualBox 7.2 |
| 🐉 Security OS | Kali Linux 2026.2 |
| 🌐 Virtual Network | NAT Network (NatNetwork) |
| 📡 Network Address | 10.0.0.0/24 |
| 🐧 Kali IP Address | 10.0.0.2/24 |
| 🚪 Default Gateway | 10.0.0.1 |
| 🌍 DNS Server | 8.8.8.8 |

---

## 📁 Repository Structure

```
NETWORKWALKS-EMMANUEL-B082-WK2-FOOTPRINTING-RECON/
│
├── README.md                          ← This file (main overview)
│
├── PM1-Multiple-Kali-Tools/
│   ├── PM1-Report.md                  ← Full module report
│   └── screenshots/
│       ├── task1-whois.png
│       ├── task2-whatweb.png
│       ├── task3-nslookup.png
│       ├── task4-curl-headers.png
│       ├── task5-wafw00f.png
│       └── task6-dnsrecon.png
│
├── PM2-GHDB/
│   ├── PM2-Report.md                  ← Full module report
│   └── screenshots/
│       ├── task1-ghdb-cam-search.png
│       ├── task1-google-dork-search.png
│       ├── task1-live-camera-feed.png
│       ├── task1-camera-results-table.png
│       ├── task2-google-dork-search.png
│       ├── task2-open-directory-listing.png
│       └── task2-ebook-results-table.png
│
├── PM3-Maltego/
│   ├── PM3-Report.md                  ← Full module report
│   └── screenshots/
│       ├── task1-maltego-download-page.png
│       ├── task1-maltego-jre-install.png
│       ├── task1-maltego-setup-complete.png
│       ├── task1-maltego-activation-options.png
│       ├── task1-maltego-create-account.png
│       ├── task1-maltego-auth-complete.png
│       ├── task1-maltego-ready.png
│       ├── task2-domain-entity-drag.png
│       ├── task2-domain-name-set.png
│       ├── task2-run-transforms-menu.png
│       ├── task2-email-results-graph.png
│       └── task2-transform-output-log.png
│
├── PM4-theHarvester/
│   ├── PM4-Report.md                  ← Full module report
│   └── screenshots/
│       ├── task1-kali-menu-theharvester.png
│       ├── task1-theharvester-usage.png
│       ├── task1-theharvester-baidu-run.png
│       ├── task1-baidu-output-saved.png
│       ├── task2-theharvester-all-sources-run.png
│       └── task2-all-sources-output-saved.png
│
└── PM5-Zenmap/
    ├── PM5-Report.md                  ← Full module report
    ├── topology/
    │   └── network-topology.pdf       ← Saved Zenmap topology
    └── screenshots/
        ├── task1-nmap-download-page.png
        ├── task1-nmap-components-selection.png
        ├── task1-npcap-install.png
        ├── task1-zenmap-desktop-shortcut.png
        ├── task2-ipconfig-output.png
        ├── task3-zenmap-ping-scan-running.png
        ├── task3-zenmap-nmap-output.png
        ├── task4-live-hosts-panel.png
        ├── task6-nmap-output-mac-addresses.png
        ├── task6-ipconfig-all-mac.png
        ├── task7-zenmap-topology-view.png
        ├── task7-save-topology-pdf-dialog.png
        └── task7-topology-pdf-on-desktop.png
```

---

## 📋 Module Summary

### PM1 — Footprinting with Multiple Kali Tools

Used six built-in Kali Linux tools to build a complete passive intelligence profile of `networkwalks.com` without ever touching the target directly.

| Tool | Purpose | Key Finding |
|---|---|---|
| whois | Domain registration | Registrar: GoDaddy, Host: HostGator |
| whatweb | Technology fingerprinting | Apache + WordPress 7.0.4, IP: 192.232.216.135 |
| nslookup | DNS resolution | Resolved to 192.232.216.135 |
| curl -I | HTTP headers | WordPress REST API exposed at `/wp-json/` |
| wafw00f | WAF detection | ModSecurity (SpiderLabs) detected |
| dnsrecon | Full DNS enumeration | 8 records: NS, MX, A, TXT, SPF, SRV |

📁 [View PM1 Report](./PM1-Multiple-Kali-Tools/PM1-Report.md)

---

### PM2 — Footprinting with GHDB

Used the Google Hacking Database (GHDB) on `exploit-db.com` to find publicly exposed devices and open directories through carefully crafted Google dork queries.

| Task | Objective | Result |
|---|---|---|
| Task 1 | Find 10 live exposed security cameras | ✅ 10 cameras found and verified |
| Task 2 | Find 10 mathematics eBook PDF listings | ✅ 10 open directory listings found |

📁 [View PM2 Report](./PM2-GHDB/PM2-Report.md)

---

### PM3 — Footprinting with Maltego

Installed Maltego on Windows, created a free Maltego ID, and used graph-based OSINT transforms to harvest email addresses associated with `networkwalks.com`.

| Task | Objective | Result |
|---|---|---|
| Task 1 | Install Maltego on Windows | ✅ Installed and configured |
| Task 2 | Harvest emails for networkwalks.com | ✅ info@networkwalks.com discovered |

📁 [View PM3 Report](./PM3-Maltego/PM3-Report.md)

---

### PM4 — Footprinting with theHarvester

Used theHarvester (pre-installed on Kali Linux) to gather email addresses and subdomains for `microsoft.com` from public sources.

| Task | Command | Source | Limit |
|---|---|---|---|
| Task 1 | `theHarvester -d microsoft.com -l 1000 -b baidu` | Baidu | 1000 results |
| Task 2 | `theHarvester -d microsoft.com -l 50 -b all` | All sources | 50 results |

📁 [View PM4 Report](./PM4-theHarvester/PM4-Report.md)

---

### PM5 — Network Scanning with Zenmap

Installed Zenmap on Windows and performed a ping scan of the local virtual lab network to discover all live hosts, their IP addresses, MAC addresses, and the network topology.

| Task | Result |
|---|---|
| Subnet Scanned | 10.0.0.0/24 |
| Live Hosts Found | *(insert count)* |
| Topology Saved | ✅ PDF saved |

📁 [View PM5 Report](./PM5-Zenmap/PM5-Report.md)

---

## 🔍 Key Concepts Demonstrated

**Passive vs Active Reconnaissance**
PM1, PM2, PM3, and PM4 are entirely passive — no packets are sent to the target. PM5 involves active scanning but only on the tester's own network.

**Why Footprinting Comes First**
Every tool in this project reveals a different layer of the target: who owns it, how it is built, what software it runs, who works there, and how the network is structured. This intelligence directs every subsequent phase of a penetration test.

**Defense Insight**
The same tools attackers use are used by defenders. Running these tools on your own infrastructure reveals exactly what an attacker would see and where to reduce exposure.

---

## 🔐 Ethical & Legal Notice

⚠️ All activities in this project were performed exclusively on authorized targets — `networkwalks.com` (with written LOA) and the tester's own local network. These tools must never be used against systems you do not own or have explicit written permission to test. Unauthorized scanning and reconnaissance is illegal in most jurisdictions.

---

## 🔗 Resources

- **Networkwalks:** [https://networkwalks.com](https://networkwalks.com)
- **Kali Linux:** [https://kali.org](https://kali.org)
- **Exploit DB / GHDB:** [https://exploit-db.com/google-hacking-database](https://www.exploit-db.com/google-hacking-database)
- **Maltego:** [https://maltego.com](https://maltego.com)
- **theHarvester:** [https://github.com/laramies/theHarvester](https://github.com/laramies/theHarvester)
- **Nmap / Zenmap:** [https://nmap.org](https://nmap.org)

---

## 👤 Author

**Emmanuel Bafi**
Cybersecurity Intern — Batch B082
Networkwalks Cybersecurity Internship Program

LinkedIn: *(add your LinkedIn profile link)*
GitHub: *(add your GitHub profile link)*

**Program:** Cybersecurity at Networkwalks | **Week:** 02 | **Project:** Footprinting, Reconnaissance & Network Scanning
