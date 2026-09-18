<img width="1460" height="605" alt="Nmap - Zenmap GUI" src="https://github.com/user-attachments/assets/7323afa6-e0f9-4e09-86c8-9db59a69b21b" /><div align="center">

# 🔐 Network Scanning with Zenmap

**W2-PM5 | Week 2 | Project Module 5**

</div>

<p align="center">
  <img src="https://img.shields.io/badge/Skill-Cybersecurity-404040?style=flat-square&labelColor=C00000" />
  <img src="https://img.shields.io/badge/Tool-Zenmap%20%2F%20Nmap-E87500?style=flat-square&labelColor=000000" />
  <img src="https://img.shields.io/badge/Platform-Windows-0070C0?style=flat-square&labelColor=000000" />
  <img src="https://img.shields.io/badge/Scan-Ping%20Scan%20(10.0.0.0%2F24)-238F89?style=flat-square&labelColor=000000" />
  <img src="https://img.shields.io/badge/Networkwalks-B082-404040?style=flat-square&labelColor=C00000" />
</p>

---

## 📌 Project Overview

This module covers **network scanning and host discovery using Zenmap**, the official graphical user interface (GUI) for Nmap. Zenmap is a free, open-source, multi-platform security scanner used by cybersecurity professionals and ethical hackers. It makes Nmap accessible to beginners while providing advanced features for experienced users, including topology visualization and the ability to save scan profiles for repeated use.

In this module, Zenmap was installed on a Windows PC and used to scan the local virtual lab network to discover all live hosts, their IP addresses, MAC addresses, and the network topology.

---

## 🎯 Objectives

- **Task 1:** Download and install Zenmap from the official website on Windows
- **Task 2:** Find the local IP address and LAN subnet
- **Task 3:** Find the list of live hosts/PCs in the IP subnet
- **Task 4:** Count how many hosts are live in the subnet
- **Task 5:** Identify the IP addresses of all live hosts
- **Task 6:** Identify the MAC addresses of all live hosts
- **Task 7:** Display and save the output network topology in PDF format

---

## 🛡️ Authorization

Network scanning was performed exclusively on the tester's own local virtual lab network (10.0.0.0/24), which is owned and controlled by the tester. This is explicitly authorized under Section 1 of the Networkwalks Letter of Authorization (Ref: NW-LOA-B082-017).

---

## 🏗️ Lab Environment

| Component | Configuration |
|---|---|
| 🖥️ Host OS | Windows 10 |
| 🧰 Tool | Zenmap (Nmap GUI) — installed via nmap-7.91-setup.exe |
| 🌐 Virtual Network | NAT Network (NatNetwork) |
| 📡 Subnet Scanned | 10.0.0.0/24 |
| 🐉 Kali Linux IP | 10.0.0.2 |
| 🔧 Scan Type | Ping Scan (`nmap -sn`) |

---

## 🪜 Task Execution

---

### Task 1 — Download & Install Zenmap on Windows

**Download:**

Opened `https://nmap.org/download.html` and downloaded the latest stable Windows self-installer: `nmap-7.91-setup.exe`.

**Install:**

Ran the installer, accepted the license agreement, left all components checked (including **Zenmap GUI Frontend** and **Npcap**), chose the default installation folder, and clicked **Install**.

**Completion:**

Installation completed successfully. Zenmap shortcut appeared on the desktop.

<img width="404" height="347" alt="Screenshot 2026-09-18 093820" src="https://github.com/user-attachments/assets/d181f55f-45ff-44e8-8f87-261655054ab4" />


---

### Task 2 — Find Local IP Address & LAN Subnet

Opened **Command Prompt** (`cmd`) and ran:

```cmd
ipconfig
```

This revealed the local IP address and subnet mask of the host PC.

**Findings:**

| Field | Value |
|---|---|
| IPv4 Address | *(insert your PC's IP, e.g., 10.0.0.2)* |
| Subnet Mask | 255.255.255.0 |
| Default Gateway | 10.0.0.1 |
| LAN Subnet | 10.0.0.0/24 |

<img width="1307" height="372" alt="Screenshot-ipconfig" src="https://github.com/user-attachments/assets/f03ba4c8-8820-46d3-b668-2cbf4119cebc" />


---

### Task 3 — Find All Live Hosts in the Subnet

Opened **Zenmap**, entered the following settings and clicked **Scan**:

| Field | Value |
|---|---|
| Target | `10.0.0.0/24` |
| Profile | Ping scan |
| Command (auto-filled) | `nmap -sn 10.0.0.0/24` |

Zenmap executed the ping scan across all 256 addresses in the subnet and reported which hosts responded.

<img width="1886" height="822" alt="Screenshot-Zenmap-1" src="https://github.com/user-attachments/assets/09d4781d-5707-4409-9d9a-c79be95f9934" />

---

### Task 4 — How Many Hosts Are Live?

After the scan completed, Zenmap listed all live hosts in the **Hosts** panel on the left.

**Answer:** 3



---

### Task 5 — IP Addresses of Live Hosts

| # | IP Address |
|---|---|
| 1 | *(10.0.0.1)* |
| 2 | *(10.0.0.10)* |
| 3 | *(10.0.0.2)* |

All IP addresses were identified directly from the Zenmap Hosts panel and the Nmap Output tab.

---

### Task 6 — MAC Addresses of Live Hosts

MAC addresses were found in the Nmap Output tab for each host. The local machine's MAC was confirmed using:

```cmd
ipconfig /all
```
<img width="671" height="199" alt="Screenshot-Zenmap-mac" src="https://github.com/user-attachments/assets/a8ac81b0-12df-4fc5-9ed8-69cb2261f6a2" />

---

### Task 7 — Save Topology as PDF

1. In Zenmap, clicked the **Topology** tab to display the network map.
2. Clicked **Legend** to enable the topology legend overlay.
3. Read the legend — it explains host types (router, switch, WAP, firewall), connection types, and ring gap meanings.
4. Clicked **Save Graphic**, set the filename to `pdf`, selected save location as **Desktop**, and chose **PDF** from the file type dropdown.
5. Clicked **OK** — the topology PDF was saved to the desktop.


<img width="1897" height="1015" alt="Screenshot-Zenmap-2" src="https://github.com/user-attachments/assets/b0c35ee9-ae33-49a2-ac45-8b8c269efb89" />


---

## 📊 Summary of Results

| Local IP / Subnet | *10.0.0.2* / 10.0.0.0/24 |
| How many hosts live? | *3* hosts |
| Topology saved? | ✅ Yes — PDF saved to desktop |

---

## 💡 What I Learned

**1. Nmap vs Zenmap**
Nmap is the underlying command-line engine; Zenmap is its GUI wrapper. Zenmap auto-generates the Nmap command from the profile selected, making it beginner-friendly without sacrificing power.

**2. Ping Scan (`-sn`)**
The ping scan sends ICMP echo requests (and optionally ARP requests on local networks) to every address in a subnet and reports which ones respond. It does not scan ports — it is purely host discovery.

**3. Subnet Scope**
A /24 subnet contains 256 addresses (254 usable hosts). Nmap scans the entire range in seconds on a local network, demonstrating how quickly an attacker could map an organization's internal network.

**4. MAC Address Intelligence**
MAC addresses identify the network interface vendor (VMware in this lab). On a real network, unexpected MACs can reveal unauthorized devices or virtual machines.

**5. Topology Visualization**
Zenmap's topology view gives a graphical picture of how hosts connect to each other. This is valuable for understanding network architecture at a glance.

**6. Nmap in Popular Culture**
Nmap and Zenmap have appeared in major Hollywood productions including The Matrix Reloaded (2001), Ocean's 8 (2018), and Snowden (2016), demonstrating its real-world recognition.

---

## 🔐 Security & Ethical Use

All scanning in this module was performed exclusively on the tester's own local virtual lab network. No external targets were scanned. Scanning networks without explicit permission is illegal in most jurisdictions.

---

## 🔗 Tools & References

- **Nmap / Zenmap Download:** [https://nmap.org/download.html](https://nmap.org/download.html)
- **Nmap Reference Guide:** [https://nmap.org/book/man.html](https://nmap.org/book/man.html)
- **Nmap in Movies:** [https://nmap.org/movies/](https://nmap.org/movies/)
- **Zenmap Practice Lab:** [https://networkwalks.com/zenmap-network-scanning-practice-lab/](https://networkwalks.com/zenmap-network-scanning-practice-lab/)

---

## 👤 Author

**Bithin Krishna Radhakrishnan**
Cybersecurity Intern — Batch B083
Networkwalks Cybersecurity Program | Week 2 | Project Module 5
