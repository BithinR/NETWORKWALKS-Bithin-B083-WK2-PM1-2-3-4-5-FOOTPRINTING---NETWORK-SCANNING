<img width="268" height="392" alt="image" src="https://github.com/user-attachments/assets/18ece9cd-e105-47b9-932e-5b42adbf201b" />

<div align="center">

# 🔐 Footprinting & Reconnaissance with Multiple Kali Tools

**W2-PM1 | Week 2 | Project Module 1**

</div>

<p align="center">
  <img src="https://img.shields.io/badge/Skill-Cybersecurity-404040?style=flat-square&labelColor=C00000" />
  <img src="https://img.shields.io/badge/Kali%20Linux-v2026.2-E87500?style=flat-square&labelColor=000000&logo=kalilinux&logoColor=white" />
  <img src="https://img.shields.io/badge/Tools-whois%20%7C%20whatweb%20%7C%20nslookup%20%7C%20curl%20%7C%20wafw00f%20%7C%20dnsrecon-238F89?style=flat-square&labelColor=000000" />
  <img src="https://img.shields.io/badge/Target-networkwalks.com-C00000?style=flat-square&labelColor=000000" />
  <img src="https://img.shields.io/badge/Networkwalks-B082-404040?style=flat-square&labelColor=C00000" />
</p>

---

## 📌 Project Overview

This module covers **passive footprinting and reconnaissance** against the target domain `networkwalks.com` (with written authorization). Six built-in Kali Linux tools were used to build a full intelligence profile of the target without ever touching it directly.

Reconnaissance is the first step in any real penetration test. Every piece of data gathered here — domain registration, web technologies, DNS records, firewall presence — forms the foundation for all later phases.

---

## 🎯 Objectives

- Run **whois** to retrieve domain registration details
- Run **whatweb** to fingerprint web technologies, CMS, and IP address
- Run **nslookup** to resolve the domain to its IP address
- Run **curl -I** to read HTTP response headers
- Run **wafw00f** to detect a Web Application Firewall (WAF)
- Run **dnsrecon** to enumerate all DNS records

---

## 🛡️ Authorization

This reconnaissance was performed under the Networkwalks Cybersecurity Internship Letter of Authorization (Ref: NW-LOA-B082-017), valid from 17 August 2026 to 24 August 2026. The target `networkwalks.com` is explicitly listed in scope for passive footprinting activities.

---

## 🏗️ Lab Environment

| Component | Configuration |
|---|---|
| 🖥️ Host OS | Windows 10 |
| 🐉 Security OS | Kali Linux 2026.2 |
| 🌐 Virtual Network | NAT Network (10.0.0.0/24) |
| 🎯 Target | networkwalks.com |
| ⚙️ Tools Used | whois, whatweb, nslookup, curl, wafw00f, dnsrecon |

---

## 🪜 Task Execution

---

### Task 1 — whois (Domain Registration Details)

**Objective:** Query the public domain registration record to identify the owner, registrar, registration/expiry dates, and name servers.

**Command executed:**

```bash
$ whois networkwalks.com
```

**Key findings:**

| Field | Value |
|---|---|
| Domain Name | NETWORKWALKS.COM |
| Registrar | GoDaddy.com, LLC |
| Registrar WHOIS Server | whois.godaddy.com |
| Creation Date | 2019-11-06 |
| Expiry Date | 2027-11-06 |
| Name Servers | NS6135.HOSTGATOR.COM / NS6136.HOSTGATOR.COM |
| DNSSEC | unsigned |

**Why attackers use this:** whois reveals the hosting provider (HostGator), registration timeline, and abuse contacts — all useful for social engineering and attack planning.

<img width="1571" height="1010" alt="Screenshot-whois" src="https://github.com/user-attachments/assets/0bd1b729-e756-458b-95db-6cb15b4f7f77" />


---

### Task 2 — whatweb (Web Technology Fingerprinting)

**Objective:** Fingerprint the web server, CMS, plugins, frameworks, and IP address running on the target.

**Command executed:**

```bash
$ whatweb networkwalks.com
```

**Key findings:**

| Field | Value |
|---|---|
| IP Address | 192.232.216.135 |
| Web Server | Apache |
| CMS | WordPress 7.0.4 |
| Plugin Detected | WP Download Manager 3.3.58 |
| jQuery Version | 3.7.1 |
| Country | United States |
| Email Leaked | info@networkwalks.com |

**Why attackers use this:** Exact software versions allow attackers to search CVE databases for known exploits. The leaked server IP and email also expand the attack surface.

<img width="1915" height="232" alt="Screenshot-whatweb" src="https://github.com/user-attachments/assets/f099c54b-b042-480a-80d2-8655274d57fc" />

---

### Task 3 — nslookup (DNS Resolution)

**Objective:** Resolve the domain name to its real IP address using DNS.

**Command executed:**

```bash
$ nslookup networkwalks.com
```

**Key findings:**

| Field | Value |
|---|---|
| DNS Server Used | 8.8.8.8 |
| Resolved IP Address | 192.232.216.135 |

**Why attackers use this:** Knowing the real IP lets an attacker scan the server directly and enumerate other sites hosted on the same IP to map the infrastructure.

<img width="976" height="150" alt="Screenshot-NSLookup" src="https://github.com/user-attachments/assets/faadbcd0-4945-4318-a65e-a7ed8fd13694" />


---

### Task 4 — curl -I (HTTP Response Headers)

**Objective:** Read the HTTP response headers to reveal the server banner, status code, cookies, and hidden endpoints.

**Command executed:**

```bash
$ curl -I https://networkwalks.com
```

**Key findings:**

| Header | Value |
|---|---|
| HTTP Status | 200 OK |
| Server | Apache |
| x-nginx-cache | WordPress |
| set-cookie | `__wpdm_client` (WordPress Download Manager session) |
| WordPress REST API | Exposed at `/wp-json/` |
| Date | Fri, 14 Aug 2026 21:33:17 GMT |

**Why attackers use this:** HTTP headers leak the web server, caching stack, and hidden endpoints such as the WordPress REST API (`/wp-json/`). These reveal entry points without loading the full page.

<img width="1917" height="472" alt="Screenshot-curl" src="https://github.com/user-attachments/assets/7cf7364b-08ec-40c3-bd5d-9cbcf3d2a071" />


---

### Task 5 — wafw00f (WAF Detection)

**Objective:** Detect whether a Web Application Firewall (WAF) is protecting the target site.

**Command executed:**

```bash
$ wafw00f networkwalks.com
```

**Key findings:**

| Field | Value |
|---|---|
| WAF Detected | Yes |
| WAF Product | ModSecurity (SpiderLabs) |
| Requests Made | 2 |

**Why attackers use this:** Knowing a WAF is in place shapes the entire attack strategy. Naive exploitation attempts will be blocked or logged, so an attacker must adapt their technique or attempt WAF bypass methods.

<img width="1278" height="417" alt="Screenshot-wafw00f" src="https://github.com/user-attachments/assets/92211c8b-34c4-4182-b745-6463f1e6b044" />


---

### Task 6 — dnsrecon (Full DNS Enumeration)

**Objective:** Enumerate all DNS records — name servers, mail servers, SPF/TXT records, and service (SRV) records.

**Command executed:**

```bash
$ dnsrecon -d networkwalks.com
```

**Key findings:**

| Record Type | Value |
|---|---|
| NS (Name Servers) | ns6135.hostgator.com / ns6136.hostgator.com |
| A Record | networkwalks.com → 192.232.216.135 |
| MX (Mail Server) | mail.networkwalks.com |
| DNS Software | Bind 9.16.23 |
| TXT (SPF) | `v=spf1 a +mx +ip4:50.87.144.87 +include:websitewelcome.com ~all` |
| TXT (Google Verify) | Present |
| SRV Records | cPanel autodiscovery service records found (184.94.x.x:443) |
| Total Records Found | 8 |

**Why attackers use this:** dnsrecon maps the target's entire DNS footprint. Mail servers, DNS software version, SPF policy, and cPanel service records each represent a potential foothold or attack vector.

<img width="1611" height="612" alt="Screenshot-dnsrecon" src="https://github.com/user-attachments/assets/7fd3aa18-835c-42e0-8eeb-7cf4674f1229" />


---

## 📊 Summary of Findings

| Tool | Key Intelligence Gathered |
|---|---|
| whois | Registrar: GoDaddy, Host: HostGator, Expiry: 2027 |
| whatweb | Apache + WordPress 7.0.4, IP: 192.232.216.135 |
| nslookup | Resolved IP: 192.232.216.135 |
| curl -I | WordPress REST API exposed, ModSecurity headers present |
| wafw00f | WAF confirmed: ModSecurity (SpiderLabs) |
| dnsrecon | MX, SPF, NS, SRV, TXT records — 8 records found |

---

## 💡 What I Learned

**1. Passive Reconnaissance Power**
All six tools only read publicly available information. The target never detected this activity, which is exactly why passive recon is so effective and hard to stop.

**2. Technology Fingerprinting**
whatweb exposed exact software versions. This is the direct link between reconnaissance and exploitation — version numbers map directly to CVEs.

**3. DNS as an Attack Surface**
dnsrecon revealed mail servers, SPF misconfiguration risks, and internal service discovery records. Each DNS record type tells a different story about the target's infrastructure.

**4. WAF Awareness**
Knowing ModSecurity is in place changes the attack approach entirely. A penetration tester must factor this into every subsequent phase.

**5. Header Intelligence**
HTTP headers alone confirmed the WordPress installation, its REST API endpoint, and the session cookie naming convention — without loading a single page.

---

## 🔐 Security & Ethical Use

This module was performed strictly within the scope of the Letter of Authorization issued by Networkwalks (Ref: NW-LOA-B082-017). All activities were passive, non-destructive, and confined to the authorized target only.

---

## 🔗 Tools & References

- **whois:** Pre-installed on Kali Linux
- **whatweb:** Pre-installed on Kali Linux — `whatweb --help`
- **nslookup:** Pre-installed on Kali Linux
- **curl:** Pre-installed on Kali Linux — `curl --help`
- **wafw00f:** Pre-installed on Kali Linux — [https://github.com/EnableSecurity/wafw00f](https://github.com/EnableSecurity/wafw00f)
- **dnsrecon:** Pre-installed on Kali Linux — [https://github.com/darkoperator/dnsrecon](https://github.com/darkoperator/dnsrecon)

---

## 👤 Author

**Bithin Krishna Radhakrishnan**
Cybersecurity Intern — Batch B082
Networkwalks Cybersecurity Program | Week 2 | Project Module 1
