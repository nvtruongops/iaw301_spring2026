# IAW301 - Web Application Security Labs
## Spring 2026

A comprehensive collection of web application security lab exercises for the IAW301 course, built with Hugo static site generator.

## Course Overview

IAW301 is a hands-on web application security course that covers the most critical security vulnerabilities found in modern web applications. This repository contains all 19 lab exercises designed to provide practical experience with:

- Vulnerability identification and exploitation
- Security testing methodologies  
- Defensive programming practices
- Real-world attack scenarios

## Lab Exercises (19 Total)

### Authentication & Access Control
- **Lab 1**: OWASP TOP 10 Overview
- **Lab 2**: Information Disclosure
- **Lab 3**: Authentication Vulnerabilities (password-based)
- **Lab 4**: Authentication Vulnerabilities (multi-factor authentication)
- **Lab 5**: Authentication Vulnerabilities (other mechanisms)
- **Lab 6**: Access Control - IDOR
- **Lab 7**: Access Control - Privilege Escalation
- **Lab 8**: Access Control - OAuth 2.0

### Injection Attacks
- **Lab 9**: SQL Injection - UNION Attacks
- **Lab 10**: Blind SQL Injection - Time-based
- **Lab 11**: Blind SQL Injection - Error-based
- **Lab 12**: OS Command Injection
- **Lab 13**: Blind OS Command Injection

### Client-Side Attacks
- **Lab 14**: Cross-Site Scripting - Reflected
- **Lab 15**: Cross-Site Scripting - Stored

### Advanced Topics
- **Lab 16**: Server-Side Request Forgery (SSRF)
- **Lab 17**: Race Conditions
- **Lab 18**: Path Traversal
- **Lab 19**: File Upload Vulnerabilities

## Structure

```
├── content/
│   ├── _index.md          # Course homepage
│   └── labs/              # All lab exercises
│       ├── _index.md      # Labs overview
│       ├── lab1.md        # OWASP TOP 10
│       ├── lab2.md        # Information Disclosure
│       └── ...            # Labs 3-19
├── layouts/               # Hugo templates
├── static/css/           # Styling
├── hugo.toml             # Hugo configuration
└── README.md             # This file
```

## Getting Started

### Prerequisites
- [Hugo](https://gohugo.io/installation/) (any version)
- Git

### Running Locally
1. Clone this repository
2. Navigate to the project directory
3. Run Hugo development server:
   ```bash
   hugo server -D
   ```
4. Open http://localhost:1313 in your browser

### Building for Production
```bash
hugo --minify
```

## Course Information

- **Course Code**: IAW301
- **Semester**: Spring 2026
- **Focus**: Web Application Security
- **Format**: Hands-on laboratory exercises
- **Total Labs**: 19

## Learning Objectives

Upon completion of this course, students will be able to:
1. Identify common web application vulnerabilities
2. Perform security assessments of web applications
3. Exploit vulnerabilities in controlled environments
4. Implement appropriate security controls and countermeasures
5. Apply secure coding practices

## License

This project is for educational purposes as part of the IAW301 course.