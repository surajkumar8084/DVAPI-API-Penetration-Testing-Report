# DVAPI – API Penetration Testing Report

A hands-on penetration testing engagement against **Damn Vulnerable API (DVAPI)**, covering all 10 categories of the **OWASP API Security Top 10 (2023)**. Performed in a controlled, isolated lab environment for educational purposes.

---

## 📋 Overview

| | |
|---|---|
| **Target** | DVAPI (Damn Vulnerable API) |
| **Environment** | Isolated local lab |
| **Methodology** | Manual black-box testing + OWASP API Security Testing Guidelines |
| **Tools Used** | Burp Suite, Postman, JWT Editor, Hashcat |
| **Scope** | All 10 OWASP API Security Top 10 (2023) categories |
| **Status** | Educational project — not performed against any production or third-party system |

> ⚠️ **Disclaimer:** This assessment was conducted strictly against a deliberately vulnerable, self-hosted lab application (DVAPI) for learning purposes. No unauthorized systems were accessed or tested.

---

## 🔍 Findings Summary

| # | Vulnerability | OWASP API Category | Severity | CVSS |
|---|---|---|---|---|
| 1 | Broken Object Level Authorization | API1:2023 | Critical | 9.8 |
| 2 | Broken Authentication | API2:2023 | Critical | 9.8 |
| 3 | Broken Object Property Level Authorization | API3:2023 | Critical | 9.8 |
| 4 | Unrestricted Resource Consumption | API4:2023 | Critical | 9.8 |
| 5 | Broken Function Level Authorization | API5:2023 | Critical | 9.8 |
| 6 | Unrestricted Access to Sensitive Business Flows | API6:2023 | Critical | 9.8 |
| 7 | Server-Side Request Forgery (SSRF) | API7:2023 | Critical | 9.8 |
| 8 | Security Misconfiguration | API8:2023 | Critical | 9.8 |
| 9 | Improper Inventory Management | API9:2023 | Critical | 9.8 |
| 10 | Unsafe Consumption of APIs | API10:2023 | Critical | 9.8 |

Full technical details — including proof-of-concept steps, screenshots, impact analysis, and remediation guidance for each finding — are documented in the [full report](./DVAPI_VAPT_Report.pdf).

---

## 🛠️ Methodology

1. **Reconnaissance** — endpoint discovery and API surface mapping using Postman
2. **Authentication analysis** — token structure review (JWT), login flow testing
3. **Authorization testing** — object-level, property-level, and function-level access control checks
4. **Traffic interception & manipulation** — Burp Suite Proxy + Repeater for request tampering
5. **Token attacks** — JWT secret brute-forcing via Hashcat, token re-signing via JWT Editor
6. **Business logic testing** — mass assignment, resource consumption, and sensitive flow abuse
7. **Reporting** — each finding documented with severity (CVSS 3.0), proof of concept, business impact, and remediation steps

---

## 🎯 Example Finding — Broken Authentication (API2:2023)

A full authentication bypass was achieved by:
1. Capturing a valid JWT via login
2. Intercepting and forwarding traffic through Burp Suite
3. Brute-forcing the JWT signing secret using Hashcat (`-m 16500`) against `rockyou.txt`
4. Re-signing a tampered token (`admin: true`) with the recovered secret using JWT Editor
5. Successfully accessing the admin profile endpoint with the forged token

*(Full step-by-step walkthrough with screenshots in the [full report](./DVAPI_VAPT_Report.pdf))*

---

## 📄 Full Report

The complete report with all proof-of-concept screenshots, per-vulnerability remediation, and OWASP references is available here:
👉 [`DVAPI_VAPT_Report.pdf`](https://github.com/surajkumar8084/DVAPI-API-Penetration-Testing-Report/blob/main/DVAPI%20-%20API%20Penetration%20Testing%20Report.pdf)

---

## 🧰 Tools & Skills Demonstrated

`Burp Suite` · `Postman` · `JWT Editor` · `Hashcat` · `OWASP API Security Top 10` · `Manual Penetration Testing` · `Authorization & Authentication Testing` · `Vulnerability Reporting`

---

## 👤 Author

**Suraj Kumar**
Cybersecurity Enthusiast | eJPT Certified
[LinkedIn](https://www.linkedin.com/in/suraj-kumar-652a60334/) · [GitHub](https://github.com/surajkumar8084) · [TryHackMe](https://tryhackme.com/p/surajkumar8084)

---

*This report was created for educational purposes as part of independent security research and skill-building.*
