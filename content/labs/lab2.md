---
title: "Lab 2 - Information Disclosure"
date: 2025-12-30
weight: 2
draft: false
description: "Information Disclosure vulnerabilities"
toc: true
---

# Lab 2: Information Disclosure Vulnerabilities

<div class="download-section">
    <a href="/iaw301_spring2026/downloads/lab2/Lab2 Information-Disclosure.docx" class="download-btn" download>
        Download Lab Material
    </a>
    <a href="/iaw301_spring2026/downloads/lab2/solution.pdf" class="download-btn" download>
        Download My Solution
    </a>
</div>

---

## Objective

Understand and exploit Information Disclosure vulnerabilities via backup files and version control.

---

## Lab 2a: Source code disclosure via backup files

Exploit backup files to obtain database credentials.

**Steps:**
1. Access `/robots.txt` - found `Disallow: /backup`
2. Access `/backup` - found `ProductTemplate.java.bak`
3. Analyze source code - found hard-coded password in `ConnectionBuilder`
4. Submit password - Lab solved

**Credentials found:** `postgres / lgeduby52fjxafqtah57b2mmm2kyxjpv`

---

## Lab 2b: Information disclosure in version control history

Exploit exposed .git directory to recover deleted admin password.

**Steps:**
1. Access `/.git` - server returns directory listing
2. Download repository: `wget -r https://target/.git/`
3. Check git log - found commit "Remove admin password from config"
4. Run `git show <commit-hash>` - found password in diff
5. Login as admin, delete user carlos - Lab solved

**Credentials found:** `administrator / onh1u8evabuoxpy8ubw9`

---

## Key Takeaways

- Remove backup files (.bak, .old) before deployment
- Block .git directory access on web server
- Never hard-code credentials - git history persists even after deletion

---

## References

- [PortSwigger - Information Disclosure](https://portswigger.net/web-security/information-disclosure)
