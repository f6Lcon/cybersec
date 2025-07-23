# 🕸️ Maltego README

Maltego is a powerful open-source intelligence (OSINT) and link analysis tool used for reconnaissance, infrastructure mapping, social network analysis, and more. This README provides a quick-start guide, practical examples, and common use cases for Red Teamers, Threat Hunters, and Security Analysts.

---

## 📦 What is Maltego?

Maltego allows you to visually explore relationships between people, groups, domains, emails, IPs, infrastructure, social media accounts, documents, and more — all in an interactive graph format.

---

## 🚀 Quick Start

1. 🔗 Download from: [https://www.maltego.com/downloads/](https://www.maltego.com/downloads/)
2. 🧪 Register for a free **Maltego CE** account
3. 🔐 Add **API keys** (Shodan, VirusTotal, HaveIBeenPwned, etc.)
4. 🌐 Create a **new graph**
5. 🔍 Start dragging entities (e.g., Domain, Person, IP Address) and apply **Transforms**

---

## 🧩 Core Concepts

| Concept     | Description                                               |
|-------------|-----------------------------------------------------------|
| **Entity**  | A node in the graph (person, domain, email, IP, etc.)     |
| **Transform** | A search function to expand an entity's connections     |
| **Graph**   | The visual workspace where entities are linked            |
| **Machine** | Automation script that chains multiple transforms         |

---

## 🎯 Use Cases in Red Teaming / OSINT

| Use Case                        | Example                                                  |
|--------------------------------|----------------------------------------------------------|
| 📧 Email Enumeration           | Track breach exposure using HaveIBeenPwned              |
| 🌍 Domain Mapping              | Discover subdomains, related domains, MX records         |
| 🕵️ People Recon               | Map usernames, social profiles, and leaked accounts      |
| 🌐 Infrastructure Discovery    | Connect IPs → Hosts → Domains → ASNs → Geolocation       |
| 📜 Metadata Extraction         | Find creator names, tool versions in online documents    |
| 👁️‍🗨️ Social Network Analysis   | Visualize influencer networks, threat actor clusters      |

---

## 🔧 Common Entities

| Entity Name          | Use For                              |
|----------------------|--------------------------------------|
| Domain               | Website analysis                     |
| Person               | Identity tracking                    |
| Email Address        | Credential & breach search           |
| IP Address           | Host mapping                         |
| Phone Number         | PII and social media discovery       |
| Alias                | Usernames / handles                  |
| Website              | Crawl structure, tech stack          |
| Document             | Metadata extraction                  |

---

## ⚙️ Common Transforms

| Transform                     | Description                                 |
|-------------------------------|---------------------------------------------|
| **To DNS Name - Forward Lookup** | IP → Hostnames                             |
| **To IP Address**             | Domain → IPs                                |
| **To WHOIS Info**            | Domain → Owner, registrar, contact          |
| **To Email Addresses**       | Domain → Discovered emails                  |
| **To Social Networks**       | Alias → Linked social accounts              |
| **HaveIBeenPwned**           | Email → Leak database check                 |
| **VirusTotal**               | Domain/IP → Reputation info                 |
| **BuiltWith / Shodan**       | Tech stack and exposed services             |

---

## 🛠️ Machines (Automation)

| Machine Name         | Function                                          |
|----------------------|--------------------------------------------------|
| Company Stalker      | Starts from a domain and maps out the company    |
| Footprint L1–L3      | Basic to advanced domain footprinting            |
| Person Recon         | Maps out emails, usernames, accounts             |

---

## 💡 Tips for Red Teaming

- 🧬 Use **Transform Hub** to install more integrations (Shodan, VirusTotal, Polarity, etc.)
- 🎯 Start with broad entities like domain, narrow down as you pivot
- 🧠 Combine Maltego with **Recon-ng**, **SpiderFoot**, or **Amass** for layered recon
- 🛑 Use proxies or VPNs when using transforms that reach out to targets
- 📤 Export graphs to image or `.graphml` for reports

---

## 📚 Resources

- 🔗 [Maltego Docs](https://docs.maltego.com/)
- 🔎 [Transform Hub](https://www.maltego.com/transform-hub/)
- 📓 [OSINT Framework](https://osintframework.com/)
- 📘 [Red Team Field Manual](https://github.com/mantvydasb/Red-Team-Tactics-and-Techniques)

---

## 🧪 Sample Workflow: Domain Enumeration

1. **Drag** a Domain entity (e.g., `example.com`)
2. **Run transforms**:
   - To IP Address
   - To DNS Name
   - To Email Addresses
   - To WHOIS Records
3. **Pivot**:
   - From emails → breaches
   - From IP → Shodan → Ports/Services
   - From WHOIS → Org/Person → Social links

---

## 🔚 Final Thoughts

Maltego is a visual powerhouse for pre-engagement intelligence. When combined with other red teaming tools, it becomes essential for mapping environments, profiling targets, and discovering weak points.

Happy hunting 🕵️‍♂️⚔️
