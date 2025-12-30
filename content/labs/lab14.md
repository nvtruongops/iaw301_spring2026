---
title: "Lab 14 - Cross-site scripting - Reflected"
date: 2025-12-30
draft: false
description: "Reflected Cross-site scripting vulnerabilities"
---

# Lab 14: Cross-site scripting - Reflected

## Objectives
- Understand Reflected XSS
- Practice exploiting reflected XSS
- Bypass XSS protection measures

## Lab Content

### 1. Reflected XSS
- Definition and characteristics
- How reflected XSS works
- Impact and risks

### 2. Common Injection Points
- URL parameters
- Form inputs
- HTTP headers
- Search functionality

### 3. Exploitation Techniques
- **Basic XSS payloads**: Basic payloads
- **Context-aware payloads**: Context-specific payloads
- **Filter bypass techniques**: Bypassing filters
- **Encoding techniques**: Encoding techniques

### 4. XSS Payloads
```javascript
<script>alert('XSS')</script>
<img src=x onerror=alert('XSS')>
<svg onload=alert('XSS')>
javascript:alert('XSS')
```

### 5. Practice
- Identify reflected XSS vulnerabilities
- Craft effective payloads
- Bypass XSS filters
- Steal cookies and session tokens

### 6. Prevention Measures
- Input validation
- Output encoding
- Content Security Policy (CSP)
- HttpOnly cookies