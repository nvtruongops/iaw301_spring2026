---
title: "Lab 18 - Path traversal vulnerabilities"
date: 2025-12-30
weight: 18
draft: false
description: "Path traversal vulnerabilities"
---

# Lab 18: Path traversal vulnerabilities

## Objectives
- Understand path traversal vulnerabilities
- Practice exploiting directory traversal
- Bypass protection measures

## Lab Content

### 1. Path Traversal
- Definition and principles
- Directory traversal attacks
- File inclusion vulnerabilities

### 2. Common Payloads
- `../../../etc/passwd` (Linux)
- `..\..\..\windows\system32\drivers\etc\hosts` (Windows)
- URL encoded: `%2e%2e%2f`
- Double URL encoded: `%252e%252e%252f`

### 3. Bypass Techniques
- **Encoding techniques**: URL encoding
- **Null byte injection**: `%00`
- **Nested traversal**: `....//`
- **Absolute paths**: `/etc/passwd`
- **UNC paths**: `\\server\share\file`

### 4. File Types to Target
- Configuration files: `/etc/passwd`, `web.config`
- Log files: `/var/log/apache/access.log`
- Application files: `config.php`, `database.xml`
- System files: `/proc/version`, `/etc/hosts`

### 5. Practice
- Identify path traversal vulnerabilities
- Access sensitive system files
- Bypass input filters
- Extract configuration data

### 6. Prevention Measures
- Input validation and sanitization
- Whitelist allowed files
- Chroot jails
- Principle of least privilege