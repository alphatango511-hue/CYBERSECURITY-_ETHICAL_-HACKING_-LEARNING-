# Web Application Reconnaissance & Fingerprinting Report: networkwalks.com

![Environment](https://img.shields.io/badge/Environment-Kali_Linux-blue)
![Status](https://img.shields.io/badge/Status-Completed-success)
![WAF](https://img.shields.io/badge/WAF-ModSecurity-red)

**Date of Testing:** September 17, 2026  
**Analyst Environment:** Kali Linux  
**Target:** `networkwalks.com`

---

## 1. WAF Fingerprinting (WAFW00F)

**What this tool does:** WAFW00F is a Web Application Firewall fingerprinting tool. It sends requests to a target to determine if a WAF is present and identifies the specific technology protecting the site.

**Command used:**
`wafw00f networkwalks.com`

**Findings:**
- **WAF Detected:** ModSecurity (SpiderLabs)
- **Requests Used:** 2
- **HTTP Patterns:** 403, 404, 405, 500, 502

**Technical Analysis:** 
WAFW00F identified that `networkwalks.com` is protected by a **ModSecurity** Web Application Firewall. ModSecurity is a widely trusted, open-source WAF engine. The tool successfully fingerprinted the WAF using only two requests. The HTTP patterns observed (such as 403 Forbidden and 405 Not Allowed) confirm that the WAF is actively filtering and rejecting suspicious traffic before it reaches the backend server.

**📸 SCREENSHOT 1: WAFW00F OUTPUT**
*[ Paste your WAFW00F screenshot here ]*

---

## 2. HTTP Header Analysis (cURL)

**What this tool does:** cURL is a command-line tool used to transfer data. In this context, it is used to fetch and analyze the HTTP response headers sent by the web server to understand its configuration and redirect rules.

**Command used:**
`curl -I http://networkwalks.com`

**Findings:**
- **Server:** Apache
- **Redirect:** 301 Moved Permanently to HTTPS
- **X-Redirect-By:** WordPress - Really Simple Security
- **X-nginx-cache:** WordPress
- **Permissions-Policy:** Google, Gstatic, reCAPTCHA, Cloudflare

**Technical Analysis:** 
The target enforces HTTPS by responding with a **301 Moved Permanently** redirect. The web server identifies itself as **Apache**. The presence of `X-Redirect-By: WordPress - Really Simple Security` and `X-nginx-cache: WordPress` reveals that the site is running on WordPress and is sitting behind an Nginx reverse proxy or cache layer. The `Permissions-Policy` header restricts certain browser features and integrates Google reCAPTCHA.

**📸 SCREENSHOT 2: CURL OUTPUT**
*[ Paste your cURL screenshot here ]*

---

## 3. Web Technology Fingerprinting (WhatWeb)

**What this tool does:** WhatWeb identifies the technologies used by a website, including CMS platforms, web servers, JavaScript libraries, and analytics tools.

**Command used:**
`whatweb networkwalks.com`

**Findings:**
- **CMS:** WordPress
- **Web Server:** Apache
- **IP Address:** 192.232.216.135
- **Libraries:** Bootstrap, jQuery
- **Title:** Networkwalks Academy

**Technical Analysis:** 
WhatWeb provided a comprehensive technology stack profile. The target is built on **WordPress**, utilizing **Bootstrap** and **jQuery** for frontend rendering. The IP address `192.232.216.135` resolves to a server located in the **United States**. The title "Networkwalks Academy" indicates a standard corporate or educational WordPress deployment.

**📸 SCREENSHOT 3: WHATWEB OUTPUT**
*[ Paste your WhatWeb screenshot here ]*

---

## 4. Domain Registration Information (WHOIS)

**What this tool does:** WHOIS queries domain registration databases to retrieve ownership, registration dates, and name server information.

**Command used:**
`whois networkwalks.com`

**Findings:**
- **Registrar:** GoDaddy.com, LLC
- **Creation Date:** 2019-11-06
- **Registry Expiry Date:** 2027-11-06
- **Name Servers:** NS6135.HOSTGATOR.COM, NS6136.HOSTGATOR.COM
- **Domain Status:** clientDeleteProhibited, clientRenewProhibited, clientTransferProhibited, clientUpdateProhibited

**Technical Analysis:** 
The domain `networkwalks.com` was registered on **November 6, 2019**, through **GoDaddy**. It is secured with standard ICANN transfer and update prohibitions, which prevents unauthorized domain hijacking. The authoritative name servers point to **HostGator**, confirming the hosting provider identified during the WhatWeb scan.

**📸 SCREENSHOT 4: WHOIS OUTPUT**
*[ Paste your WHOIS screenshot here ]*

---

## 5. Conclusion

Based on the tools executed in this exercise, the following infrastructure profile was established for `networkwalks.com`:

1. **Security Posture:** The target is protected by a **ModSecurity (SpiderLabs)** Web Application Firewall.
2. **Hosting & Infrastructure:** The site is hosted on an **Apache** web server with an **Nginx** reverse proxy/cache layer, provided by **HostGator**.
3. **CMS & Stack:** The application is built on **WordPress**, utilizing **Bootstrap** and **jQuery**.
4. **Network:** The site resolves to IP `192.232.216.135` (US) and enforces HTTPS via a 301 redirect.
5. **Domain:** Registered via **GoDaddy** since 2019, with secure lock statuses in place.
