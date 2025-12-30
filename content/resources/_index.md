---
title: "Course Resources"
date: 2025-12-30
description: "Essential tools, platforms, and materials for IAW301"
---

# Course Resources
## Tools, Platforms & Materials for IAW301

### Primary Learning Platforms

#### PortSwigger Web Security Academy
- **URL**: https://portswigger.net/web-security/all-topics
- **Description**: Main learning platform with comprehensive web security topics
- **Usage**: Primary source for all lab exercises and theoretical content
- **Access**: Free registration required

#### DVWA (Damn Vulnerable Web Application) v1.0.7
- **URL**: http://www.computersecuritystudent.com/cgi-bin/CSS/process_request_v3.pl?HID=688b0913be93a4d95daed400990c4745&TYPE=SUB
- **Description**: Intentionally vulnerable web application for practice
- **Usage**: Hands-on vulnerability testing and exploitation

### Essential Security Tools

#### Burp Suite
- **Type**: Web Application Security Testing Platform
- **Description**: Professional-grade tool for web security testing
- **Features**:
  - Proxy for intercepting HTTP/HTTPS traffic
  - Scanner for automated vulnerability detection
  - Intruder for automated attacks
  - Repeater for manual testing
- **Versions**: Community (free) and Professional (paid)

#### SQLMap
- **Type**: Automated SQL Injection Testing Tool
- **Description**: Open-source penetration testing tool
- **Features**:
  - Automatic SQL injection detection
  - Database fingerprinting
  - Data extraction capabilities
  - Support for multiple database systems

### Course Management System

#### FPT Learning Management System
- **URL**: https://flm.fpt.edu.vn/
- **Purpose**: 
  - Course announcements and updates
  - Assignment submissions
  - Grade tracking
  - Course materials download
- **Access**: Student credentials required

### Lab Exercise Links

Each lab corresponds to specific PortSwigger Academy topics:

1. **Lab 1**: [OWASP Top 10](https://portswigger.net/web-security)
2. **Lab 2**: [Information Disclosure](https://portswigger.net/web-security/information-disclosure)
3. **Lab 3**: [Password-based Authentication](https://portswigger.net/web-security/authentication/password-based)
4. **Lab 4**: [Multi-factor Authentication](https://portswigger.net/web-security/authentication/multi-factor)
5. **Lab 5**: [Other Authentication Mechanisms](https://portswigger.net/web-security/authentication/other-mechanisms)
6. **Lab 6**: [Insecure Direct Object References](https://portswigger.net/web-security/access-control/lab-insecure-direct-object-references)
7. **Lab 7**: [Privilege Escalation](https://portswigger.net/web-security/access-control/lab-user-id-controlled-by-request-parameter)
8. **Lab 8**: [OAuth Authentication Bypass](https://portswigger.net/web-security/oauth/lab-oauth-authentication-bypass-via-oauth-implicit-flow)
9. **Lab 9**: [SQL Injection UNION Attacks](https://portswigger.net/web-security/sql-injection/union-attacks/lab-determine-number-of-columns)
10. **Lab 10**: [Time-based Blind SQL Injection](https://portswigger.net/web-security/sql-injection/blind/lab-time-delays)
11. **Lab 11**: [Error-based Blind SQL Injection](https://portswigger.net/web-security/sql-injection/blind/lab-conditional-errors)
12. **Lab 12**: [OS Command Injection](https://portswigger.net/web-security/os-command-injection/lab-simple)
13. **Lab 13**: [Blind OS Command Injection](https://portswigger.net/web-security/os-command-injection/lab-blind-time-delays)
14. **Lab 14**: [Reflected XSS](https://portswigger.net/web-security/cross-site-scripting/dom-based/lab-dom-xss-reflected)
15. **Lab 15**: [Stored XSS](https://portswigger.net/web-security/cross-site-scripting/dom-based/lab-dom-xss-stored)
16. **Lab 16**: [Server-side Request Forgery](https://portswigger.net/web-security/ssrf/blind/lab-out-of-band-detection)
17. **Lab 17**: [Race Conditions](https://portswigger.net/web-security/race-conditions/lab-race-conditions-limit-overrun)
18. **Lab 18**: [Path Traversal](https://portswigger.net/web-security/file-path-traversal/lab-absolute-path-bypass)
19. **Lab 19**: [File Upload Vulnerabilities](https://portswigger.net/web-security/file-upload)

### Additional Resources

#### Documentation & References
- **OWASP Top 10**: https://owasp.org/www-project-top-ten/
- **OWASP Web Security Testing Guide**: https://owasp.org/www-project-web-security-testing-guide/
- **CWE (Common Weakness Enumeration)**: https://cwe.mitre.org/

#### Browser Extensions for Security Testing
- **Wappalyzer**: Technology stack identification
- **Cookie Editor**: Cookie manipulation
- **User-Agent Switcher**: User agent modification

### Setup Instructions

#### For Burp Suite Community
1. Download from https://portswigger.net/burp/communitydownload
2. Install and configure browser proxy settings
3. Import Burp's CA certificate for HTTPS testing

#### For SQLMap
1. Install Python 3.x
2. Download SQLMap from https://sqlmap.org/
3. Run via command line: `python sqlmap.py`

### Important Notes

- **Ethical Use**: All tools and techniques taught in this course are for educational purposes only
- **Legal Compliance**: Only test on authorized systems and applications
- **Lab Environment**: Use provided lab environments and avoid testing on production systems
- **Academic Integrity**: Complete all assignments individually unless group work is specified