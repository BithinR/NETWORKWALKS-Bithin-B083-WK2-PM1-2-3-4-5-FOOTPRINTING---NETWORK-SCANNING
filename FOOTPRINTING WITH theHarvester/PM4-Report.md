<div align="center">

# 🔐 Footprinting & Reconnaissance with theHarvester

**W2-PM4 | Week 2 | Project Module 4**

</div>

<p align="center">
  <img src="https://img.shields.io/badge/Skill-Cybersecurity-404040?style=flat-square&labelColor=C00000" />
  <img src="https://img.shields.io/badge/Kali%20Linux-v2026.2-E87500?style=flat-square&labelColor=000000&logo=kalilinux&logoColor=white" />
  <img src="https://img.shields.io/badge/Tool-theHarvester%20v4.10-238F89?style=flat-square&labelColor=000000" />
  <img src="https://img.shields.io/badge/Target-microsoft.com-0070C0?style=flat-square&labelColor=000000" />
  <img src="https://img.shields.io/badge/Networkwalks-B082-404040?style=flat-square&labelColor=C00000" />
</p>

---

## 📌 Project Overview

This module covers **passive email and subdomain reconnaissance using theHarvester**. theHarvester is a pre-installed Kali Linux tool designed to gather email addresses, subdomains, hostnames, employee names, open ports, and banners from dozens of public sources including search engines, PGP key servers, and the SHODAN database.

Because theHarvester only reads public data and never touches the target system directly, it is a form of **passive reconnaissance** — the target never knows it is being studied.

Two tasks were completed: one querying a single data source (Baidu) with a high result limit, and one querying all available sources with a limited result count.

---

## 🎯 Objectives

- **Task 1:** Use theHarvester to find email IDs and subdomains for `microsoft.com` via **Baidu**, with a limit of 1000 results
- **Task 2:** Use theHarvester to find email IDs and subdomains for `microsoft.com` via **all sources**, with a limit of 50 results

---

## 🏗️ Lab Environment

| Component | Configuration |
|---|---|
| 🐉 Security OS | Kali Linux 2026.2 |
| 🧰 Tool | theHarvester v4.10 (pre-installed on Kali) |
| 🎯 Target Domain | microsoft.com (public domain — education exercise) |
| ⚙️ Sources Used | baidu (Task 1), all (Task 2) |

---

## 🪜 Task Execution

---

### Task 1 — theHarvester with Baidu (Limit: 1000)

**Objective:** Search for email addresses and subdomains related to `microsoft.com` using the Baidu source, limiting results to 1000.

**Step 1: Open theHarvester**

Opened a terminal window in Kali Linux. theHarvester is pre-installed and available directly from the terminal or the Kali applications menu.

> 📸 **Screenshot:** `screenshots/task1-kali-menu-theharvester.png`
>
> *(Insert screenshot of theHarvester being launched from the Kali Linux applications menu or terminal)*

**Step 2: Read the Usage Instructions**

Before running the main command, reviewed theHarvester's usage options by running it without arguments to understand available flags.

```bash
theHarvester
```

Key flags confirmed:
- `-d` — target domain
- `-l` — limit the number of results (default: 500)
- `-b` — data source to use
- `-f` — save output to a file

Available sources include: `baidu, bevigil, bitbucket, brave, bufferoverun, builtwith, censys, certspotter, chaos, commoncrawl, criminalip, crtsh, dehashed, dnsdumpster, duckduckgo, fofa, fullhunt, github-code, git, haveibeenpwned, hudsonrock, hunter, hunterhow, intelx, leakix, leaklookup, netlas, onyphe, otx, pentesttools, projectdiscovery, rapiddns, robtex, rocketreach, securityscorecard, security, subdomaincenter, subdomainfinderc99, thc, threatcrowd, tomba, urlscan, venacus, virustotal, waybackarchive, whoisxml, windvane, yahoo, zoomeye`

> 📸 **Screenshot:** `screenshots/task1-theharvester-usage.png`
>
> *(Insert screenshot of the terminal showing theHarvester's usage output with all available flags and supported sources)*

**Step 3: Run theHarvester with Baidu**

```bash
$ theHarvester -d microsoft.com -l 1000 -b baidu
```

**Command breakdown:**
- `-d microsoft.com` — target domain
- `-l 1000` — limit results to 1000
- `-b baidu` — use Baidu as the data source

> 📸 **Screenshot:** `screenshots/task1-theharvester-baidu-run.png`
>
> *(Insert screenshot of the terminal showing theHarvester running with the Baidu source and the output results — emails found and hosts found sections)*

**Results from Baidu:**

| Category | Findings |
|---|---|
| Target | microsoft.com |
| Source | Baidu |
| IPs Found | *(insert count/values from your output)* |
| Emails Found | *(insert email addresses from your output, e.g., viva-noreply@microsoft.com)* |
| Hosts Found | *(insert subdomains found, or "No hosts found")* |

**Step 4: Save Output**

Saved the terminal screenshot and also saved the output to a text file:

```bash
$ theHarvester -d microsoft.com -l 1000 -b baidu -f task1-baidu-output
```

> 📸 **Screenshot:** `screenshots/task1-baidu-output-saved.png`
>
> *(Insert screenshot confirming the output was saved to a file, or showing the saved file in the directory)*

> **Note:** Results may differ slightly from the module guide because theHarvester's data sources update their algorithms and indexes regularly. The search methodology remains the same.

---

### Task 2 — theHarvester with All Sources (Limit: 50)

**Objective:** Search for email addresses and subdomains for `microsoft.com` using all available data sources simultaneously, limiting results to 50.

**Step 1: Open a New Terminal**

Opened a fresh terminal window in Kali Linux.

**Step 2: Run theHarvester with All Sources**

```bash
$ theHarvester -d microsoft.com -l 50 -b all
```

**Command breakdown:**
- `-d microsoft.com` — target domain
- `-l 50` — limit results to 50 per source
- `-b all` — query every available data source

> 📸 **Screenshot:** `screenshots/task2-theharvester-all-sources-run.png`
>
> *(Insert screenshot of the terminal showing theHarvester running with `-b all`, including the source-by-source output as it queries each one)*

**Observed behavior:** Several sources returned "Missing API key" errors for premium services (bevigil, bitbucket, bufferoverun, builtwith, brave, etc.). This is expected — free sources returned results while paid API-gated sources were skipped.

**Results from All Sources:**

| Category | Findings |
|---|---|
| Target | microsoft.com |
| Source | All available sources |
| Sources with errors | *(list sources that returned API key errors)* |
| IPs Found | *(insert count/values)* |
| Emails Found | *(insert email addresses discovered)* |
| Hosts/Subdomains Found | *(insert subdomains discovered)* |

**Step 3: Save Output**

Saved the terminal screenshot and output to a text file:

```bash
$ theHarvester -d microsoft.com -l 50 -b all -f task2-all-sources-output
```

> 📸 **Screenshot:** `screenshots/task2-all-sources-output-saved.png`
>
> *(Insert screenshot of the completed output or saved file confirmation)*

---

## 📊 Summary of Findings

| Task | Source | Limit | Emails Found | Subdomains Found |
|---|---|---|---|---|
| Task 1 | Baidu | 1000 | *(insert count)* | *(insert count)* |
| Task 2 | All sources | 50 | *(insert count)* | *(insert count)* |

---

## 💡 What I Learned

**1. Passive Recon at Scale**
theHarvester can query dozens of data sources in seconds. What would take hours of manual searching across individual sources is automated into a single command.

**2. Source Diversity**
Different sources return different results. Baidu may surface different subdomains than DuckDuckGo or CertSpotter. Using `-b all` maximizes coverage but also reveals which sources require paid API keys.

**3. Email as Attack Vector**
Every discovered email address is a potential phishing target and provides clues about an organization's email format (e.g., `firstname.lastname@domain.com`). This pattern can be used to enumerate additional employee addresses.

**4. Subdomain Value**
Each discovered subdomain is another potential entry point — an older subdomain may run outdated software or have weaker security controls than the main domain.

**5. Why Passive Recon is Powerful**
theHarvester never touches the target. It reads public sources only. The target has no log of this activity — which is exactly why passive recon is the first and most critical phase of any penetration test.

---

## 🔐 Security & Ethical Use

theHarvester was run against `microsoft.com` purely for educational purposes as instructed in the module. This is a well-known public domain. No data was stored, used maliciously, or shared outside this report. All activities comply with the Networkwalks program's liability disclaimer.

---

## 🔗 Tools & References

- **theHarvester (GitHub):** [https://github.com/laramies/theHarvester](https://github.com/laramies/theHarvester)
- **Install on non-Kali systems:**
  ```bash
  sudo apt-get install theHarvester
  # or
  git clone https://github.com/laramies/theHarvester.git
  cd theHarvester
  sudo python ./theHarvester.py
  ```

---

## 👤 Author

**Emmanuel Bafi**
Cybersecurity Intern — Batch B082
Networkwalks Cybersecurity Program | Week 2 | Project Module 4
