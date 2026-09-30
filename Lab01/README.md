# Lab 01: SQL Injection - Retrieve Hidden Data

**Vulnerability:** SQL Injection (OWASP Top 10 - A03:2021 Injection)
**Severity:** High
**Lab:** PortSwigger Web Security Academy
**Tool:** Burp Suite Community Edition

### Vulnerable Endpoint
`/filter?category=`

### Payload Used
Gifts' OR 1=1--+

### Description
The category filter parameter was vulnerable to SQL injection. By injecting payload, I bypassed filter and retrieved hidden data.

### Steps to Reproduce
1. Opened lab in Burp browser (Intercept OFF)
2. Injected payload in category parameter
3. All products disclosed - lab solved

### Impact
- Unauthorized data disclosure
- Full database compromise possible

### Remediation
Use parameterized queries / prepared statements

### Proof
- solved.png
- burp-evidence.png
