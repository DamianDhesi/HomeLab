root cert is at /roots.pem
intermediate cert is at /intermediates.pem

need to make sure dns configuration for CA includes server ip (ex: 10.0.0.2) or else it will not be possible to generate certificates on another host (TLS will fail)

[running step-ca as a daemon](https://smallstep.com/docs/step-ca/certificate-authority-server-production/)

## Generate TLS/SSL Cert
```
step ca certificate <FQDN> <crt_file> <key_file>
```
can use 
```
--provisioner=acme
```
to use the default HTTP-01 authen with acme server

## Packing p12
can use [step certificate p12](https://smallstep.com/docs/step-cli/reference/certificate/p12/)
- need intermediate and root certs for the p12 cert to have the correct expiration date, issuer, and such

## [Cert Renewal](https://smallstep.com/docs/step-ca/renewal/#the-standalone-step-renewal-daemon)
will need to run
```
caddy reload --config /etc/caddy/Caddyfile --force
```
to force caddy to use newly renewed certs
