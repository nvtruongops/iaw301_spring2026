---
title: "Lab 5 - Authentication Vulnerabilities (other authentication mechanisms)"
date: 2026-01-06
weight: 5
draft: false
description: "Exploiting vulnerabilities in stay-logged-in cookies and offline password cracking"
toc: true
---

# Lab 5: Authentication Vulnerabilities (other authentication mechanisms)

<div class="download-section">
    <a href="/iaw301_spring2026/downloads/lab5/Lab5 Authentication Vulnerabilities (other authentication mechanisms).docx" class="download-btn" download>
        Download Lab Material
    </a>
    <a href="/iaw301_spring2026/downloads/lab5/solution.pdf" class="download-btn" download>
        Download My Solution
    </a>
</div>

## Objectives
- Understand how "Stay logged in" cookies are constructed and validated.
- Exploit weak cookie generation logic using Brute-force attacks.
- Combine Cross-Site Scripting (XSS) with weak session mechanisms to steal cookies.
- Perform offline password cracking from stolen hashed credentials.

## Lab Content

### 1. Challenge 1: Brute-forcing a stay-logged-in cookie
**Vulnerability:** The application uses a predictable pattern for the "stay-logged-in" cookie: `base64(username:md5(password))`.

**Exploitation Steps:**
- **Analysis:** Logged in as `wiener` to decode and identify the cookie structure.
- **Verification:** Used **Burp Intruder** to reconstruct a valid cookie for the user `wiener` to confirm the logic.
- **Attack:** Brute-forced the victim `carlos`'s cookie using a list of candidate passwords.
- **Result:** Successfully hijacked `carlos`'s session by injecting the generated valid cookie.

### 2. Challenge 2: Offline password cracking
**Vulnerability:** The application leaks the password hash inside the session cookie and is vulnerable to Stored XSS.

**Exploitation Steps:**
- **Cookie Theft:** Injected a Stored XSS payload into a blog comment to send the victim's cookie to the **Exploit Server**.
- **Extraction:** Retrieved the cookie `carlos:hash` from the access logs.
- **Cracking:** Decoded the Base64 cookie and used an online rainbow table (CrackStation) to crack the MD5 hash `26323c16d5f4dabff3bb136f2460a943`.
- **Result:** Recovered the password `onceuponatime`, logged in as `carlos`, and deleted the account.

## Tools Used
- **Burp Suite Professional/Community:** Proxy, Intruder, Decoder.
- **Browser Developer Tools:** Cookie manipulation.
- **Exploit Server:** Receiving exfiltrated data (XSS).
- **CrackStation:** Online hash cracking.