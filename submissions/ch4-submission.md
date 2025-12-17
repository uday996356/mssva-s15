 Submission Format

Challenge ID: CH4  
Target URL: http://172.16.13.89:9004  
Finding Summary: Server-Side Request Forgery (SSRF) vulnerability on /fetch endpoint allows fetching arbitrary URLs including localhost and internal resources  
Detection Method: Nuclei template tests /fetch?url= parameter with external (example.com) and internal (127.0.0.1) URLs, both return 200 with HTML content  
Template File: ch4-ssrf.yaml

Vulnerability Confirmed:YES   
Nuclei Output:  
- [ch4-ssrf-detection] [http] [high] http://172.16.13.89:9004/fetch?url=http://example.com  
- [ch4-ssrf-detection] [http] [high] http://172.16.13.89:9004/fetch?url=http://127.0.0.1

Impact: Attacker can access internal services, scan internal network, and potentially retrieve sensitive data from metadata endpoints
