  Simple Web Vulnerability Scanner

A beginner-friendly Python tool that scans websites for common web security misconfigurations.

Created by [@dengrgb](https://github.com/dengrgb)

---

Features

-  Clickjacking detection (`X-Frame-Options`)
-   Common exposed directories check (`/admin`, `/uploads`, etc.)
-  Missing HTTP security headers check
-  Color-coded CLI output with `colorama`

---

 Requirements

Make sure Python is installed, then install dependencies:

```bash
pip install -r requirements.txt
requirements.txt content:



requests
How to Use
1 Clone the project:

bash
git clone https://github.com/dengrgb/web-vulnerability-scanner.git
cd web-vulnerability-scanner
2 Run the script
python scanner.py
3 When prompted, enter a full website URL (with http:// or https://):

Enter full URL (e.g., https://example.com): http://testphp.vulnweb.com
4 What It Checks
Check	Description
Clickjacking	Verifies if X-Frame-Options header is missing
 Security Headers	Looks for 4 important HTTP headers
 Directory Listing	Attempts to access common sensitive folders
Recommended Test Targets
Use one of these legally safe URLs:

http://testphp.vulnweb.com

http://demo.testfire.net
sample output
https://httpbin.org (for header testing)
=== Simple Web Vulnerability Scanner ===
Enter full URL (e.g., https://example.com): http://testphp.vulnweb.com

[+] Checking for Clickjacking...
[-] Vulnerable: X-Frame-Options not set!

[+] Checking for Missing Security Headers...
[-] Missing: Content-Security-Policy
[-] Missing: Strict-Transport-Security

[+] Checking for Directory Listing...
[!] Possible directory listing at http://testphp.vulnweb.com/admin
 Author
Deng Kuot
GitHub: @dengrgb
⚠️ Legal Disclaimer
This tool is for educational purposes only. Do not scan any website you don't own or have explicit permission to test.
 Support
If you find this useful, please ⭐ star the repo and follow @dengrgb on GitHub!










