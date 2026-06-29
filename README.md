# API Security Assessment – crAPI

A hands-on security assessment of the **Completely Ridiculous API (crAPI)** focused on identifying and validating vulnerabilities from the **OWASP API Security Top 10**. Each finding includes reproduction steps, supporting evidence, impact analysis, and remediation recommendations.

---

## Scope

| Target | Methodology              | Standard                  |
| ------ | ------------------------ | ------------------------- |
| crAPI  | Black-box Manual Testing | OWASP API Security Top 10 |

---

## Vulnerabilities Covered

|  ID | Finding                                  | Severity |
| :-: | ---------------------------------------- | :------: |
|  01 | Broken Object Level Authorization (BOLA) |   High   |
|  02 | Broken  user Authentication              |   High   |
|  03 | Broken Function Level Authorization      |   High   |
|  04 | Mass Assignment                          |  Medium  |
|  05 | SQL Injection                            |   High   |
|  06 | Server-Side Request Forgery (SSRF)       |   High   |
|  07 | Rate Limiting                            |  Medium  |
|  08 | JWT Vulnerabilities                      |  Medium  |
|  09 | Excessive Data Exposure                  |  Medium  |
|  09 | LLM Vulnerabilities                      |  Medium  |
---

## Tools

Burp Suite • Postman • Firefox • curl • ffuf • jwt_tool

---

## Repository Structure

```text
api-security-assessment-crapi/
│
├── README.md
├── reports/
│   ├── 01_BOLA.md
│   ├── 02_Broken_Authentication.md
│   ├── ...
│
├── screenshots/
│   ├── 01_BOLA.png
│   ├── 02_Broken_Authentication.png
│   ├── ...
```

---

## Report Format

Each report contains:

* Overview
* Reconnaissance
* Vulnerability Analysis
* Exploitation
* Evidence
* Impact
* Remediation
* References
---

## Disclaimer

This assessment was performed in a controlled lab environment against an intentionally vulnerable application for educational purposes only.
