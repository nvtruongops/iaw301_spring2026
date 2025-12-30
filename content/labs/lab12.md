---
title: "Lab 12 - OS command injection vulnerabilities"
date: 2025-12-30
weight: 12
draft: false
description: "Operating system command injection vulnerabilities"
---

# Lab 12: OS command injection vulnerabilities

## Objectives
- Understand OS command injection
- Practice exploiting command injection
- Apply prevention measures

## Lab Content

### 1. OS Command Injection
- Definition and causes
- Special characters in command injection
- Impact of vulnerabilities

### 2. Command Separators
- Unix/Linux: `;`, `&`, `&&`, `||`, `|`
- Windows: `&`, `&&`, `||`, `|`
- Newline characters: `\n`, `\r\n`

### 3. Exploitation Techniques
- **Basic command injection**: Basic command injection
- **Blind command injection**: Blind command injection
- **Out-of-band techniques**: Out-of-band techniques
- **Time-based detection**: Time-based detection

### 4. Practice
- Identify injection points
- Execute system commands
- Extract system information
- Establish reverse shells

### 5. Prevention Measures
- Input validation and sanitization
- Whitelist allowed commands
- Use safe APIs
- Principle of least privilege