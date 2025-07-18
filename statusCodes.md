# 🌐 Most Common HTTP Status Codes

Understanding HTTP status codes is critical for web application testing, red teaming, and bug bounty hunting. These codes reveal how a server responds to various requests — and can expose misconfigurations, security flaws, or unintended behaviors.

---

## 📦 Table of Contents

- [1xx Informational](#1xx-informational)
- [2xx Success](#2xx-success)
- [3xx Redirection](#3xx-redirection)
- [4xx Client Errors](#4xx-client-errors)
- [5xx Server Errors](#5xx-server-errors)
- [🧠 Tips](#tips)

---

## 1xx Informational

| Code | Meaning                  | Description                              |
|------|--------------------------|------------------------------------------|
| 100  | Continue                 | Request received, continue processing    |
| 101  | Switching Protocols      | Switching to another protocol (WebSocket)|

---

## 2xx Success

| Code | Meaning       | Description                             |
|------|---------------|-----------------------------------------|
| 200  | OK            | Request succeeded                       |
| 201  | Created       | Resource successfully created           |
| 202  | Accepted      | Request accepted but not completed yet  |
| 204  | No Content    | Request succeeded, no content to return |

---

## 3xx Redirection

| Code | Meaning         | Description                                  |
|------|------------------|----------------------------------------------|
| 300  | Multiple Choices | Multiple options for the resource            |
| 301  | Moved Permanently| Resource has been moved permanently          |
| 302  | Found            | Temporary redirect                           |
| 304  | Not Modified     | Cached version can be used                   |
| 307  | Temporary Redirect | Respects original HTTP method (e.g., POST) |

---

## 4xx Client Errors

| Code | Meaning          | Description                                      |
|------|------------------|--------------------------------------------------|
| 400  | Bad Request      | Server can't process request due to bad syntax   |
| 401  | Unauthorized     | Authentication required                          |
| 403  | Forbidden        | Authenticated but not authorized                 |
| 404  | Not Found        | Resource does not exist                          |
| 405  | Method Not Allowed | HTTP method not supported by resource         |
| 429  | Too Many Requests| Rate limiting in effect                          |

---

## 5xx Server Errors

| Code | Meaning                 | Description                              |
|------|-------------------------|------------------------------------------|
| 500  | Internal Server Error   | Generic server error                     |
| 501  | Not Implemented         | Server doesn't support functionality     |
| 502  | Bad Gateway             | Invalid response from upstream server    |
| 503  | Service Unavailable     | Server temporarily unavailable            |
| 504  | Gateway Timeout         | No timely response from upstream server  |

---

## 🧠 Tips

- 🔍 **401 vs 403**:  
  - `401` = Not authenticated  
  - `403` = Authenticated, but not allowed  

- 📁 **404 Enumeration**:  
  Use 404 patterns to guess directories or files.

- 📤 **3xx Responses**:  
  Good indicator of redirects — watch for phishing or alternate login flows.

- 🐞 **5xx Responses**:  
  May expose stack traces, error logs, or other unintended debug info.

---

## 🔧 Tools for HTTP Enumeration

- `curl -I <url>` – See headers and status code  
- `httpx`, `ffuf`, `dirsearch` – Fuzzing for content discovery  
- `burpsuite` – Full-featured web testing tool  
- `nmap -p80,443 --script http-enum <target>` – Discover web endpoints

---

Keep this close during recon, fuzzing, or analyzing web app behavior.  
Happy hunting! 🎯
