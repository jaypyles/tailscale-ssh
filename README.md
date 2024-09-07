# tailscale-ssh

Github Action to connect runner to tailnet, ssh into a machine, run a command, and exit. Tailnet node cleaned up on exit.

Example usage:

```yaml
- name: Deploy
uses: jaypyles/tailscale-ssh@v1.0.0
with:
    ts-oauth-client-id: ${{ secrets.TS_OAUTH_CLIENT_ID }}
    ts-oauth-secret: ${{ secrets.TS_OAUTH_SECRET }}
    host: ${{ secrets.HOST }} # optional, default: 22
    username: ${{ secrets.USERNAME }}
    password: ${{ secrets.PASSWORD }}
    port: ${{ secrets.PORT }}
    script: ${{ secrets.DEPLOY_COMMAND }}
    tag: ${{ secrets.TAG }} # optional, default: ci
```

Must create a tag in your tailscale ACL file.
