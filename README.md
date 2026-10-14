# Week 8: Advanced VAPT – Attack Chain & Full Exploitation Project

**Cyber Security Intern @ DG Interns Hub**

## Project Overview

This project demonstrates an advanced Vulnerability Assessment and Penetration Testing (VAPT) exercise on OWASP Juice Shop, an intentionally vulnerable web application running in a local, isolated lab environment.

The objective was to identify multiple logic-based vulnerabilities and demonstrate how they can be chained together to create a greater security impact.

## Target & Tools

- **Target:** OWASP Juice Shop
- **Testing Environment:** Local Docker lab (`localhost:3000`)
- **Tools:** Burp Suite Community Edition, Firefox
- **Testing Approach:** Manual, logic-driven security testing

## Vulnerabilities Identified

1. **SQL Injection** — Authentication bypass.
2. **Broken Access Control** — Unauthorized access to the administration panel.
3. **IDOR (Insecure Direct Object Reference)** — Access to other users' records and baskets.
4. **Parameter Tampering** — Acceptance of invalid and negative basket quantities.
5. **Weak Session Management** — Session token remained usable after logout.

## Attack Chain

The assessment explored how individual weaknesses could combine into a larger security incident:

- Step 1: Authentication bypass through SQL injection.
- Step 2: Access to the administration interface.
- Step 3: Access to user records and baskets through object IDs.
- Step 4: Manipulation of basket quantities.
- Step 5: Testing session-token reuse after logout.

## Risk & Impact Analysis

The findings demonstrated potential risks including unauthorized account access, exposure of customer information, manipulation of order data, and continued access through an uninvalidated session token.

Severity ratings were assigned according to the potential impact and exploitability observed in the lab.

## Remediation

- Use parameterized queries to prevent SQL injection.
- Enforce server-side authorization on administrative routes.
- Verify object ownership on every API request.
- Validate basket quantities on the server.
- Invalidate session tokens securely during logout.

## Key Learnings

- Multiple vulnerabilities can combine into a serious attack chain.
- Hidden routes do not replace proper access control.
- Server-side validation is essential.
- Session management must include effective token invalidation.
- Manual, logic-driven testing can reveal issues that basic scanning may miss.

## Disclaimer

This project was conducted for educational purposes in an authorized, isolated OWASP Juice Shop lab. All testing was limited to the intentionally vulnerable training environment.

## Submission

Prepared as part of **Week 8: Advanced VAPT** for **DG Interns Hub**.
