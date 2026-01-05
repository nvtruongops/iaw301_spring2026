---
title: "Lab 4 - Authentication Vulnerabilities (multi-factor authentication)"
date: 2025-12-30
weight: 4
draft: false
description: "Multi-factor authentication vulnerabilities"
toc: true
---

# Lab 4: Authentication Vulnerabilities (multi-factor authentication)

<div class="download-section">
    <a href="/iaw301_spring2026/downloads/lab4/Lab4 Authentication-Vulnerabilities (multi-factor authentication).docx" class="download-btn" download>
        Download Lab Material
    </a>
    <a href="/iaw301_spring2026/downloads/lab4/solution.pdf" class="download-btn" download>
        Download My Solution
    </a>
</div>

---

## Objective

Exploit vulnerabilities in multi-factor authentication mechanisms to bypass 2FA protection.

---

## Lab 4a: 2FA simple bypass

Bypass 2FA by directly navigating to the authenticated page after login.

**Steps:**
1. Login with your own credentials: `wiener / peter`.
2. Complete 2FA verification, note the post-login URL is `/my-account`.
3. Logout and login with victim credentials: `carlos / montoya`.
4. When prompted for the 2FA code, do not enter it. Instead, manually change the URL in the browser address bar to `/my-account`.
5. Successfully bypassed 2FA and accessed carlos's account (Force Browsing).

**Vulnerability:** The application fails to verify 2FA completion before granting access to the specific account page.

---

## Lab 4b: 2FA broken logic

Exploit flawed 2FA verification logic and session handling to access another user's account without their password.

**Steps:**
1. Login with `wiener / peter`, observe the 2FA process requests.
2. Identify that the `verify` parameter in the cookie determines which user is being verified.
3. **Trigger Code:** Send a `GET /login2` request via Burp Repeater with the cookie modified to `verify=carlos` to generate a 2FA code for the victim.
4. **Brute-force:** Configure Burp Intruder (or Turbo Intruder) to attack the `mfa-code` parameter while maintaining the `verify=carlos` cookie.
5. Identify the valid code (e.g., `0847`) by looking for a **302 Found** status code.
6. **Session Hijacking:** Extract the valid `session` cookie from the successful Intruder response.
7. Manually inject this new session cookie into the browser's Developer Tools to bypass the login prompt and access Carlos's account.

**Vulnerability:** The 2FA mechanism relies on client-side cookies for user identification and fails to bind the verification code to the original browser session properly.

---

## Key Takeaways

- **Server-side Validation:** Always verify 2FA completion server-side before rendering protected pages.
- **Session Binding:** Bind 2FA verification steps tightly to the authenticated session; do not rely on manipulatable cookies for identity.
- **Rate Limiting:** Implement strict rate limiting on 2FA code entry to prevent brute-force attacks.
- **Session Integrity:** Ensure session tokens are rotated and validated correctly upon successful 2FA completion.

---

## References

- [PortSwigger - Multi-factor Authentication](https://portswigger.net/web-security/authentication/multi-factor)