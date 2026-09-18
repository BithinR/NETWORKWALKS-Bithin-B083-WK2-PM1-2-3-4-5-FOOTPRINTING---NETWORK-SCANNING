<div align="center">

# 🔐 Footprinting & Reconnaissance with GHDB

**W2-PM2 | Week 2 | Project Module 2**

</div>

<p align="center">
  <img src="https://img.shields.io/badge/Skill-Cybersecurity-404040?style=flat-square&labelColor=C00000" />
  <img src="https://img.shields.io/badge/Tool-Google%20Hacking%20Database-E87500?style=flat-square&labelColor=000000" />
  <img src="https://img.shields.io/badge/Platform-exploit--db.com-238F89?style=flat-square&labelColor=000000" />
  <img src="https://img.shields.io/badge/Networkwalks-B082-404040?style=flat-square&labelColor=C00000" />
</p>

---

## 📌 Project Overview

This module covers **passive footprinting using the Google Hacking Database (GHDB)**. GHDB is a large collection of ready-made Google search queries called "Google dorks," hosted at `exploit-db.com`. These dorks use standard Google search operators in creative ways to surface sensitive information that websites have accidentally left publicly accessible — exposed cameras, open directories, login portals, config files, and downloadable documents.

Because all data is retrieved directly from Google's index, the target is never contacted and never knows it is being studied. This makes GHDB one of the quietest and hardest-to-detect forms of footprinting.

---

## 🎯 Objectives

- Use GHDB dorks to locate **10 live, exposed, and accessible security cameras** on the Internet
- Use GHDB dorks to locate **10 listings containing downloadable mathematics eBooks in PDF format**
- Record every finding with its link, relevant dork used, and credentials (if exposed)

---

## 🏗️ Lab Environment

| Component | Configuration |
|---|---|
| 🖥️ OS | Windows (Host) |
| 🌐 Browser | Google Chrome |
| 📡 GHDB Source | https://www.exploit-db.com/google-hacking-database |
| 🔍 Search Engine | Google (google.com) |

---

## 🪜 Task Execution

---

### Task 1 — Find 10 Live Vulnerable Security Cameras

**Objective:** Use GHDB camera dorks to find live, exposed, and accessible IP camera feeds that are publicly visible on the Internet.

**Procedure:**

1. Opened `https://www.exploit-db.com` and navigated to the **GHDB** section from the left menu.
2. Searched for the keyword **"cam"** in the GHDB quick search bar.
3. Copied dorks one by one from the results list.
4. Pasted each dork into `google.com` and searched.
5. Opened each result link, verified it showed a live camera feed, and recorded it.

> 📸 **Screenshot:** `screenshots/task1-ghdb-cam-search.png`
>
> *(Insert screenshot of the GHDB website showing results for the "cam" search)*

> 📸 **Screenshot:** `screenshots/task1-google-dork-search.png`
>
> *(Insert screenshot of Google search results for the camera dork)*

> 📸 **Screenshot:** `screenshots/task1-live-camera-feed.png`
>
> *(Insert screenshot of one verified live exposed camera feed in the browser)*

**Dorks used (examples):**

```
intitle:"webcamXP" inurl:8080
intitle:"Live View / - AXIS"
intitle:"EvoCam" inurl:"webcam.html"
inurl:axis-cgi/jpg
allintitle: "Network Camera NetworkCamera"
inurl:/view.shtml
intitle:"Login" intext:"cam"
intitle:"index of" "/DCIM/camera"
intitle:ip camera login page
intitle:"Microseven M7CAM IP Camera"
```

**Results Table:**

| No. | Link | Relevant Dork | Username/Password (if any) |
|---|---|---|---|
| 1 | *(insert verified URL)* | `intitle:"webcamXP" inurl:8080` | --- |
| 2 | *(insert verified URL)* | `intitle:"Live View / - AXIS"` | --- |
| 3 | *(insert verified URL)* | `inurl:axis-cgi/jpg` | --- |
| 4 | *(insert verified URL)* | `allintitle: "Network Camera NetworkCamera"` | --- |
| 5 | *(insert verified URL)* | `intitle:"EvoCam" inurl:"webcam.html"` | --- |
| 6 | *(insert verified URL)* | `inurl:/view.shtml` | --- |
| 7 | *(insert verified URL)* | `intitle:"Login" intext:"cam"` | --- |
| 8 | *(insert verified URL)* | `intitle:"index of" "/DCIM/camera"` | --- |
| 9 | *(insert verified URL)* | `intitle:ip camera login page` | --- |
| 10 | *(insert verified URL)* | `intitle:"Microseven M7CAM IP Camera"` | --- |

> 📸 **Screenshot:** `screenshots/task1-camera-results-table.png`
>
> *(Insert screenshot showing your completed results table with verified camera links)*

---

### Task 2 — Find 10 Listings with Downloadable Mathematics eBooks (PDF)

**Objective:** Use GHDB dorks to locate open directory listings containing downloadable mathematics eBooks in PDF format.

**Procedure:**

1. On `google.com`, searched the following dork:

```
intitle:index.of "parent directory" mathematics pdf
```

2. Opened results one by one and verified each listing contained actual mathematics PDF files.
3. Recorded the link and relevant dork for each verified result.

> 📸 **Screenshot:** `screenshots/task2-google-dork-search.png`
>
> *(Insert screenshot of the Google search results for the mathematics PDF dork)*

> 📸 **Screenshot:** `screenshots/task2-open-directory-listing.png`
>
> *(Insert screenshot of a verified open directory page showing mathematics PDF files)*

**Results Table:**

| No. | Link | Relevant Dork | Username/Password (if any) |
|---|---|---|---|
| 1 | https://www.skylineuniversity.ac.ae/pdf/math/ | `intitle:index.of "parent directory" mathematics pdf` | --- |
| 2 | *(insert verified URL)* | `intitle:index.of "parent directory" mathematics pdf` | --- |
| 3 | *(insert verified URL)* | `intitle:index.of "parent directory" mathematics pdf` | --- |
| 4 | *(insert verified URL)* | `intitle:index.of mathematics filetype:pdf` | --- |
| 5 | *(insert verified URL)* | `intitle:index.of mathematics filetype:pdf` | --- |
| 6 | *(insert verified URL)* | `inurl:/pdf/math` | --- |
| 7 | *(insert verified URL)* | `inurl:/pdf/math` | --- |
| 8 | *(insert verified URL)* | `intitle:"Index of" calculus pdf` | --- |
| 9 | *(insert verified URL)* | `intitle:"Index of" calculus pdf` | --- |
| 10 | *(insert verified URL)* | `intitle:index.of "parent directory" mathematics pdf` | --- |

> 📸 **Screenshot:** `screenshots/task2-ebook-results-table.png`
>
> *(Insert screenshot of your completed results table with all 10 verified eBook listing links)*

---

## 💡 What I Learned

**1. Google as a Recon Tool**
Google constantly indexes everything websites make public. GHDB turns standard Google into a precision reconnaissance instrument — no special tool or skill needed beyond knowing the right search syntax.

**2. Why GHDB is So Dangerous**
Because the target is never contacted, there is no log entry, no IDS alert, and no way for the target to know it is being studied. This makes it one of the stealthiest recon techniques available.

**3. Exposed Cameras**
A surprising number of IP cameras are accessible from the public Internet with no authentication at all. Owners often do not realize their camera streams are indexed by Google.

**4. Open Directory Risks**
Open directory listings (`intitle:index.of`) expose entire file structures. Files placed in a web-accessible folder without proper access controls are effectively public — including sensitive documents, credentials, and proprietary materials.

**5. Defender's Perspective**
The same dorks an attacker uses are used by security teams to audit their own public exposure. Periodically running GHDB dorks against your own domain is a fast way to discover unintended leaks before an attacker does.

---

## 🔐 Security & Ethical Use

All activities in this module were performed in accordance with GHDB's intended use — security research and education. No systems were accessed beyond reading their publicly visible information as indexed by Google. No data was downloaded, modified, or stored from any of the discovered targets.

---

## 🔗 Tools & References

- **Google Hacking Database:** [https://www.exploit-db.com/google-hacking-database](https://www.exploit-db.com/google-hacking-database)
- **Exploit Database:** [https://www.exploit-db.com](https://www.exploit-db.com)
- **GHDB Documentation:** [https://www.exploit-db.com/google-hacking-database](https://www.exploit-db.com/google-hacking-database)

---

## 👤 Author

**Emmanuel Bafi**
Cybersecurity Intern — Batch B082
Networkwalks Cybersecurity Program | Week 2 | Project Module 2
