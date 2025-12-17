Submission Format

Challenge ID: CH6  
Target URL: http://127.0.0.1:9020  
Finding Summary: State machine bypass allows accessing extended data by skipping /advance step - calling /init then /commit directly reveals {"mode":"extended","ops":3}  
Detection Method: Nuclei template performs /init to create session, then immediately calls /commit (bypassing /advance), detecting "extended", "mode", "ops" in response  
Template File: ch6-state.yaml

Vulnerability Confirmed:YES   
Nuclei Output: [ch6-state-desync] [http] [medium] http://127.0.0.1:9020/commit
