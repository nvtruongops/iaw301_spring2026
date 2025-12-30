# Web Security Learning Notes

Personal blog documenting my learning journey in Web Application Security, built with Hugo static site generator.

## About This Project

This is a personal learning blog where I share my notes, experiences, and solutions from studying Web Application Security. The content is based on my coursework at **FPT University**.

## Source & Credits

- **Course**: IAW301 - Web Application Security
- **Institution**: FPT University
- **Learning Platform**: [PortSwigger Web Security Academy](https://portswigger.net/web-security)
- **Reference**: [OWASP Top 10](https://owasp.org/www-project-top-ten/)

## Lab Notes (19 Total)

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

## Project Structure

```
├── content/
│   ├── _index.md          # Homepage
│   ├── about/             # About page
│   ├── resources/         # Learning resources
│   └── labs/              # All lab notes
├── layouts/               # Hugo templates
├── static/css/            # Styling
├── hugo.toml              # Hugo configuration
└── README.md              # This file
```

## Running Locally

### Prerequisites
- [Hugo](https://gohugo.io/installation/)
- Git

### Development
```bash
git clone https://github.com/nvtruongops/iaw301_spring2026.git
cd iaw301_spring2026
hugo server -D
```
Open http://localhost:1313

### Build
```bash
hugo --minify
```

## Disclaimer

- This is a **personal learning blog**, not official course material
- Content represents my own understanding and notes
- All security testing should be done **ethically and legally**
- Only test on systems you have **permission** to test

## License

This project is for educational purposes. Course materials are credited to FPT University.
