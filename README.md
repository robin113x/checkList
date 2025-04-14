# 🛡️ Comprehensive Bug Bounty Checklist (Basic to Advanced)

This checklist provides a structured approach to bug bounty hunting — from beginner steps to advanced techniques — and includes tools you can use at every level.

---

## 1. 🧭 Information Gathering

### Basic
- Subdomain enumeration → `assetfinder`, `amass`, `subfinder`, `crt.sh`
- DNS records analysis → `dnsenum`, `dig`, `dnsrecon`
- Tech stack identification → `Wappalyzer`, `WhatWeb`, `BuiltWith`
- WHOIS & IP range mapping → `whois`, `ipinfo.io`, `bgp.he.net`
- Check robots.txt / sitemap.xml → `dirsearch`, `gobuster`

### Intermediate
- Cloud provider detection → Favicon hash, headers
- Historical data → `gau`, `waybackurls`, `hakrawler`
- JavaScript parsing → `LinkFinder`, `JSParser`, `SecretFinder`
- GitHub repo analysis → `truffleHog`, `gitrob`, dorks

### Advanced
- OSINT on employees → `theHarvester`, `LinkedIn`, `hunter.io`
- ASN enumeration → `bgp.he.net`, `amass intel`
- Cert transparency logs → `crt.sh`, `Censys`, `Certspotter`
- CDN/WAF behavior → `WAFW00F`, header fingerprinting

---

## 2. 🔐 Authentication Testing

### Basic
- Brute force detection → `hydra`, `ffuf`, `nmap`
- Default credentials → `CIRT default creds list`, manual testing
- Password policy testing → UI/UX manual checks

### Intermediate
- MFA analysis → `evilginx`, token replay
- Session flaws → `Burp`, manual session handling
- Account enumeration → Diff response messages

### Advanced
- JWT weaknesses → `jwt_tool`, `HackBar`
- OAuth misconfigurations → `AAuthz`, redirect URI manipulation
- SAML/SSO testing → SAML toolkits, token tampering
- Password reset logic → Burp + custom workflows

---

## 3. ✅ Authorization Testing

### Basic
- IDOR → `Burp`, `Autorize`
- Horizontal privilege escalation → Manual role-switching

### Intermediate
- Function-level control → `Autorize`
- API endpoint auth → `Postman`, `Burp`
- Vertical privilege escalation → Parameter tampering

### Advanced
- JWT claims tampering → `jwt_tool`
- Business logic bypass → Manual testing, macro workflows
- OAuth scope abuse → `AAuthz`, token editing

---

## 4. 🧪 Input Validation Testing

### Basic
- Reflected XSS → `DalFox`, `XSStrike`
- Basic SQLi → `sqlmap`, `sqliv`
- Open Redirects → Manual + payloads

### Intermediate
- Stored/DOM XSS → `DalFox`, browser dev tools
- Command injection → `Commix`
- SSRF → `Burp Collaborator`, `Interactsh`
- File upload flaws → Content-type spoofing

### Advanced
- XXE → DTD-based payloads, `Burp`
- SSTI → `tplmap`, Jinja/Twig payloads
- HTTP header injection → `http-smuggler`
- HTTP parameter pollution → Manual & fuzzer
- WebSocket fuzzing → `wscat`, `Burp`

---

## 5. ⚙️ Configuration Testing

### Basic
- Directory listing → Browser, `gobuster`, `dirsearch`
- Default setups → Manual checks
- Security headers → `SecurityHeaders.com`, `curl`

### Intermediate
- CORS misconfig → `corsy`, CORS scanner
- Verbose errors → Trigger misbehavior manually
- HTTP methods → `curl`, `nmap`, OPTIONS requests

### Advanced
- Cookie attributes → Inspect via DevTools
- Clickjacking → iframe tests
- CSRF → `csrfpoccreator`, token validation

---

## 6. 📦 Business Logic Testing

### Basic
- Negative values → Manual input, logic flow
- Client-side bypass → JS modification

### Intermediate
- Price/quantity tampering → Intercept & edit requests
- Workflow bypass → Replay/tamper requests

### Advanced
- Race conditions → `race-the-web`, `Turbo Intruder`
- Referral/free trial abuse → Manual scenario analysis
- Time-based privilege escalation → Timer manipulation

---

## 7. 🔌 API Testing

### Basic
- Input fuzzing → `Postman`, `ffuf`
- Auth & rate limits → `Burp`, test concurrent hits

### Intermediate
- Broken Object-Level Auth → `Autorize`, `Postman`
- Excessive data exposure → Manual error analysis
- Mass assignment → Add hidden fields manually

### Advanced
- GraphQL flaws → `InQL`, `Altair`, `GraphQLmap`
- Asset management issues → `gau`, `assetnote`
- JWT abuse in APIs → `jwt_tool`, token replay

---

## 8. 📱 Mobile Testing

### Basic
- Insecure storage → `MobSF`, filesystem check
- Insecure comms → Burp proxy, SSL bypass

### Intermediate
- Reverse engineering → `apktool`, `jadx`, `class-dump`
- Debug info in production → Strings & symbol detection

### Advanced
- Code tampering → `Frida`, `objection`
- Dynamic testing → Runtime hooks with `Frida`
- Intent abuse → `adb`, `drozer`

---

## 9. 🎯 Post-Exploitation

### Basic
- Data exposure → Manual search
- Impact validation → PII, tokens, config files

### Intermediate
- Privilege escalation → Enumeration, local exploits
- Pivoting → SSRF, tunnels, internal service abuse

### Advanced
- Persistence → Cookies, scheduled jobs
- Payload chaining → SSRF → RCE → internal enum
- Lateral movement → Local recon, internal creds

---

## 🧠 Advanced Techniques

| Technique             | Tool(s)                     |
|-----------------------|-----------------------------|
| DOM-based XSS         | `DOM Invader`, browser devtools |
| WebSocket testing     | `Burp`, `WS King`, `wscat`  |
| GraphQL attacks       | `InQL`, `Altair`, `GraphQLmap` |
| HTTP Smuggling        | `smuggler.py`, `http-smuggler` |
| Web Cache Poisoning   | `Param Miner`, `Burp`       |
| Prototype Pollution   | JS payloads, custom fuzzing |
| DNS Rebinding         | `singularity`, `dnsrebind`  |
| Timing Attacks        | Manual + `ffuf`              |

---

## 🔁 Continuous Improvement

- 🔍 Log *everything* (even non-vulns)
- ✅ Analyze false positives/negatives
- 📢 Share responsibly (reports/writeups)
- 🔄 Regularly update tools & wordlists
- 🧠 Play CTFs / join Red vs Blue labs
- 📖 Read public reports (HackerOne, Bugcrowd, Intigriti)

---

## 📦 Wordlists & Payloads

- [`PayloadsAllTheThings`](https://github.com/swisskyrepo/PayloadsAllTheThings)
- [`SecLists`](https://github.com/danielmiessler/SecLists)
- [`Commonspeak2`](https://github.com/assetnote/commonspeak2)
- [`JHaddix all.txt`](https://github.com/jhaddix/)

---

🧩 **Feel free to fork and expand this checklist with your own tooling preferences and bug categories!**
