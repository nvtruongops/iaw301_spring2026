---
title: "Lab 11 - Blind SQL injection - Error-based SQL Injection"
date: 2025-12-30
weight: 11
draft: false
description: "Error-based blind SQL injection"
---

# Lab 11: Blind SQL injection - Error-based SQL Injection

<div class="download-section">
    <a href="/iaw301_spring2026/downloads/lab11/Lab11 Blind SQL injection - Error SQL Injection.docx" class="download-btn" download>
        Download Lab Material
    </a>
</div>

## Objectives
- Understand Error-based Blind SQL injection
- Exploit through error messages
- Extract data from database errors

## Lab Content

### 1. Error-based SQL Injection
- Concepts and principles
- Types of database errors
- Information leakage through errors

### 2. Exploitation Techniques
- **Triggering database errors**: Triggering database errors
- **Extracting data via errors**: Extracting data via errors
- **Conditional errors**: Conditional errors
- **Verbose error exploitation**: Verbose error exploitation

### 3. Error Functions
- MySQL: `ExtractValue()`, `UpdateXML()`
- PostgreSQL: `CAST()` errors
- SQL Server: `CONVERT()` errors
- Oracle: `UTL_INADDR.GET_HOST_NAME()`

### 4. Practice
- Identify error-based injection points
- Extract database schema via errors
- Retrieve sensitive data
- Bypass error filtering