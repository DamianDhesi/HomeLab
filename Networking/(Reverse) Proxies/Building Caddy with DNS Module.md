(Done on RHEL 10.2)

requires git and golang 
```
sudo dnf install -y golang git
```

get latest version of xcaddy
```
go install github.com/caddyserver/xcaddy/cmd/xcaddy@latest
```

can verify xcaddy version
```
xcaddy version
```
may need to add go binary to directory path
```
export PATH="$PATH:$(go env GOPATH)/bin"
```


build the xcaddy file with the desired dns module (I used the cloudflare module as cloudflare is my domain registrar)
```
xcaddy build --with github.com/caddy-dns/cloudflare
```

change the existing binary
```
sudo systemctl stop caddy
sudo cp /usr/bin/caddy /usr/bin/caddy.standard
```
- good to keep regular binary as a backup
install custom build
```
sudo install -o root -g root -m 755 ./caddy /usr/bin/caddy
```
confirm module installed
```
caddy list-modules | grep cloudfalre
```