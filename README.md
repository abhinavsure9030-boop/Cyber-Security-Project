# 🚩 Project: Mobile-Based Penetration Testing Lab
**Target:** OWASP Juice Shop
**Researcher:** abhinavsure9030-boop
**Date:** January 16, 2026

---

## 1. Phase 1: Reconnaissance
I used **Nmap** on a mobile Termux environment to identify active services on the target.
- **Finding:** Open ports 80 (HTTP) and 443 (HTTPS) were discovered.
- **Evidence:** See uploaded Nmap screenshot.

## 2. Phase 2: Vulnerability Exploitation
### SQL Injection (Authentication Bypass Attempt)
- **Vulnerability:** SQL Injection
- **Payload used:** `' OR 1=1 --`
- **Result:** Upon submission, the application triggered a `500 Internal Server Error` (Application Crash).
- **Impact:** Critical. The server's inability to sanitize the input indicates that the backend query was successfully manipulated. This demonstrates a vulnerability to both Injection and Denial of Service (DoS) attacks.
- **Evidence:** See uploaded Login and Application Error screenshots.

## 3. Conclusion & Remediation
The target application is vulnerable to SQL Injection. To fix this, I recommend the developers implement **Parameterized Queries** (Prepared Statements) to ensure user input is never executed as database code.
