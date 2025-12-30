---
title: "Lab 10 - Blind SQL injection - Time-based SQL Injection"
date: 2025-12-30
draft: false
description: "Time-based blind SQL injection"
---

# Lab 10: Blind SQL injection - Time-based SQL Injection

## Objectives
- Understand Time-based Blind SQL injection
- Practice exploitation using time delays
- Extract data when there's no direct output

## Lab Content

### 1. Time-based Blind SQL Injection
- Concepts and characteristics
- When to use time-based techniques
- Time delay functions in various DBMS

### 2. Exploitation Techniques
- **Confirming vulnerability**: Confirming vulnerability
- **Conditional time delays**: Conditional delays
- **Data extraction**: Bit-by-bit data extraction
- **Automated exploitation**: Automated exploitation

### 3. Time Delay Functions
- MySQL: `SLEEP()`, `BENCHMARK()`
- PostgreSQL: `pg_sleep()`
- SQL Server: `WAITFOR DELAY`
- Oracle: `DBMS_PIPE.RECEIVE_MESSAGE()`

### 4. Practice
- Detect time-based SQL injection
- Extract database version
- Retrieve user data bit by bit
- Automate with tools