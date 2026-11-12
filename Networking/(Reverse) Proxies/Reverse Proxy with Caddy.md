ex:
```
<domain> {
	tls /path/to/crt /path/to/key
	reverse_proxy <ip>:<port>
}
```
- don't need to specify tls section if using Caddy's own CA
	- can technically setup caddy to use a self-hosted CA, but I was not able to get it to work after a lot of trying and research
		- this works fine and all that is needed is to set up autorenewal yourself


if using automated cert renewal, it is good to check journalctl to see if Caddy properly grabbed certs on a fresh start
```
sudo journalctl -u caddy -f
```

certificate storage, by default, is at
```
/var/lib/caddy/.local/share/caddy/
```