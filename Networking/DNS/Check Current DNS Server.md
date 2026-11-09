nslookup gives the dns server being used and its answer for a given domain
```
PS C:\> nslookup google.com
Server:  dns-main.dslab.internal
Address:  192.168.1.15

Non-authoritative answer:
Name:    google.com
Addresses:  2607:f8b0:4005:816::200e
          142.251.219.1
```
- if its not the authoritative server for that domain, it will signal it as such
	- will just give name and address of domain if authoritative