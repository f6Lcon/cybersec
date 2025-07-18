# 🔐 Common Ports Reference for Red Teaming

This guide provides a concise list of commonly used network ports and the services that run on them. These are crucial to understand during reconnaissance, enumeration, exploitation, and post-exploitation phases of penetration testing and red teaming.

---

## 📦 Table of Contents

- [Basic Services](#basic-services)
- [Web Services](#web-services)
- [Remote Access](#remote-access)
- [File Transfer](#file-transfer)
- [Email Services](#email-services)
- [Database Services](#database-services)
- [Directory Services](#directory-services)
- [Other Notable Ports](#other-notable-ports)
- [Tips](#tips)

---

## 📡 Basic Services

| Port | Protocol | Service            | Notes                         |
|------|----------|--------------------|-------------------------------|
| 80   | TCP      | HTTP               | Web traffic (insecure)        |
| 443  | TCP      | HTTPS              | Secure web traffic (SSL/TLS) |
| 53   | UDP/TCP  | DNS                | Domain Name System            |
| 123  | UDP      | NTP                | Network Time Protocol         |

---

## 🔐 Remote Access

| Port | Protocol | Service | Notes                                  |
|------|----------|---------|----------------------------------------|
| 22   | TCP      | SSH     | Secure Shell                           |
| 23   | TCP      | Telnet  | Insecure remote login                  |
| 3389 | TCP      | RDP     | Remote Desktop Protocol (Windows)      |
| 5900 | TCP      | VNC     | Virtual Network Computing              |

---

## 📁 File Transfer

| Port | Protocol | Service       | Notes                                |
|------|----------|---------------|--------------------------------------|
| 20   | TCP      | FTP-Data      | Data channel                         |
| 21   | TCP      | FTP           | File Transfer Protocol (control)     |
| 69   | UDP      | TFTP          | Trivial File Transfer (no auth)      |
| 137  | UDP      | NetBIOS-Name  | SMB related                          |
| 138  | UDP      | NetBIOS-DGM   | SMB                                  |
| 139  | TCP      | NetBIOS-SSN   | SMB over NetBIOS                     |
| 445  | TCP      | SMB           | File sharing on Windows              |
| 2049 | TCP/UDP  | NFS           | Network File System (Unix/Linux)     |

---

## 📧 Email Services

| Port | Protocol | Service    | Notes                                |
|------|----------|------------|--------------------------------------|
| 25   | TCP      | SMTP       | Send mail                            |
| 110  | TCP      | POP3       | Receive mail                         |
| 143  | TCP      | IMAP       | Manage/read emails                   |
| 465  | TCP      | SMTPS      | Secure SMTP                          |
| 993  | TCP      | IMAPS      | Secure IMAP                          |
| 995  | TCP      | POP3S      | Secure POP3                          |

---

## 🗃️ Database Services

| Port  | Protocol | Database     | Notes                             |
|-------|----------|--------------|-----------------------------------|
| 3306  | TCP      | MySQL        | Common open-source SQL database   |
| 5432  | TCP      | PostgreSQL   | Advanced open-source database     |
| 1433  | TCP      | MSSQL        | Microsoft SQL Server              |
| 1521  | TCP      | Oracle DB    | Oracle database                   |
| 27017 | TCP      | MongoDB      | NoSQL database                    |
| 6379  | TCP      | Redis        | In-memory key-value store         |

---

## 🗂️ Directory Services

| Port | Protocol | Service | Notes                    |
|------|----------|---------|--------------------------|
| 389  | TCP/UDP  | LDAP    | Directory services       |
| 636  | TCP      | LDAPS   | Secure LDAP              |
| 88   | TCP/UDP  | Kerberos| Authentication protocol  |

---

## 🛠️ Other Notable Ports

| Port | Protocol | Service      | Notes                            |
|------|----------|--------------|----------------------------------|
| 111  | TCP/UDP  | RPCbind      | Remote procedure calls (Linux)   |
| 500  | UDP      | ISAKMP       | VPN key exchange (IPSec)         |
| 4500 | UDP      | NAT-T        | IPSec NAT traversal               |
| 8000 | TCP      | Common Alt   | Alternate HTTP port              |
| 8080 | TCP      | HTTP Proxy   | Often used for proxy services    |
| 8443 | TCP      | HTTPS Alt    | Alternate secure HTTP            |

---
