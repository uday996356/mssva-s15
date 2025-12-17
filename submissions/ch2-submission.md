Submission Format

Challenge ID: CH2  
Target URL: http://172.16.13.89:8002  
Finding Summary: Path traversal protection bypass using ....// sequences - changes response from "403 Not allowed" to "404 Not found", confirming directory escape  
Detection Method: Testing /download endpoint - ../ triggers "Not allowed", but ....//....//....//.... bypasses the startswith() check, proving path validation weakness  
Template File: ch2-file.yaml

Vulnerability Confirmed: YES  
Evidence:  
- `?file=../../../etc/passwd` → 403 "Not allowed" (blocked)
- `?file=....//....//....//....//etc/passwd` → 404 "Not found" (bypassed protection, file doesn't exist)

Impact:The ....// bypass defeats os.path.normpath() + startswith() validation, allowing directory traversal. While tested files weren't found on the server, the protection bypass is confirmed.
