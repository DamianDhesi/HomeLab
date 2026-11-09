**ips reserved for homelab: .1 - .30**
## Hosts
192.168.1.1
- Proxmox Backup Server
- Proxmox Backup Server 4.2
- Lenovo thinkpad x201

192.168.1.2
- Proxmox node
- Proxmox 9.1
- Dell Latitude 5430 rugged
- pm-latitude

192.168.1.3
- Proxmox node
- Proxmox 9.1
- Lenovo Thinkpad P16s
- pm-lenovo

192.168.1.4
- Proxmox node
- Proxmox 9.1
- Dell Latitude 7420
- pm-dell

## VMs
192.168.1.11
- Windows 11
- [JellyFin Server](https://jellyfin.org/)

192.168.1.12
- Debian 13
- Stack

192.168.1.13
- Debian 13
- [Splunk Enterprise Security](https://www.splunk.com/en_us/products/enterprise-security.html) with 10GB dev license

192.168.1.14
- Kali Rolling (2026.2)
- Pentesting VM

192.168.1.15
- Debian 13 generic cloud
- [Technitium DNS/DHCP server](https://technitium.com/dns/) (Main)

192.168.1.16
- Debian 13 generic cloud
- [Technitium DNS/DHCP server](https://technitium.com/dns/) (Secondary)

192.168.1.17
- Debian 13 generic cloud
- [Step-CA Certificate Authority](https://smallstep.com/docs/step-ca/)

192.168.1.18
- RHEL 10 x86_64
- [Caddy build (using xcaddy)](https://caddy.community/t/how-to-use-dns-provider-modules-in-caddy-2/8148) with [cloudflare dns module](https://github.com/caddy-dns/cloudflare)
	- Wildcard cert for \*.internal.ddhesi.com with automated renewals through DNS-01 challenge

192.168.1.19
- Debian 13 generic cloud
- [Uptime Kuma](https://uptimekuma.co/)

192.168.1.20
- Debian 13 generic cloud
- [PriceBuddy](https://pricebuddy.jez.me/) docker

192.168.1.21
- ~~Debian 13 generic cloud~~
- ~~[GoPhish](https://getgophish.com/)~~

192.168.1.22
- Debian 13 generic cloud
- [Invidious](https://invidious.io/)

192.168.1.23
- Talos amd64
- [K8s control plane](https://www.siderolabs.com/talos-linux)

192.168.1.24
- ~~Talos amd64~~
- ~~[K8s worker](https://www.siderolabs.com/talos-linux)~~
