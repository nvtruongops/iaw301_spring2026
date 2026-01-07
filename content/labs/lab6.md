---
title: "Lab 6 - Access control vulnerabilities - IDOR"
date: 2026-01-07
weight: 6
draft: false
description: "Insecure Direct Object References vulnerabilities exploitation"
toc: true
---

# Lab 6: Access control vulnerabilities - IDOR

<div class="download-section">
    <a href="/iaw301_spring2026/downloads/lab6/Lab6 Access control vulnerabilities - IDOR.docx" class="download-btn" download>
        Download Lab Material
    </a>
    <a href="/iaw301_spring2026/downloads/lab6/solution.pdf" class="download-btn" download>
        Download My Solution
    </a>
</div>

---

## Objective

We will explore the concept of Insecure Direct Object References (IDOR), understand how it poses a significant security threat to web applications, and solve the lab by finding the password for the user `carlos`.

---

## Part 1: Theoretical Questions

### Question 1: What is IDOR?

**Definition:** IDOR occurs when an application provides direct access to objects based on user-supplied input.

**Security Risk:**
* Attackers can bypass authorization mechanisms.
* Access resources directly by modifying parameters pointing to an object.
* Leads to unauthorized access to sensitive data (files, DB records, user accounts).

---

### Question 2: Exploitation Techniques

Attackers exploit IDOR by observing parameters in requests (URL, headers, body) and modifying them.

| Technique | Description |
|---|---|
| **Number Incrementing** | If ID is sequential (e.g., `id=100`), attackers increment/decrement to access adjacent records. |
| **Filename Guessing** | Predicting filenames if they follow a pattern (e.g., timestamps, sequential logs). |
| **Parameter Pollution** | Supplying multiple parameters to confuse the application's validation logic. |

---

### Question 3: Affected Areas

IDOR vulnerabilities typically impact the following areas of a web application:

| Category | Examples |
|---|---|
| **Affected Data** | PII, private messages, financial records, medical records, internal system files. |
| **Affected Functionality** | Viewing order details, downloading invoices/transcripts, account management, changing passwords. |

---

## Part 2: Lab Challenge Walkthrough

**Scenario:** The lab stores user chat logs directly on the server's file system using static URLs.
**Goal:** Find the password for user `carlos`.

### Step 1: Analysis & Traffic Capture
* Accessed the "Live Chat" feature and sent a message "Hello" to the bot Hal Pline.
* Clicked **View transcript** and analyzed the request in Burp Suite.
* **Observation:** The application requests a static URL: `/download-transcript/2.txt`.
* **Insight:** Files are stored using an incrementing numeric filename.

### Step 2: Verification
* Downloaded `2.txt` and confirmed it matched the current session's content.

### Step 3: Exploitation
* Hypothesis: A file named `1.txt` exists and belongs to a previous session/user.
* **Action:** Modified the URL path from `/2.txt` to `/download-transcript/1.txt`.

### Step 4: Retrieving Sensitive Data
* The server returned `1.txt`.
* **Result:** The file contained a chat log where the user explicitly stated their password.

> **Stolen Credentials found in 1.txt:**
> * **User:** `carlos`
> * **Password:** `32viwe531feo1b29m3je`

### Step 5: Completion
* Navigated to **My Account**.
* Logged in using the stolen credentials for `carlos`.
* The lab was marked as **Solved**.

---

## Conclusion

This lab demonstrated how predictable resource naming conventions (sequential filenames), combined with a lack of authorization checks on direct object references, allowed for the vertical escalation of privilege to extract sensitive credentials.

---

## References

- [PortSwigger Web Security Academy](https://portswigger.net/web-security)