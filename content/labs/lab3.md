---
title: "Lab 3 - Authentication Vulnerabilities (password-based)"
date: 2025-12-30
weight: 3
draft: false
description: "Password-based authentication vulnerabilities"
toc: true
---

# Lab 3: Authentication Vulnerabilities (password-based)

<div class="download-section">
    <a href="/iaw301_spring2026/downloads/lab3/Lab3 Authentication Vulnerabilities (password-based).docx" class="download-btn" download>
        Download Lab Material
    </a>
    <a href="/iaw301_spring2026/downloads/lab3/solution.pdf" class="download-btn" download>
        Download My Solution
    </a>
</div>

---

## Objective

Exploit vulnerabilities in password-based login mechanisms using username enumeration and brute-force attacks.

---

## Lab 3a: Username enumeration via different responses

Exploit different error messages to enumerate valid usernames, then brute-force the password.

**Steps:**
1. Capture login request in Burp Suite
2. Send to Intruder, set payload on username parameter
3. Load username wordlist, run Sniper attack
4. Analyze Length column - different length = valid username
5. Valid username found: `akamai`
6. Configure second attack on password parameter
7. Look for 302 status code (redirect = success)
8. Valid password found: `andrew`

**Credentials:** `akamai / andrew`

---

## Lab 3b: Username enumeration via response timing

Exploit server response timing to enumerate usernames, bypassing IP-based protection.

**Steps:**
1. Add `X-Forwarded-For` header to bypass IP blocking
2. Set very long password (100+ chars) to maximize processing time
3. Configure Pitchfork attack:
   - Payload 1: IP numbers (1-100)
   - Payload 2: Username wordlist
4. Enable "Response received" timing column
5. Valid username causes longer response (~2,469ms vs ~260ms)
6. Valid username found: `azureuser`
7. Second Pitchfork attack for password brute-force
8. Look for 302 status code
9. Valid password found: `dragon`

**Credentials:** `azureuser / dragon`

---

## Key Takeaways

- Different error messages can leak valid usernames
- Response timing can reveal valid accounts
- Use generic error messages: "Invalid credentials"
- Implement constant-time responses
- Don't trust X-Forwarded-For for rate limiting

---

## References

- [PortSwigger - Authentication Vulnerabilities](https://portswigger.net/web-security/authentication)
