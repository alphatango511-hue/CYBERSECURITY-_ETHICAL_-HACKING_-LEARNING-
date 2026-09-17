# Web Application Reconnaissance & Fingerprinting Report: networkwalks.com

![Kali Linux](https://img.shields.io/badge/Environment-Kali_Linux-blue)
![Status](https://img.shields.io/badge/Status-Completed-success)
![WAF](https://img.shields.io/badge/WAF-ModSecurity-red)

**Date of Testing:** September 17, 2026  
**Analyst Environment:** Kali Linux  
**Target:** `networkwalks.com`  

---

## ⚠️ Disclaimer & Legal Notice

This report documents passive reconnaissance and fingerprinting techniques performed in a controlled environment for educational and portfolio purposes. 

*   Testing was conducted with the assumption of authorized permission on the target.
*   This report does not claim that any vulnerabilities exist.
*   No attempts were made to bypass the identified security controls or exploit the target.
*   **Never perform reconnaissance on systems you do not own or have explicit written permission to test.**

---

## 📖 Table of Contents
1. [Environment & Tools Used](#1-environment--tools-used)
2. [WAF Fingerprinting (WAFW00F)](#2-waf-fingerprinting-wafw00f)
3. [HTTP Header Analysis (cURL)](#3-http-header-analysis-curl)
4. [Web Technology Fingerprinting (WhatWeb)](#4-web-technology-fingerprinting-whatweb)
5. [Domain Registration Information (WHOIS)](#5-domain-registration-information-whois)
6. [Conclusion](#6-conclusion)
7. [Appendix: How to Reproduce](#7-appendix-how-to-reproduce)

---

## 1. Environment & Tools Used
The testing was performed using standard Kali Linux tools. The following screenshot shows the Kali Linux Tools page used to select the appropriate utilities for this exercise.

![Kali Linux Tools](screenshots/kali-tools.png)

---

## 2. WAF Fingerprinting (WAFW00F)

**Command:**
```bash
wafw00f networkwalks.com
