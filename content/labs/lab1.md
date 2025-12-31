---
title: "Lab 1 - OWASP TOP 10"
date: 2025-01-01
weight: 1
description: "Exploring the OWASP Top 10 vulnerabilities"
toc: true
---

# Lab 1: Exploring the OWASP Top 10

<div class="download-section">
    <a href="/iaw301_spring2026/downloads/lab1/Lab1 OWASP-TOP-10.docx" class="download-btn" download>
        Download Lab Material
    </a>
    <a href="/iaw301_spring2026/downloads/lab1/solution.pdf" class="download-btn" download>
        Download My Solution
    </a>
</div>

---

## Objective

Explore the OWASP Top 10 evolution, ranking factors, and real-world security incidents.

---

## Question 1: OWASP Top 10 Evolution

Comparison between 2017, 2021, and 2025 versions:

| Key Change | Description |
|------------|-------------|
| **Broken Access Control** | Remains #1, now includes SSRF |
| **Supply Chain Security** | New - combines Vulnerable Components and Integrity Failures |
| **Security Misconfiguration** | Rank increased due to Cloud/Kubernetes adoption |
| **API Insecurity** | New - focuses on API-specific risks |

---

## Question 2: Vulnerability Ranking Factors

3 main factors affecting ranking:
- **Prevalence**: How widespread the vulnerability is
- **Exploitability**: How easy to exploit
- **Impact**: Damage level when exploited

Technology trends driving changes:
- AI-Driven Exploitation
- Cloud-Native Architectures
- Supply Chain Complexity

---

## Question 3: Real-World Security Incidents

| Incident | Vulnerability | Impact |
|----------|--------------|--------|
| **Equifax (2017)** | Vulnerable Components | 147M people, $575M+ |
| **Capital One (2019)** | SSRF + Misconfiguration | 100M records, $80M fine |
| **Optus (2022)** | Broken Access Control + API | 9.8M customers |

---

## Key Takeaways

- OWASP Top 10 shifted from code bugs to architectural and supply chain risks
- AI and Cloud are changing the attack landscape
- Major breaches are linked to OWASP Top 10 vulnerabilities
- Apply: Automated scanning, Zero Trust, Regular audits

---

## References

- [OWASP Top 10](https://owasp.org/www-project-top-ten/)
- [PortSwigger Web Security Academy](https://portswigger.net/web-security)
