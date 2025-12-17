Submission Format

Challenge ID: CH7  
Target URL: http://172.16.13.89:9021  
Finding Summary: Multiple security control absences - missing security headers (X-Frame-Options, X-Content-Type-Options, HSTS) and unauthenticated access to sensitive endpoints  
Detection Method: Nuclei template tests for missing security headers using DSL matchers and checks unauthenticated access to /admin and /api/sensitive endpoints  
Template File: ch7-absence.yaml

Vulnerability Confirmed:YES   
Nuclei Output: 3 matches found  
- [ch7-security-absence] [http] [medium] http://172.16.13.89:9021/admin  
- [ch7-security-absence] [http] [medium] http://172.16.13.89:9021/api/sensitive  
- [ch7-security-absence] [http] [medium] http://172.16.13.89:9021

Impact:Missing security headers expose application to clickjacking, MIME-sniffing attacks; unauthenticated endpoints allow unauthorized data access
