import requests
from bs4 import BeautifulSoup
from colorama import Fore

def check_clickjacking(url):
    print(Fore.CYAN + "[+] Checking for Clickjacking...")
    headers = requests.get(url).headers
    if 'X-Frame-Options' not in headers:
        print(Fore.RED + "[-] Vulnerable to Clickjacking!")
    else:
        print(Fore.GREEN + "[+] X-Frame-Options is set!")

def check_directory_listing(url):
    print(Fore.CYAN + "[+] Checking for Directory Listing...")
    common_paths = ["/admin", "/backup", "/.git", "/config", "/uploads"]
    for path in common_paths:
        full_url = url + path
        response = requests.get(full_url)
        if "Index of" in response.text or response.status_code == 200:
            print(Fore.RED + f"[-] Possible directory listing at {full_url}")
        else:
            print(Fore.GREEN + f"[+] {full_url} looks safe.")

def main():
    target = input("Enter target URL (e.g., https://example.com): ")
    check_clickjacking(target)
    check_directory_listing(target)

if __name__ == "__main__":
    main()
# Simple Web Vulnerability Scanner 🔍

A basic Python-based web vulnerability scanner that checks for:

- Clickjacking
- Directory listing
- Missing security headers

## 🚀 How to Run

1. Clone the repo:
```bash
git clone https://github.com/yourusername/web-vulnerability-scanner.git
cd web-vulnerability-scanner


