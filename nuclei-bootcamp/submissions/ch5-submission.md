Submission Format

Challenge ID: CH5  
Target URL: http://172.16.13.89:9005  
Finding Summary: Session management vulnerability - application accepts and maintains pre-set session cookies without proper regeneration after authentication  
Detection Method: Nuclei template sets attacker-controlled session cookie before authentication and verifies it persists, detecting session fixation via lack of Set-Cookie header regeneration  
Template File: ch5-session.yaml

Vulnerability Confirmed:YES  
Nuclei Output: 3 matches found on /login and /dashboard endpoints  
- [ch5-session-fixation] [http] [high] http://172.16.13.89:9005/login  
- [ch5-session-fixation] [http] [high] http://172.16.13.89:9005/dashboard

Impact: Attacker can fixate victim's session ID before authentication, then hijack authenticated session after victim logs in
