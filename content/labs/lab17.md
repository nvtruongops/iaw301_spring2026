---
title: "Lab 17 - Race conditions vulnerabilities"
date: 2025-12-30
weight: 17
draft: false
description: "Race conditions vulnerabilities"
---

# Lab 17: Race conditions vulnerabilities

## Objectives
- Understand race condition vulnerabilities
- Practice exploiting race conditions
- Identify and prevent race conditions

## Lab Content

### 1. Race Conditions
- Definition and causes
- Time-of-check to time-of-use (TOCTOU)
- Concurrent processing issues

### 2. Common Scenarios
- **Payment processing**: Payment processing
- **Account creation**: Account creation
- **File operations**: File operations
- **Resource allocation**: Resource allocation
- **Coupon redemption**: Coupon redemption

### 3. Exploitation Techniques
- **Concurrent requests**: Sending concurrent requests
- **Timing attacks**: Timing attacks
- **Thread synchronization issues**: Thread synchronization issues
- **Database transaction races**: Database transaction races

### 4. Tools and Techniques
- Burp Suite Intruder
- Custom scripts with threading
- Automated race condition testing
- Network delay manipulation

### 5. Practice
- Identify race condition vulnerabilities
- Exploit payment race conditions
- Bypass rate limiting
- Multiple account creation

### 6. Prevention Measures
- Proper locking mechanisms
- Atomic operations
- Database transactions
- Input validation and rate limiting