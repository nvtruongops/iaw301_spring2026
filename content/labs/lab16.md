---
title: "Lab 16 - Server-side request forgery (SSRF)"
date: 2025-12-30
draft: false
description: "Server-side request forgery vulnerabilities"
---

# Lab 16: Server-side request forgery (SSRF)

## Objectives
- Understand SSRF vulnerabilities
- Practice exploiting SSRF
- Bypass SSRF protection measures

## Lab Content

### 1. SSRF Overview
- Definition and operating principles
- Types of SSRF attacks
- Impact of SSRF

### 2. SSRF Attack Vectors
- **Internal network scanning**: Internal network scanning
- **Cloud metadata access**: Cloud metadata access
- **File system access**: File system access
- **Port scanning**: Port scanning

### 3. Common SSRF Targets
- `http://localhost/`
- `http://127.0.0.1/`
- `http://169.254.169.254/` (AWS metadata)
- `file:///etc/passwd`
- Internal IP ranges

### 4. Bypass Techniques
- **URL encoding**: URL encoding
- **Alternative IP representations**: Alternative IP representations
- **DNS rebinding**: DNS rebinding attacks
- **Protocol smuggling**: Protocol smuggling

### 5. Practice
- Identify SSRF vulnerabilities
- Access internal services
- Retrieve cloud metadata
- Bypass SSRF filters

### 6. Prevention Measures
- Whitelist allowed domains
- Disable unused protocols
- Network segmentation
- Input validation