Windows will typically use the first/most recently refreshed DNS entry from DHCP (v6 or v4)
- This can lead to situations with dns servers tied to DHCP v6 being used first over DHCP v4 servers
	- Can break dns if the dns servers from ipv4 DHCP are different from the ipv6 ones

best solution
- Make sure only the desired servers are advertised on DHCP v4/v6 and disable DHCP from everything esle (DNS/DHCP servers, ISP routers, etc. )

if an undesired DNS server already took precedent due to DHCP (v6 or v4)
- disable the DHCP causing the issue

flush stale entries
```
ipconfig /release
ipconfig /renew
Restart-netAdapter -Name "<affected_interface_name"
ipconfig /flushdns
```
- can do /release6, /renew6 to release and renew only ipv6
