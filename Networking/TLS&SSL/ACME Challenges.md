## HTTP-01
test by trying to retrieve a file on a port 80 webserver set up by the host ACME client
- can be redirected to port 443 but wont validate certs

## DNS-01
put a specific txt record under domain name to prove you own domain related to a cert
- allows for wildcard certs
- will query for the txt record on the DNS server and if it exists then cert is valid
	- would likely want control of the DNS server for this

## TLS-ALPN-01
performed on port 443 and uses ALPN protocol 
- allows validation through SNI field that matches the domain name being validated
- nice since it all happens with TLS but will need support for ALPN protocol 