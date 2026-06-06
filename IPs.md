ips reserved for homelab: .1 - .30
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
- JellyFin Server

192.168.1.12
- Debian 13.4
- Testout filesharing (SMB, etc.)

192.168.1.13
- Debian 13.4
- Splunk Enterprise Security with 10GB dev license

192.168.1.14
- Kali Rolling (2026.2)
- Pentesting VM

192.168.1.15
- Debian 13 generic cloud
- Technitium DNS/DHCP server (Main)

192.168.1.16
- Debian 13 generic cloud
- Technitium DNS/DHCP server (Secondary)

192.168.1.17
- Debian 13 generic cloud
- Step-CA Certificate Authority 

## Planned
- set up internal cert authority with step ca?
	- tls cert for communication with servers
	- ssh cert make administration with ansible more secure
		- can have a short lived ssh cert compared to "infinite life" of ssh private key
- Look into setting up [Ansible](https://docs.ansible.com/) for easier update management
- Set up internal domain so domain names can be assigned to hosts
- Reverse proxy with [nginx](https://nginx.org/)
- VPN server using [wireguard](https://www.wireguard.com/)
	- would have to forward port
	- would be good to limit open ports/connections (using iptables and such)
		- outbound to proxy
		- outbound to dns server (for proxy to do anything)
		- inbound from management pc
		- outbound to internet
- self hosted Single Sign On (SSO) with [Authentik](https://goauthentik.io/)?
