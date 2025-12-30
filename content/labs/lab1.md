---
title: "Lab 1 - OWASP TOP 10"
date: 2025-01-01
weight: 1
description: "My notes on OWASP TOP 10 vulnerabilities"
toc: true
---

# Lab 1: Exploring the OWASP Top 10

## Objective

The objective of this lab is to explore the dynamics of the OWASP (Open Web Application Security Project) Top 10 list. We aim to understand how it has evolved over the years, why certain vulnerabilities move up in rank, and its real-world implications. Additionally, we will examine regional and industry-specific variations in the prevalence of these vulnerabilities and identify effective strategies for addressing them.

<div class="download-section">
    <a href="/downloads/lab1/Lab1 OWASP-TOP-10.docx" class="download-btn" download>
        Download Lab
    </a>
</div>

---

## Question 1: OWASP Top 10 Evolution

> **How has the OWASP Top 10 evolved over the past few years, and what are the key differences in the most recent versions compared to earlier ones?**

### 1. Overview of Evolution

Over the past decade, the OWASP Top 10 has fundamentally shifted its focus from **symptom-based code vulnerabilities** to **architectural risks and supply chain integrity**.

- **2017:** The focus was heavily on technical implementation bugs like *Cross-Site Scripting (XSS)* and *XML External Entities (XXE)*.
- **2021:** A major shift occurred towards "Root Cause Analysis," introducing categories like *Insecure Design* and consolidating smaller bugs into broader categories like *Injection*
- **2025 (Current):** The most recent version reflects the complexities of modern software ecosystems. It prioritizes **Supply Chain Security** and **Resilience** against automated AI attacks, moving away from isolated coding errors to systemic failures.

### 2. Comparative Analysis: 2017 vs. 2021 vs. 2025

The table below illustrates the ranking shifts across the three most significant versions.

| Rank | OWASP Top 10: 2025 (Current) | OWASP Top 10: 2021 | OWASP Top 10: 2017 | Analysis of Key Changes |
|------|------------------------------|---------------------|---------------------|------------------------|
| A01 | Broken Access Control | Broken Access Control | Injection | Remains the #1 threat. In 2025, this category has expanded to strictly cover **SSRF** (merged from A10:2021) as it represents a fundamental access failure. |
| A02 | Security Misconfiguration | Cryptographic Failures | Broken Authentication | **Rank Increased.** With the dominance of Cloud and Kubernetes, misconfiguration is now more prevalent than encryption errors. |
| A03 | Software Supply Chain Failures | Injection | Sensitive Data Exposure | **New Scope.** Combines "Vulnerable Components" (A06:2021) and "Integrity Failures" (A08:2021) into a massive category addressing CI/CD and library risks. |
| A04 | Cryptographic Failures | Insecure Design | XML External Entities (XXE) | Dropped in rank but remains critical. The focus is on the protection of data in transit and at rest against quantum decryption risks. |
| A05 | Injection | Security Misconfiguration | Broken Access Control | **Rank Decreased.** Modern ORMs and frameworks have successfully mitigated many SQLi risks, though Command Injection remains a threat. |
| A06 | Insecure Design | Vulnerable and Outdated Components | Security Misconfiguration | Focuses on architectural flaws. Moving "Supply Chain" to A03 allows A06 to focus purely on logical design errors and threat modeling. |
| A07 | Identification and Authentication Failures | Identification and Authentication Failures | Cross-Site Scripting (XSS) | **Stable Rank.** While frameworks handle sessions well, the rise of **AI Deepfakes** and sophisticated phishing has kept identity attacks relevant. |
| A08 | Security Logging and Monitoring Failures | Software and Data Integrity Failures | Insecure Deserialization | **Rank Increased (from A09).** In the age of automated AI attacks, the inability to detect breaches in real-time (Mean Time to Detect) is a fatal flaw. |
| A09 | **API Insecurity** (or *Data Privacy Breaches*) | Security Logging and Monitoring Failures | Using Components with Known Vulnerabilities | **New/Emerging Focus.** As "Integrity" moved to A03, A09 now highlights risks specific to APIs (Zombie APIs, Shadow APIs) which are the backbone of modern apps. |
| A10 | Mishandling of Exceptional Conditions | Server-Side Request Forgery (SSRF) | Insufficient Logging & Monitoring | **New Category.** Replaces SSRF (merged into A01). It addresses "fail-open" errors and logic crashes exploited by AI fuzzing tools. |

### 3. Key Differences in the 2025 Version

**A. The Rise of Supply Chain Security (A03)**
In previous versions (2017/2021), the focus was limited to "Using Components with Known Vulnerabilities." The 2025 update expands this into **Software Supply Chain Failures**, acknowledging that attackers now target the *process* of building software (CI/CD pipelines, repo integrity) rather than just the finished application.

**B. Consolidation of SSRF into Access Control**
Server-Side Request Forgery (SSRF), which debuted as A10 in 2021, has been merged into **Broken Access Control (A01)** in 2025. This simplifies the list by categorizing SSRF as a specific type of access control failure rather than a standalone bug.

**C. Resilience vs. AI (A10)**
The introduction of **Mishandling of Exceptional Conditions** replaces SSRF at A10. This category directly addresses the threat of AI-powered scanners and fuzzers that attempt to crash applications or force them into insecure states through edge-case inputs.

### 4. Conclusion

The evolution from 2017 to 2025 demonstrates that security is no longer just about writing "clean code." It is about **secure architecture (Insecure Design)**, **trusting the supply chain (A03)**, and **resilience against automation (A10)**. Modern developers must look beyond the code editor to secure the entire lifecycle of the application.

### References

1. **OWASP Foundation.** (2025). *OWASP Top 10: 2025 - The Future of AppSec.* Retrieved from [https://owasp.org/Top10/](https://owasp.org/Top10/)
2. **OWASP Foundation.** (2021). *OWASP Top 10: 2021 Release.* Retrieved from [https://owasp.org/Top10/2021/](https://owasp.org/Top10/2021/)
3. **OWASP Foundation.** (2017). *OWASP Top 10 - 2017: The Ten Most Critical Web Application Security Risks.* Retrieved from [https://owasp.org/www-project-top-ten/2017/](https://owasp.org/www-project-top-ten/2017/)

---

## Question 2: Vulnerability Ranking Factors

> **What are the common factors that lead to vulnerabilities moving up in rank within the OWASP Top 10 list? Are there specific trends or technologies that contribute to this change?**

### 1. Common Factors Influencing Ranking Shifts

The ranking of vulnerabilities in the OWASP Top 10 is determined by a combination of data-driven metrics and industry surveys. Generally, a vulnerability moves up the list due to three primary factors based on the OWASP Risk Rating Methodology:

- **Prevalence (Incidence Rate):** This measures how widespread the vulnerability is. If automated scans show that a specific flaw (like *Broken Access Control*) appears in a vast majority of tested applications, its ranking rises significantly.
- **Ease of Exploitability:** This assesses how easy it is for an attacker to exploit the flaw. If new tools or AI scripts allow even unskilled attackers (script kiddies) to exploit a vulnerability, its risk score increases.
- **Severity of Impact:** This measures the damage caused if the vulnerability is exploited. Flaws that lead to total data breaches or system takeovers naturally maintain high rankings.

### 2. Key Trends and Technologies Driving Changes

In the context of the modern threat landscape (2024–2025), several specific trends are driving these shifts:

**A. The "AI-Driven Exploitation" Trend**
The rise of Generative AI has lowered the barrier to entry for attackers. Automated AI agents can now write custom exploit scripts and fuzz API endpoints at a speed humans cannot match.

- *Result:* Vulnerabilities related to logic and error handling (such as **Mishandling of Exceptional Conditions**) are moving up because they are easily discovered by these automated AI tools.

**B. Cloud-Native and Microservices Architectures**
The industry shift from monolithic servers to distributed Cloud/Kubernetes environments has created a massive, complex attack surface.

- *Result:* **Security Misconfiguration** has risen in rank because managing thousands of configuration files across a cloud infrastructure is prone to human error.

**C. Supply Chain Complexity**
Modern development relies heavily on third-party open-source libraries (npm, Maven, PyPI). Attackers have shifted tactics to poisoning these upstream libraries rather than attacking the app directly.

- *Result:* This trend forced the creation and high ranking of **Software Supply Chain Failures**, consolidating previous categories like "Vulnerable Components".

### 3. Conclusion

Vulnerabilities rise in the OWASP Top 10 when technological advancements change the **Return on Investment (ROI)** for attackers. Currently, the combination of **AI automation**, **complex Cloud environments**, and **fragile Supply Chains** is making architectural and configuration flaws far more dangerous than simple coding errors.

### References

1. **OWASP Foundation.** (2021). *OWASP Top 10 Data Analysis and Methodology*.
2. **Snyk.** (2024/2025). *The State of AI in Software Security Report*.
3. **Veracode.** (2024). *State of Software Security, Volume 14*.

---

## Question 3: Real-World Security Incidents

> **Can you identify real-world examples of data breaches or security incidents that were caused by vulnerabilities listed in the OWASP Top 10? What were the consequences, and how could these incidents have been prevented?**

### 1. Introduction

History has consistently demonstrated that the vulnerabilities listed in the OWASP Top 10 are not merely theoretical risks but are the direct causes of some of the largest data breaches in history. Below are three case studies spanning different years, illustrating the persistent danger of these flaws.

### 2. Real-World Case Studies

#### Case Study 1: The Equifax Breach (2017)

- **Vulnerability Involved:** **A06: Vulnerable and Outdated Components** (Now evolved into **A03: Software Supply Chain Failures** in the 2025 list).

- **The Incident:** Attackers exploited a critical vulnerability (CVE-2017-5638) in **Apache Struts**, an open-source framework used by Equifax's customer portal. Equifax had failed to patch this known vulnerability for months after it was disclosed.

- **Consequences:**
  - **Data Impact:** Personal data (SSNs, birth dates) of **147 million consumers** was stolen.
  - **Business Impact:** Equifax agreed to pay at least **$575 million** (up to $700 million) in settlements with the FTC and other regulators.

- **Prevention:**
  - **Automated Patching:** Implement a rigorous patch management process to apply critical security updates within 48 hours.
  - **SCA Tools:** Use Software Composition Analysis (SCA) tools to continuously inventory open-source components and detect known CVEs in the supply chain.

#### Case Study 2: The Capital One Breach (2019)

- **Vulnerability Involved:** SSRF (Server-Side Request Forgery) and A02: Security Misconfiguration. (Note: In 2025, SSRF is categorized under A01: Broken Access Control).

- **The Incident:** A hacker exploited a misconfigured Web Application Firewall (WAF) hosted on AWS. The misconfiguration allowed the attacker to perform an SSRF attack, querying the AWS Metadata Service (IMDSv1) to retrieve temporary IAM credentials, which granted access to S3 buckets.

- **Consequences:**
  - **Data Impact:** 100 million credit card applications and 140,000 Social Security numbers were compromised.
  - **Financial Impact:** Capital One was fined $80 million by U.S. regulators for failing to establish effective risk assessment processes.

- **Prevention:**
  - **Restrict Metadata Access:** Enforce the use of IMDSv2 (which requires session tokens) on AWS instances to prevent simple SSRF attacks.
  - **Least Privilege:** Ensure that the IAM roles assigned to WAFs or web servers have only the minimum necessary permissions.

#### Case Study 3: The Optus Breach (2022)

- **Vulnerability Involved:** **A01: Broken Access Control** and **A09: API Insecurity**.

- **The Incident:** Optus, a major telecommunications company, left a testing API endpoint publicly accessible via the internet without authentication. Worse, the API used sequential identifiers for customer records (ID Enumeration), allowing attackers to systematically harvest data by incrementing customer IDs.

- **Consequences:**
  - **Data Impact:** Personal information of **9.8 million customers** (nearly 40% of Australia's population) was exposed, including names, dates of birth, phone numbers, email addresses, and for some customers, passport and driver's license numbers.
  - **Business Impact:** Optus faced massive public backlash, regulatory investigations, and was required to pay for identity monitoring services for affected customers. The CEO resigned shortly after the incident.

- **Prevention:**
  - **API Authentication:** Implement proper authentication and authorization for all API endpoints, especially those containing sensitive data.
  - **Non-Sequential IDs:** Use UUIDs or other non-predictable identifiers instead of sequential integers for customer records.
  - **API Security Testing:** Regularly audit and penetration test APIs to identify exposed endpoints and access control flaws.

### 3. Common Prevention Strategies

Based on these case studies, several universal prevention strategies emerge:

1. **Automated Security Scanning:** Implement continuous security scanning in CI/CD pipelines to detect vulnerabilities before deployment.

2. **Zero Trust Architecture:** Assume no component is trustworthy by default. Verify every request and limit access based on the principle of least privilege.

3. **Regular Security Audits:** Conduct periodic security assessments, including penetration testing and code reviews, to identify potential vulnerabilities.

4. **Incident Response Planning:** Develop and regularly test incident response procedures to minimize damage when breaches occur.

5. **Security Training:** Ensure development teams are trained on secure coding practices and are aware of the latest threats in the OWASP Top 10.

### 4. Conclusion

These real-world examples demonstrate that OWASP Top 10 vulnerabilities are not abstract concepts but concrete risks that have led to some of the most devastating data breaches in recent history. The financial and reputational damage from these incidents far exceeds the cost of implementing proper security measures. Organizations must treat the OWASP Top 10 as a critical security checklist and implement comprehensive security programs to protect against these well-documented threats.

### References

1. **U.S. Government Accountability Office.** (2018). *Equifax Data Breach: Actions Taken but Opportunities Exist to Improve Oversight of Consumer Reporting Agencies*.
2. **Capital One.** (2019). *Information on the Capital One Cyber Incident*. Retrieved from Capital One official statements.
3. **Australian Cyber Security Centre.** (2022). *Optus Cyber Security Incident - Lessons Learned*.