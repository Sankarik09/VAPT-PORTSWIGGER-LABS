# Lab06 - Broken Access Control - Unprotected Admin Functionality

## Bug: Admin panel /administrator-panel has no authentication check

### How I Found:
1. Checked /robots.txt -> Found Disallow: /administrator-panel
2. Directly accessed /administrator-panel -> Opened without login!
3. Deleted user carlos -> Lab Solved

### Impact: Attacker can access admin panel and delete any user/data

### Proof:
![Robots.txt](Lab06-Robots.png)
![Admin Panel](Lab06-Admin-Panel.png)
![Solved](Lab06-Solved.png)

### Fix: Add login check + Role-based access control for admin paths
