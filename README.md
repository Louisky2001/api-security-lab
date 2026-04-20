## 👤 Author

Louis Okperiruisi  
Cybersecurity Analyst | SOC | API Security | AI Security

# 🔐 API Security Lab

## 📌 Overview
This project demonstrates practical API security assessment using industry-standard tools to identify, analyze, and remediate vulnerabilities in real-world API environments.

The assessment was conducted using:
- Qualys TotalAppSec
- Aikido Security Platform
- Wallarm API Security

Target APIs were sourced from:
https://www.apisecuniversity.com/api-tools-and-resources

---

## 🎯 Objectives
- Perform API vulnerability scanning
- Identify security weaknesses
- Analyze risks and impacts
- Recommend remediation strategies
- Improve API security posture

---

## 🛠️ Tools Used
- **Qualys** – Web & API vulnerability scanning
- **Aikido** – API security monitoring & analysis
- **Wallarm** – API threat detection & vulnerability analysis
- **Postman Collections** – API testing

---

## 🔍 Key Findings

### 1. Inconsistent Security Controls (User-Agent Manipulation)
- Different responses based on user-agent
- Potential exposure to:
  - XSS
  - SQL Injection
  - Authorization bypass

✅ **Recommendation:**
- Enforce consistent validation across all platforms
- Apply strict input validation and sanitization

---

### 2. TLS Renegotiation Vulnerability
- Potential MITM attack vector
- Weak TLS session handling

✅ **Recommendation:**
- Enable TLS secure renegotiation
- Enforce TLS 1.2 / TLS 1.3

---

### 3. Missing Rate-Limiting Headers
- No `X-RateLimit-*` headers found
- Risk of abuse and DoS

⚠️ Impact:
- Poor API usage control
- Risk of HTTP 429 errors

✅ **Recommendation:**
- Implement rate limiting using:
  - API Gateway (NGINX, Kong, AWS API Gateway)
  - Middleware (FastAPI + slowapi)
- Add headers:
  - X-RateLimit-Limit
  - X-RateLimit-Remaining
  - X-RateLimit-Reset

---

### 4. Security Misconfiguration (Wallarm Findings)
- Improper configuration exposes internal resources
- Sensitive endpoints accessible

✅ **Recommendation:**
- Secure deployment configurations
- Restrict unnecessary endpoints
- Implement proper access control

---

## 📊 Tools Comparison

| Tool     | Strength                          | Key Finding |
|----------|----------------------------------|-------------|
| Qualys   | Deep vulnerability scanning       | TLS & endpoint inconsistencies |
| Aikido   | Developer-focused security        | Missing rate limits |
| Wallarm  | API threat detection              | Security misconfiguration |

---

## 🧠 Skills Demonstrated
- API Security Testing
- Vulnerability Assessment
- Risk Analysis
- Security Tool Integration
- Security Recommendations & Reporting

---
---

## 📁 Project Structure

api-security-lab/
├── README.md
├── reports/
│   ├── qualys-report.md
│   ├── aikido-report.md
│   └── wallarm-report.md
├── findings/
│   └── key-findings.md
├── screenshots/
│   ├── qualys/
│   ├── aikido/
│   └── wallarm/

---

## 📸 Evidence & Scan Results

### 🔍 Qualys – Vulnerability Detections
![Qualys Detections](./screenshots/qualys/detections.png)

### 🔍 Qualys – Key Finding (Rate Limit Issue)
![Qualys Finding](./screenshots/qualys/findings-summary.png)

---

### 🛡️ Aikido – Critical Security Issue
![Aikido CSP Issue](./screenshots/aikido/issue-details.png)

---

### 🚨 Wallarm – Vulnerable Component Detection
![Wallarm Vulnerability](./screenshots/wallarm/vulnerabilities.png)

## 📈 Project Outcome

- Identified multiple API security vulnerabilities across test environments
- Detected critical misconfigurations, including missing security headers and vulnerable components
- Compared the strengths of Qualys, Aikido, and Wallarm for API security analysis
- Documented practical remediation steps to improve API security posture
- Demonstrated hands-on experience in API security testing, analysis, and reporting

- ## ▶️ How to Reproduce

1. Select a target API from APIsec University resources
2. Import or configure the API target in Qualys, Aikido, and Wallarm
3. Run security scans in each tool
4. Review findings such as missing headers, TLS issues, vulnerable components, and configuration weaknesses
5. Compare results across tools and document remediation recommendations
