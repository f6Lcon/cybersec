# 🕵️ Wireshark Cheat Sheet

Wireshark is a powerful packet analyzer used for capturing and analyzing network traffic. This cheat sheet includes capture filters, display filters, shortcuts, and real-world red teaming use cases.

---

## 📦 Table of Contents

- [🎯 Capture Filters vs Display Filters](#-capture-filters-vs-display-filters)
- [🔍 Common Display Filters](#-common-display-filters)
- [🧪 Protocol-Specific Filters](#-protocol-specific-filters)
- [💀 Red Team Use Cases](#-red-team-use-cases)
- [⌨️ Useful Shortcuts](#️-useful-shortcuts)
- [🧠 Tips & Tricks](#-tips--tricks)
- [📚 Resources](#-resources)

---

## 🎯 Capture Filters vs Display Filters

| Type           | Use For                     | Syntax Example            |
|----------------|-----------------------------|---------------------------|
| **Capture**    | **During capture only**     | `port 80`                 |
| **Display**    | **After capture analysis**  | `http.request.method == "GET"` |

---

## 🔍 Common Display Filters

| Filter                          | Description                          |
|---------------------------------|--------------------------------------|
| `ip.addr == 192.168.1.1`        | Traffic to/from host                 |
| `tcp.port == 80`                | Traffic over TCP port 80             |
| `http`                          | Show HTTP packets                    |
| `tcp.flags.syn == 1`            | SYN packets (TCP handshake)          |
| `tcp.flags.reset == 1`          | TCP reset flags                      |
| `frame contains "password"`     | Find sensitive keywords              |
| `dns.qry.name == "example.com"` | DNS query for specific domain        |

---

## 🧪 Protocol-Specific Filters

### 🔐 Credentials & Auth

| Protocol | Filter Example                            | Notes                      |
|----------|--------------------------------------------|----------------------------|
| HTTP     | `http.authorization`                     | Base64 auth header         |
| FTP      | `ftp.request.command == "PASS"`          | FTP credentials            |
| Telnet   | `telnet`                                 | Plaintext login            |
| SMB      | `smb2` or `smb`                          | File shares, hashes        |
| Kerberos | `kerberos`                              | Look for AS-REQ/TGS-REP    |
| NTLM     | `ntlmssp.auth`                          | NTLM auth details          |

### 🧭 Recon & Enumeration

| Use Case        | Filter                               |
|------------------|--------------------------------------|
| DNS Lookups      | `dns` or `dns.qry.name`              |
| NetBIOS Traffic  | `nbns` or `udp.port == 137`          |
| ARP Scans        | `arp`                                |
| Nmap SYN Scan    | `tcp.flags.syn == 1 and tcp.flags.ack == 0` |

---

## 💀 Red Team Use Cases

| Task                          | Filter / Tip                          |
|------------------------------|----------------------------------------|
| 🕸️ Identify open services    | Look at SYN packets and TCP handshakes |
| 🔑 Capture credentials       | Use filters for `ftp`, `http.auth`, etc |
| 🧭 DNS mapping               | `dns.qry.name` to identify target domains |
| 🎭 MITM attack confirmation  | Look for duplicate IPs or ARP spoofing  |
| 📦 Exfil detection           | Look for strange protocols or large outbound traffic |
| 📥 File downloads            | `http.content_type` or large `tcp.stream` sizes |

---

## ⌨️ Useful Shortcuts

| Shortcut | Description                          |
|----------|--------------------------------------|
| `Ctrl + E` | Toggle packet capturing             |
| `Ctrl + K` | Clear display filter                |
| `Ctrl + F` | Find in packets                     |
| `Ctrl + Shift + F` | Advanced packet search      |
| `Ctrl + H` | Hide/show packet details            |
| `Ctrl + M` | Mark packet                         |
| `Ctrl + ↑/↓` | Navigate to next/prev packet     |

---

## 🧠 Tips & Tricks

- 🔍 **Follow TCP Stream**: Right-click → "Follow" → "TCP Stream"  
- 🕵️ **Reassemble HTTP files**: Export → Objects → HTTP  
- ⛔ **Avoid filtering with equals for existence checks**:  
  Use `http.request` (not `http.request == 1`)  
- 🗃️ **Save filtered packets**:  
  File → Export Specified Packets

---

## 📚 Resources

- [Wireshark Display Filter Reference](https://wiki.wireshark.org/DisplayFilters)
- [PacketLife Filter Cheat Sheet](https://packetlife.net/media/library/23/Wireshark_Display_Filters.pdf)
- [GTFOBins for Traffic Analysis](https://gtfobins.github.io/)
- [Red Team Notes](https://redteamnotes.com/)

---

🎯 Keep your eyes sharp, filters tighter, and traffic decrypted.  
Happy sniffing!
