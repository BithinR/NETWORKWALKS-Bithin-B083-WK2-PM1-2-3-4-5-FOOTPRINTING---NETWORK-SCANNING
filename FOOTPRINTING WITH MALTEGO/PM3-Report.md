<div align="center">

# 🔐 Footprinting with Maltego

**W2-PM3 | Week 2 | Project Module 3**

</div>

<p align="center">
  <img src="https://img.shields.io/badge/Skill-Cybersecurity-404040?style=flat-square&labelColor=C00000" />
  <img src="https://img.shields.io/badge/Tool-Maltego-E87500?style=flat-square&labelColor=000000" />
  <img src="https://img.shields.io/badge/Target-networkwalks.com-238F89?style=flat-square&labelColor=000000" />
  <img src="https://img.shields.io/badge/Platform-Windows-0070C0?style=flat-square&labelColor=000000" />
  <img src="https://img.shields.io/badge/Networkwalks-B082-404040?style=flat-square&labelColor=C00000" />
</p>

---

## 📌 Project Overview

This module covers **email address harvesting and OSINT footprinting using Maltego**. Maltego is a powerful open-source intelligence (OSINT) and graphical link-analysis tool used by cybersecurity professionals and investigators worldwide. It aggregates data from dozens of public sources and visualizes relationships between entities — domains, email addresses, IP addresses, people, and organizations.

In this module, Maltego was installed on a Windows computer, configured with a free Maltego ID, and used to discover all email addresses associated with the target domain `networkwalks.com` (with written authorization).

---

## 🎯 Objectives

- **Task 1:** Download and install Maltego on a Windows computer
- **Task 2:** Use Maltego transforms to harvest all email addresses related to `networkwalks.com`

---

## 🛡️ Authorization

This reconnaissance was performed under the Networkwalks Cybersecurity Internship Letter of Authorization (Ref: NW-LOA-B082-017), valid 17–24 August 2026. The target `networkwalks.com` is explicitly authorized for passive footprinting.

---

## 🏗️ Lab Environment

| Component | Configuration |
|---|---|
| 🖥️ OS | Windows (Host PC) |
| 🧰 Tool | Maltego Graph (Desktop) — Version 4.11.3 |
| 🌐 Activation | Maltego ID (Free Community Edition) |
| 🎯 Target | networkwalks.com |
| ⚙️ Transforms Used | \[Utilities\] To Email Addresses (Search Engine) |

---

## 🪜 Task Execution

---

### Task 1 — Download & Install Maltego on Windows

**Step 1: Download Maltego**

Opened `https://maltego.com`, navigated to **Resources → Download Maltego**, selected **Windows (.exe + Java x64)** and downloaded the installer.

> 📸 **Screenshot:** `screenshots/task1-maltego-download-page.png`
>
> *(Insert screenshot of the Maltego download page showing the Windows installer option selected)*

**Step 2: Run the Setup**

Ran the installer as Administrator. Maltego prompted to install the Java Runtime Environment (Eclipse Temurin JRE 17) as a prerequisite, which was accepted and installed automatically before Maltego itself installed.

> 📸 **Screenshot:** `screenshots/task1-maltego-jre-install.png`
>
> *(Insert screenshot of the JRE installation dialog during the Maltego setup)*

> 📸 **Screenshot:** `screenshots/task1-maltego-setup-complete.png`
>
> *(Insert screenshot of the "Completing Maltego Setup" dialog with the Finish button)*

**Step 3: Launch & Activate Maltego**

Right-clicked the Maltego desktop shortcut and selected **Run as administrator**. On the Welcome screen, selected **Maltego ID** activation and **Online Activation (Default)**.

> 📸 **Screenshot:** `screenshots/task1-maltego-activation-options.png`
>
> *(Insert screenshot of the Maltego activation screen showing "Maltego ID" selected)*

**Step 4: Create a Free Maltego Account**

Clicked **Browser Login** which opened the Maltego login portal. Selected **"No Maltego Account? Create ID"** and filled in the registration form with name and email. Completed email verification.

> 📸 **Screenshot:** `screenshots/task1-maltego-create-account.png`
>
> *(Insert screenshot of the "Create Maltego ID" registration form in the browser)*

> 📸 **Screenshot:** `screenshots/task1-maltego-auth-complete.png`
>
> *(Insert screenshot showing "Authentication complete" in the browser)*

**Step 5: Complete Configuration**

Returned to Maltego. Accepted the EULA, kept default data sources (Utilities + Maltego Local Transform Server), accepted default browser and Privacy Mode: Normal settings. Maltego completed configuration and was ready.

> 📸 **Screenshot:** `screenshots/task1-maltego-ready.png`
>
> *(Insert screenshot of the fully loaded Maltego Graph desktop application, showing it is ready to use)*

---

### Task 2 — Harvest Email Addresses for networkwalks.com

**Step 6: Open a New Graph and Add a Domain Entity**

1. Opened a new blank graph in Maltego.
2. In the **Entity Palette** on the left, searched for **"Domain"**.
3. Dragged the **Domain** entity onto the main graph canvas.

> 📸 **Screenshot:** `screenshots/task2-domain-entity-drag.png`
>
> *(Insert screenshot showing the Domain entity being dragged from the Entity Palette onto the canvas)*

**Step 7: Set Target Domain**

Double-clicked the Domain entity on the canvas to open its properties. Changed the **Domain Name** field to `networkwalks.com` and clicked OK.

> 📸 **Screenshot:** `screenshots/task2-domain-name-set.png`
>
> *(Insert screenshot of the entity properties dialog showing "networkwalks.com" entered as the domain name)*

**Step 8: Run Email Transforms**

Right-clicked on the `networkwalks.com` domain entity. In the **Run Transforms** context menu, filtered for **"email"** to narrow the transform list. Selected and ran:

- `[Utilities] To Email address [From whois info]`
- `[Utilities] To Email Addresses [PGP]`
- `[Utilities] To Email Addresses [Search Engine]`

> 📸 **Screenshot:** `screenshots/task2-run-transforms-menu.png`
>
> *(Insert screenshot of the Run Transforms context menu with the email transforms visible and selected)*

**Step 9: Results**

After the transforms completed, Maltego returned the discovered email addresses linked to `networkwalks.com` and displayed them as connected entities on the graph.

**Email addresses discovered:**

| # | Email Address | Source Transform |
|---|---|---|
| 1 | info@networkwalks.com | \[Utilities\] To Email Addresses (Search Engine) |
| *(add more)* | *(add if discovered)* | *(add transform name)* |

> 📸 **Screenshot:** `screenshots/task2-email-results-graph.png`
>
> *(Insert screenshot of the Maltego graph showing networkwalks.com connected to the discovered email address entities)*

> 📸 **Screenshot:** `screenshots/task2-transform-output-log.png`
>
> *(Insert screenshot of the Transform Output log at the bottom of Maltego showing the completed transform and results)*

---

## 📊 Summary of Findings

| Entity | Value |
|---|---|
| Target Domain | networkwalks.com |
| Tool | Maltego Graph 4.11.3 (Community Edition) |
| Transforms Run | To Email (whois), To Email (PGP), To Email (Search Engine) |
| Email(s) Found | info@networkwalks.com *(+ any others discovered)* |

---

## 💡 What I Learned

**1. Visual Intelligence Mapping**
Maltego's graph-based interface makes it easy to see relationships between entities. A domain connected to email addresses, IP addresses, and DNS names tells a complete story visually.

**2. Transform Ecosystem**
Maltego's power comes from its transforms — automated queries that pull data from dozens of public sources. The Community Edition (free) provides enough transforms for educational use, while paid tiers unlock significantly more data.

**3. Why Email Addresses Matter**
Every email address harvested is a potential target for phishing, password spray attacks, or credential stuffing. Discovering `info@networkwalks.com` tells an attacker the email format the organization uses, which can be extended to enumerate employee addresses.

**4. OSINT Aggregation**
Maltego saves enormous time by automating what would otherwise require manually querying whois, PGP key servers, and search engines one by one.

**5. Maltego on Kali**
Maltego can also be installed and run directly on Kali Linux, making it available in the same environment as all other penetration testing tools.

---

## 🔐 Security & Ethical Use

All Maltego transforms in this module were run against `networkwalks.com` only, within the scope of the issued Letter of Authorization. No unauthorized systems were queried or accessed.

---

## 🔗 Tools & References

- **Maltego Download:** [https://maltego.com/downloads](https://www.maltego.com/downloads/)
- **Maltego Documentation:** [https://docs.maltego.com](https://docs.maltego.com)
- **Maltego Academy:** [https://maltego.com/maltego-academy](https://maltego.com/maltego-academy/)

---

## 👤 Author

**Emmanuel Bafi**
Cybersecurity Intern — Batch B082
Networkwalks Cybersecurity Program | Week 2 | Project Module 3
