# Lab 02: SQL Injection - Login Bypass

## Lab Description
This lab contains a SQL injection vulnerability in the login functionality.

## Objective
To bypass authentication and login as the administrator.

## Vulnerability
Login page vulnerable to SQL injection at username field.

## Payload Used
## Steps to Reproduce
1. Go to login page /login
2. Intercept request with Burp Suite
3. In username field, inject payload `administrator'--`
4. Leave password blank or any random password
5. Forward request - logged in as administrator
6. Lab solved

## Impact
Authentication bypass, unauthorized admin access.

## Mitigation
Use parameterized queries / prepared statements. Avoid string concatenation in SQL.

## Evidence
- Burp-evidence.png: Shows SQL payload in login request
- Solved.png: Shows successful admin login

## Tools Used
- Burp Suite
- PortSwigger Web Security Academy
