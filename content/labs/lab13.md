---
title: "Lab 13 - Blind OS command injection vulnerabilities"
date: 2025-12-30
weight: 13
draft: false
description: "Blind OS command injection vulnerabilities"
---

# Lab 13: Blind OS command injection vulnerabilities

<div class="download-section">
    <a href="/iaw301_spring2026/downloads/lab13/Lab13 Blind OS command injection vulnerabilities.docx" class="download-btn" download>
        Download Lab Material
    </a>
</div>

## Objectives
- Understand Blind OS command injection
- Practice exploitation when there's no direct output
- Use out-of-band techniques

## Lab Content

### 1. Blind Command Injection
- Concepts and characteristics
- When blind command injection occurs
- Challenges in exploitation

### 2. Detection Techniques
- **Time-based detection**: Using sleep commands
- **DNS-based detection**: Triggering DNS lookups
- **HTTP-based detection**: Sending HTTP requests
- **File-based detection**: Creating files on server

### 3. Exploitation Techniques
- **Time delays**: `sleep`, `ping`, `timeout`
- **DNS exfiltration**: Using `nslookup`, `dig`
- **HTTP callbacks**: `curl`, `wget`
- **File operations**: Create, delete, modify files

### 4. Practice
- Detect blind command injection
- Use time-based techniques
- Implement DNS exfiltration
- Extract data via HTTP callbacks

### 5. Tools and Automation
- Burp Collaborator
- Custom scripts
- Automated scanners