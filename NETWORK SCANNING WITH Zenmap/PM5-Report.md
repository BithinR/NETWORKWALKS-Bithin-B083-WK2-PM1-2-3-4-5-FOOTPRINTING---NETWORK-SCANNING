<div align="center">

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

> 📸 **Screenshot:** `screenshots/task1-nmap-download-page.png`
>
> *(Insert screenshot of the nmap.org download page with the Windows installer highlighted)*

**Install:**

Ran the installer, accepted the license agreement, left all components checked (including **Zenmap GUI Frontend** and **Npcap**), chose the default installation folder, and clicked **Install**.

> 📸 **Screenshot:** `screenshots/task1-nmap-components-selection.png`
>
> *(Insert screenshot of the Nmap setup component selection screen showing all options checked)*

> 📸 **Screenshot:** `screenshots/task1-npcap-install.png`
>
> *(Insert screenshot of the Npcap installation options dialog)*

**Completion:**

Installation completed successfully. Zenmap shortcut appeared on the desktop.

> 📸 **Screenshot:** `screenshots/task1-zenmap-desktop-shortcut.png`
>
> *(Insert screenshot of the Windows desktop showing the Zenmap and Nmap shortcut icons after installation)*

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

> 📸 **Screenshot:** `screenshots/task2-ipconfig-output.png`
>
> *(Insert screenshot of the Command Prompt showing the ipconfig output with your IP address and subnet mask highlighted)*

---

### Task 3 — Find All Live Hosts in the Subnet

Opened **Zenmap**, entered the following settings and clicked **Scan**:

| Field | Value |
|---|---|
| Target | `10.0.0.0/24` |
| Profile | Ping scan |
| Command (auto-filled) | `nmap -sn 10.0.0.0/24` |

Zenmap executed the ping scan across all 256 addresses in the subnet and reported which hosts responded.

> 📸 **Screenshot:** `screenshots/task3-zenmap-ping-scan-running.png`
>
> *(Insert screenshot of Zenmap with the target and Ping scan profile set, either mid-scan or showing results)*

> 📸 **Screenshot:** `screenshots/task3-zenmap-nmap-output.png`
>
> *(Insert screenshot of the Nmap Output tab showing the full scan results text, including the MAC addresses and "Nmap done" line)*

---

### Task 4 — How Many Hosts Are Live?

After the scan completed, Zenmap listed all live hosts in the **Hosts** panel on the left.

**Answer:** **_(insert your count)_ hosts** are live in the subnet (including the scanning machine itself).

*(In the lab example: 4 hosts were found live — 10.0.0.1, 10.0.0.4, 10.0.0.5, 10.0.0.19)*

> 📸 **Screenshot:** `screenshots/task4-live-hosts-panel.png`
>
> *(Insert screenshot of the Zenmap Hosts panel on the left showing all discovered live hosts listed)*

---

### Task 5 — IP Addresses of Live Hosts

| # | IP Address |
|---|---|
| 1 | *(insert IP — e.g., 10.0.0.1)* |
| 2 | *(insert IP — e.g., 10.0.0.2)* |
| 3 | *(insert IP — e.g., 10.0.0.4)* |
| 4 | *(insert IP — e.g., 10.0.0.5)* |

All IP addresses were identified directly from the Zenmap Hosts panel and the Nmap Output tab.

---

### Task 6 — MAC Addresses of Live Hosts

MAC addresses were found in the Nmap Output tab for each host. The local machine's MAC was confirmed using:

```cmd
ipconfig /all
```

| # | IP Address | MAC Address | Vendor |
|---|---|---|---|
| 1 | *(insert IP)* | *(insert MAC, e.g., 00:50:56:E3:B3:2C)* | *(e.g., VMware)* |
| 2 | *(insert IP)* | *(insert MAC, e.g., 00:0C:29:C0:94:8F)* | *(e.g., VMware)* |
| 3 | *(insert IP)* | *(insert MAC, e.g., 00:50:56:E9:64:82)* | *(e.g., VMware)* |
| 4 | *(insert IP — local PC)* | *(insert MAC from ipconfig /all)* | *(local NIC vendor)* |

> 📸 **Screenshot:** `screenshots/task6-nmap-output-mac-addresses.png`
>
> *(Insert screenshot of the Nmap Output tab clearly showing the MAC Address lines for each discovered host)*

> 📸 **Screenshot:** `screenshots/task6-ipconfig-all-mac.png`
>
> *(Insert screenshot of ipconfig /all in CMD showing the physical/MAC address of your local network adapter)*

---

### Task 7 — Save Topology as PDF

1. In Zenmap, clicked the **Topology** tab to display the network map.
2. Clicked **Legend** to enable the topology legend overlay.
3. Read the legend — it explains host types (router, switch, WAP, firewall), connection types, and ring gap meanings.
4. Clicked **Save Graphic**, set the filename to `pdf`, selected save location as **Desktop**, and chose **PDF** from the file type dropdown.
5. Clicked **OK** — the topology PDF was saved to the desktop.

> 📸 **Screenshot:** `screenshots/task7-zenmap-topology-view.png`
>
> *(Insert screenshot of the Zenmap Topology tab showing the network map with the legend panel open on the left)*

> 📸 **Screenshot:** `screenshots/task7-save-topology-pdf-dialog.png`
>
> *(Insert screenshot of the "Save Topology" dialog box with PDF selected from the file type dropdown)*

> 📸 **Screenshot:** `screenshots/task7-topology-pdf-on-desktop.png`
>
> *(Insert screenshot of your Windows desktop showing the saved topology PDF file icon)*

The saved topology PDF is included in this repository: `topology/network-topology.pdf`

---

## 📊 Summary of Results

| Task | Question | Answer |
|---|---|---|
| Task 2 | Local IP / Subnet | *(insert your IP)* / 10.0.0.0/24 |
| Task 4 | How many hosts live? | *(insert count)* hosts |
| Task 5 | IP addresses of live hosts | *(list all IPs)* |
| Task 6 | MAC addresses of live hosts | *(list all MACs)* |
| Task 7 | Topology saved? | ✅ Yes — PDF saved to desktop |

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

**Emmanuel Bafi**
Cybersecurity Intern — Batch B082
Networkwalks Cybersecurity Program | Week 2 | Project Module 5
