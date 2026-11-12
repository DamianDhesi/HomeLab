Can be useful to use wildcard certs for HTTPS TLS/SSL certs as the cert applies to all sub domains
- \*.example.com cert will apply to one.example.com and two.example.com
- one.example.com cert will work for one.example.com but that cert can't be used for two.example.com
Also a minor benefit that the sub domains associated with the wildcard cert are obscured. Certificate transparency logs will show that you [posses a wildcard cert but there is no information given on the sub domains](https://ctlogs.io/search?q=internal.ddhesi.com&mode=certs) you have using that cert, so it will be (somewhat) harder to be attacked

## Automating Wildcard Cert Renewal
Only possible with the [DNS-01 challenge](https://letsencrypt.org/docs/challenge-types/#dns-01-challenge) where your webserver/proxy writes a TXT record to your domain that is confirmed by the cert authority
- Also nice since you do not need to expose ports 80 or 443, so it works well for exclusively internal services

Will require getting an API key from your domain registrar in order for your service to edit DNS records
- in the case of Cloudflare the required permissions are
	- write permissions to DNS records
	- read permissions to Zone information

