Nuclei Flag Finder

Install Nuclei (Go must be installed):

```powershell
go install -v github.com/projectdiscovery/nuclei/v2/cmd/nuclei@latest
# ensure $GOPATH/bin or $GOBIN is in PATH
```

Scan local targets listed in `../targets/local.txt` with the template:

```powershell
nuclei -t templates/find-flags.yaml -l targets/local.txt -o nuclei-flags.txt
```

Notes:
- The template hits common endpoints (`/`, `/login`, `/download?file=flag.txt`, `/api/orders/1`, `/init`, `/advance`, `/commit`) and extracts typical flag patterns such as `FLAG{...}` or `FLAG-xxxxx`.
- Run the apps locally first (the sample apps in `apps/` listen on ports 8001,8002,8003,9020) so the scanner can reach them.
