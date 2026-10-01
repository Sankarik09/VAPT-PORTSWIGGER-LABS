# Lab04 - Stored XSS into HTML context with nothing encoded

## Objective
Exploit Stored XSS vulnerability where comment is stored without encoding.

## Lab Link
PortSwigger - Stored XSS into HTML context with nothing encoded

## Steps to Exploit
1. Opened any blog post
2. Went to comment section
3. Entered payload in Comment field: `<script>alert(document.domain)</script>`
4. Filled Name and Email
5. Clicked Post Comment
6. Clicked Back to Blog and reopened post
7. Alert triggered and lab solved

## Payload Used
<script>alert(document.domain)</script>

## Proof of Concept

### 1. Lab Solved
![Solved](StoredXSS-solved.png)

### 2. Alert Popup
![Alert](StoredXSS-alert.png)

## Impact
Attacker can steal user cookies and hijack sessions.

## Mitigation
- HTML Encode output
- Sanitize user input
- Implement CSP
