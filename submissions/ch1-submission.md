Submission Format

Challenge ID: CH1  
Target URL: http://127.0.0.1:8001  
Finding Summary: Authentication bypass vulnerability allows login without password by sending only username parameter, returns "internal-access" token  
Detection Method: Nuclei template sends POST request to /login with {"username":"admin"} and detects "internal-access" token in 200 response  
Template File: ch1-auth.yaml

Vulnerability Confirmed: YES   
Nuclei Output: [ch1-auth-bypass] [http] [high] http://127.0.0.1:8001/login ["internal-access"]
