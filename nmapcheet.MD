# 🛡️ Nmap Cheatsheet

This is a comprehensive reference for commonly used **Nmap** commands, including port scanning, host discovery, version detection, evasion techniques, output formatting, and more.

---

## 📍 Port Specific Scanning

| Command | Description |
|--------|-------------|
| `nmap -p 23 123.1.1` | Scan specific port 23 |
| `nmap -p 23-100 123.1.1` | Scan ports 23 through 100 |
| `nmap -pU:110,T:23-25,443 123.1.1` | Scan specific UDP and TCP ports |
| `nmap -p- 123.1.1` | Scan all 65535 ports |
| `nmap -p smtp,https 123.1.1` | Scan by service name |
| `nmap -F 123.1.1` | Fast scan (top 100 ports) |
| `nmap -p "*" 123.1.1` | Scan using all known service names |
| `nmap -r 123.1.1` | Scan ports sequentially |

---

## 🌐 Host Discovery

| Command | Description |
|--------|-------------|
| `nmap -sL 123.1.1` | List targets without scanning |
| `nmap -sn 123.1.1` | Ping scan only (no port scan) |
| `nmap -Pn 123.1.1` | Skip host discovery (assume host is up) |
| `nmap -PS22-25,80 123.1.1` | TCP SYN discovery on ports 22–25, 80 |
| `nmap -PA22-25,80 123.1.1` | TCP ACK discovery |
| `nmap -PU53 123.1.1` | UDP discovery on port 53 |
| `nmap -PR 123.1.1/8` | ARP discovery in local networks |
| `nmap -n 123.1.1` | Disable DNS resolution |

---

## 🔍 Version Detection

| Command | Description |
|--------|-------------|
| `nmap -sV 123.1.1` | Detect service versions |
| `nmap -sV --version-intensity 6 123.1.1` | Set version detection intensity (0–9) |
| `nmap -sV --version-all 123.1.1` | Use all probes (max intensity) |
| `nmap -sV --version-light 123.1.1` | Lighter version detection |
| `nmap -A 123.1.1` | Aggressive scan (OS, version, script, traceroute) |
| `nmap -O 123.1.1` | OS detection only |

---

## 🧱 Firewall Evasion & Bypass

| Command | Description |
|--------|-------------|
| `nmap -f 123.1.1` | Fragment packets |
| `nmap --mtu [MTU] 123.1.1` | Set custom MTU size |
| `nmap -sI [zombie] 123.1.1` | Idle zombie scan |
| `nmap --source-port [PORT] 123.1.1` | Use specific source port |
| `nmap --data-length [SIZE] 123.1.1` | Append random data |
| `nmap --randomize-hosts 172.1.1.0/24` | Randomize host scanning order |

---

## ⏱️ Timing Options

| Command | Description |
|--------|-------------|
| `nmap -T0 123.1.1` | Paranoid (slowest scan) |
| `nmap -T5 123.1.1` | Insane (fastest scan) |

---

## ⚙️ Scan Types

| Command | Description |
|--------|-------------|
| `nmap -sS 123.1.1` | TCP SYN scan (stealth) |
| `nmap -sT 123.1.1` | TCP connect scan |
| `nmap -sA 123.1.1` | TCP ACK scan |
| `nmap -sU 123.1.1` | UDP scan |
| `nmap -sF 123.1.1` | TCP FIN scan |
| `nmap -sX 123.1.1` | Xmas scan |
| `nmap -sP 123.1.1` | Ping scan (legacy) |
| `nmap -sL 123.1.1` | List scan (no packets sent) |

---

## 📝 Output Formats

| Command | Description |
|--------|-------------|
| `nmap -oN scan.txt 123.1.1` | Normal output |
| `nmap -oX scan.xml 123.1.1` | XML format |
| `nmap -oG grep.txt 123.1.1` | Grepable format |
| `nmap -oA scan 123.1.1` | All formats (`.nmap`, `.xml`, `.gnmap`) |

---

## 🧩 Miscellaneous Options

| Command | Description |
|--------|-------------|
| `nmap -6 123.1.1` | Scan IPv6 targets |
| `nmap --proxies proxy1,proxy2 123.1.1` | Use proxies |
| `nmap --open 123.1.1` | Show only open ports |

---

## ❓ How to Display `ftp` Client Help Menu

To show the FTP client help menu, use:

```bash
ftp --help
