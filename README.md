# Web Application Reconnaissance & Fingerprinting Report: networkwalks.com

**Date of Testing:** September 17, 2026  
**Analyst Environment:** Kali Linux  
**Target:** `networkwalks.com`  

---

## ⚠️ Disclaimer & Legal Notice
This report documents passive reconnaissance and fingerprinting techniques performed in a controlled environment for educational and portfolio purposes. Testing was conducted with the assumption of authorized permission on the target. This report does not claim that any vulnerabilities exist.

---

## 1. Environment & Tools Used
The testing was performed using standard Kali Linux tools. 

![Kali Tools](<Screenshot 2026-09-17 121639.png>)

---

## 2. WAF Fingerprinting (WAFW00F)
**Command used:**
```bash
wafw00f networkwalks.com
