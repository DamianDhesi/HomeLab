root cert is at /roots.pem
intermediate cert is at /intermediates.pem

need to make sure dns configuration for CA includes server ip (ex: 10.0.0.2) or else it will not be possible to generate certificates on another host (TLS will fail)

[running step-ca as a daemon](https://smallstep.com/docs/step-ca/certificate-authority-server-production/)

## Packing p12
can use [step certificate p12](https://smallstep.com/docs/step-cli/reference/certificate/p12/)
- need intermediate and root certs for the p12 cert to have the correct expiration date, issuer, and such