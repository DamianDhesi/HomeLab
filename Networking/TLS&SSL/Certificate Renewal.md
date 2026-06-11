[TLS cert lifetimes will be reduced to a max of 47 days by 2029](https://www.digicert.com/blog/tls-certificate-lifetimes-will-officially-reduce-to-47-days)
- will need to move towards automation of cert renewal
	- ACME clients like Certbot are a decent choice at smaller scale and step-ca has its own renewal system via "step ca renew" which can be run regularly as a daemon through systemd
- lower times is good for security reasons
	- if attacker compromises a tls/ssl cert then it can only be abused for a shorter time frame
	- passive revocation (disallowing renewal of the certificate is more effective with shorter times)
	- only problem is cert renewal automation becomes necessary, especially at shorter times like the 24 hour expiration time default of step-ca, however, that can be problematic with older/proprietary systems that make cert renewal harder 