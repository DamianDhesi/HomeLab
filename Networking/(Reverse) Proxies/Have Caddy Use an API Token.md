create a file with the token
ex:
```
CLOUDFLARE_API_TOKEN=YOUR_CLOUDFLARE_API_TOKEN
```

give it permissions such that root can edit the token file but the caddy process can only read it
```
sudo chown root:caddy cloudflare.env
sudo chmod 640 cloudflare.env
```

edit caddy systemd service to add the token to the environment
```
sudo systemctl edit caddy
```
add
```
[Service]
EnvironmentFile=/path/to/cloudflare.env
```

reload the daemon
```
sudo systemctl daemon-reload
```

can now configure the Caddyfile to to use the token environment variable
```
tls {
    dns cloudflare {env.CLOUDFLARE_API_TOKEN}
    resolvers 1.1.1.1 1.0.0.1
}
```
- the Caddyfile should have 640 permissions with root:caddy ownership to ensure that the caddy service can read the file but only root and edit it
