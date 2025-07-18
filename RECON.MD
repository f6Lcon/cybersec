Guide on Penetration testing or Bugbounty Hunting

1Find sub domains
2check CM=NAME Records to those subdomains, check for subdomain takeover
3use waybackURLS for URLS
4Use NMAP for port scanning
5Do github recon on webapp
6check for CORS misconfiguaration
7check for email header injection on reset password function .
8check fir SMTP and HOST Headdder Injection.
9check for iframe(for clickjackng)
10check for improper access control and parameter tempering
11check burp history fir hidden endpoints
12use Arjun for finding hidden enpoints
13check for CSRF SSFR parameters XSS and SSTI.
14Check for cryptography in reset password token
15check for unicode injection in email parameter
16check for bypassing Ratelimit
17Headers:
    X-originated-IP: IP
    X-fowarded-for: IP
    X-remote-IP: IP
    X-client-IP: IP
    X-fowarded-Host: IP
18Directory bruteforce
19Http request smuggling
20open redirect through waybackURLs
21Social-Sigon Bypass
22State Parameter in Social Sign-In and check whether its possible to cause DOS using multiple cookie injection.
23file upload CSRF XSS SSRF RCE LFI XXE
24Buffer overflow