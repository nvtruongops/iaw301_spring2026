---
title: "Lab 8 - Access control vulnerabilities - OAuth2.0"
date: 2025-12-30
weight: 8
draft: false
description: "OAuth 2.0 vulnerabilities"
---

# Lab 8: Access control vulnerabilities - OAuth2.0

## Objectives
- Understand OAuth 2.0 and its vulnerabilities
- Practice exploiting OAuth flows
- Configure secure OAuth

## Lab Content

### 1. OAuth 2.0 Flows
- Authorization Code flow
- Implicit flow
- Client Credentials flow
- Resource Owner Password flow

### 2. OAuth Vulnerabilities
- **Authorization code interception**
- **CSRF attacks on OAuth flows**
- **Open redirect vulnerabilities**
- **Scope abuse**
- **State parameter bypass**

### 3. Practice
- Intercept authorization codes
- Exploit redirect_uri parameter
- CSRF attacks on OAuth
- Token hijacking

### 4. Protection Measures
- Proper redirect_uri validation
- State parameter implementation
- PKCE (Proof Key for Code Exchange)
- Secure token storage