# SSH port forwarding

Sometimes, we want to access web services running locally on remote computer, then we will not this **SSH port forwarding**(Local forwarding).

```bash
ssh -L <port-forward-to>:localhost:<port-on-remote-pc> <remote>
# visit localhost:8080 for the service on remote pc, who is running on port 8000
ssh -L 8080:localhost:8000 proverbs@proverbs.top
```
