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
- Splunk Enterprise with 10GB dev license

192.168.1.14
- Kali Rolling (2026.2)
- Pentesting VM

## Planned
- Recursive dns ([technitium](https://technitium.com/dns/))
	- maybe also set up dhcp through technitium
		- dhcp failover?
- Reverse proxy with [nginx](https://nginx.org/)
- VPN server using [wireguard](https://www.wireguard.com/)
	- would have to forward port
	- would be good to limit open ports/connections (using iptables and such)
		- outbound to proxy
		- outbound to dns server (for proxy to do anything)
		- inbound from management pc
		- outbound to internet
