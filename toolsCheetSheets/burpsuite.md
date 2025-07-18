# 🧰 Burp Suite Cheat Sheet

Burp Suite is a powerful tool for web application security testing. This cheat sheet covers the essential features, workflows, shortcuts, and tips to help you use Burp like a pro.

---

## 📦 Table of Contents

- [🔧 Setup Tips](#-setup-tips)
- [🧪 Common Tools](#-common-tools)
- [🧵 Intercept Workflows](#-intercept-workflows)
- [💣 Intruder Payload Types](#-intruder-payload-types)
- [🔎 Repeater Tips](#-repeater-tips)
- [🧭 Decoder Tricks](#-decoder-tricks)
- [🔐 Auth Bypass Tricks](#-auth-bypass-tricks)
- [🎯 Vulnerability Tests](#-vulnerability-tests)
- [⌨️ Hotkeys](#️-hotkeys)
- [📚 Recommended Extensions](#-recommended-extensions)
- [💡 Pro Tips](#-pro-tips)

---

## 🔧 Setup Tips

- Set browser to proxy through **127.0.0.1:8080**
- Install **Burp CA Certificate** in browser:
  - Visit `http://burp` → download → import to browser
- Use **FoxyProxy** extension for easy proxy toggling

---

## 🧪 Common Tools

| Tool      | Use Case                            |
|-----------|--------------------------------------|
| Proxy     | Intercept and modify traffic         |
| Target    | View site map and scope              |
| Repeater  | Manual request crafting              |
| Intruder  | Fuzz parameters                      |
| Decoder   | Encode/decode/encrypt data           |
| Comparer  | Diff two responses                   |
| Extender  | Add custom or community extensions   |
| Logger    | View HTTP history in detail          |

---

## 🧵 Intercept Workflows

- **Pause/Resume Intercept**: Toggle using the “Intercept is on” button
- Right-click → **Send to Repeater / Intruder / Scanner**
- Edit headers, body, cookies, tokens, etc.
- Forward or Drop requests as needed

---

## 💣 Intruder Payload Types

| Type       | Description                             |
|------------|-----------------------------------------|
| Sniper     | One payload position, try all values    |
| Battering Ram | Same payload across all positions     |
| Pitchfork  | Different payloads at each position     |
| Cluster Bomb | All combinations of payloads          |

Payload examples:
- Wordlists (`SecLists`, fuzzing, auth bypass, SQLi)
- Custom payloads like tokens, encodings, shell commands

---

## 🔎 Repeater Tips

- Use Repeater for **manual testing**
- Modify methods (GET/POST), headers, params
- Observe how server responds to different input
- Great for testing:
  - SQLi, XSS, LFI, IDOR, Auth bypass

---

## 🧭 Decoder Tricks

| Action         | Shortcut |
|----------------|----------|
| Base64 decode  | Right-click → Decode as Base64 |
| URL decode     | Right-click → URL decode       |
| Hashing        | Useful for password attacks     |

Example:
%3Cscript%3Ealert(1)%3C/script%3E → <script>alert(1)</script>


---

## 🔐 Auth Bypass Tricks

Try modifying headers like:

X-Forwarded-For: 127.0.0.1
X-Original-URL: /admin
X-Rewrite-URL: /admin
X-Client-IP: 127.0.0.1


- Swap methods (GET/POST)
- Remove or duplicate cookies
- Tamper JWT tokens (in Decoder)
- Look for IDOR vulnerabilities

---

## 🎯 Vulnerability Tests

| Vuln        | Test Ideas                                 |
|-------------|--------------------------------------------|
| SQLi        | `' or 1=1--`, `UNION SELECT`, error responses |
| XSS         | `<script>alert(1)</script>` or variations  |
| LFI         | `../../../../etc/passwd`                   |
| SSRF        | `http://127.0.0.1:80/` or internal URLs    |
| CSRF        | Look for unsafe state-changing GET/POSTs   |
| IDOR        | Increment/decrement user IDs               |
| Auth Bypass | Header tampering, token reuse              |

---

## ⌨️ Hotkeys

| Action                      | Shortcut (Windows/Linux) |
|----------------------------|--------------------------|
| Send to Repeater           | Ctrl+R                   |
| Send to Intruder           | Ctrl+I                   |
| Forward Intercepted Req    | Ctrl+F                   |
| Toggle Intercept           | Ctrl+T                   |
| Search                     | Ctrl+F                   |
| Next/Prev Tab              | Ctrl+Tab / Ctrl+Shift+Tab|

---

## 📚 Recommended Extensions (BApp Store)

- **Autorize** – Test authorization flaws (IDOR)
- **Turbo Intruder** – Fast fuzzing
- **JS Beautifier** – Beautify JS in responses
- **Hackvertor** – Encode/decode on the fly
- **ActiveScan++** – Enhanced scanning logic
- **Param Miner** – Discover hidden parameters

---

## 💡 Pro Tips

- 🔒 Always define scope: Target → Scope → Add host
- ⏳ Use Logger++ for better history tracking
- 📂 Save sessions often: Project Options → Save
- 🎯 Use match & replace rules (Proxy → Options)
- ⚠️ Scanner is only available in Burp Pro
- 🧪 Combine with tools like `ffuf`, `nmap`, `wfuzz` for full recon

---

Burp Suite is your Swiss Army knife for web security testing. Mastering its features will elevate your red teaming and bug bounty game.

Happy Burping! 🧪💥
