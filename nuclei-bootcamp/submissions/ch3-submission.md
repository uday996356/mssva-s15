Submission Format

Challenge ID: CH3  
Target URL: http://127.0.0.1:8003  
Finding Summary: Broken Object Level Authorization (BOLA/IDOR) allows accessing any user's order data with any token value  
Detection Method: Nuclei template sends requests to /api/orders/1 and /api/orders/2 with arbitrary Authorization header, successfully retrieves other users' data  
Template File: ch3-api.yaml

Vulnerability Confirmed:YES   
Nuclei Output: [ch3-broken-access-control] [http] [high] http://127.0.0.1:8003/api/orders/2 ["mohit","phone"]
