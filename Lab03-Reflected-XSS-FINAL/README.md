# Lab 03 - Reflected XSS into HTML context with nothing encoded

**Platform:** PortSwigger Web Security Academy  
**Vulnerability:** Cross-Site Scripting (XSS) - Reflected  
**Severity:** High  

### Description
The application reflects user input from the search parameter directly into the HTML response without any encoding. This allows an attacker to inject malicious JavaScript.

### Steps to Reproduce
1. Accessed the lab.
2. Navigated to the search functionality: `/?search=test`
3. Tested for XSS with payload: `<script>alert(1)</script>`
4. Injected the payload into the `search` parameter.
5. The payload was reflected and executed in the browser.
6. Lab marked as solved.

### Payload Used
```html
<script>alert(document.domain)</script>
ImpactSession HijackingAccount TakeoverCredential Harvesting / PhishingWebsite DefacementMitigationOutput Encoding: HTML-encode all user-controlled data before reflecting it.Content Security Policy (CSP): Implement a strong CSP to prevent inline script execution.HttpOnly Flag: Set HttpOnly flag on cookies.Evidence1. Browser - Alert ExecutionPart of this response isn't supported on this device yet. View the full response on your phone.2. Burp Suite - RequestPart of this response isn't supported on this device yet. View the full response on your phone.3. Burp Suite - ResponsePart of this response isn't supported on this device yet. View the full response on your phone.Tools UsedBurp Suite ProfessionalWeb BrowserStatus: Solved ✅javascript
**How to update:**
1. Open `Lab03-Reflected-XSS-FINAL/README.md`
2. Click Edit (pencil icon)
3. Select all (Ctrl + A) and delete
4. Paste this new code
5. Commit changes
