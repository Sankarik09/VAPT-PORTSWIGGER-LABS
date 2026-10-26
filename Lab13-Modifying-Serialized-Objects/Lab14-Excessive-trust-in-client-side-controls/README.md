# Lab14: Excessive trust in client-side controls

**Lab Link:** https://portswigger.net/web-security/logic-flaws/examples/lab-logic-flaws-flawed-business-logic
**Category:** Business logic vulnerabilities > Flawed business logic
**Difficulty:** Apprentice

## Description
Shop la `Lightweight "l33t" leather jacket` price $1337. Store credit $100 than irukku. Logic flaw use panni cheap ah vaanganum.

## Vulnerability
**Excessive trust in client-side controls (Price Tampering)**
- Server client anupura `price` parameter ah blind ah trust panuthu
- CWE-472 / CWE-807
- OWASP A04:2021

## Steps to Reproduce

1. Login with `wiener:peter`
2. Burp Proxy -> Intercept ON
3. Add `Lightweight "l33t" leather jacket` to cart
4. Intercepted request:
   ```http
   POST /cart
   productId=1&quantity=1&price=1337.00

   
