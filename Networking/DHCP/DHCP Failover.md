good idea to have a second server set up for DHCP
- ideally able to set ip up such that if the primary DHCP server goes down, then the secondary DHCP server will be enabled

## Hacky Method
not always possible to set up a secondary DHCP server to be enabled only when the primary server goes down. So it will be necessary to run two DHCP servers at once
- in order to prevent the different DHCP servers from leasing the same ip to different devices, it is important to give the secondary DHCP servers a significant delay on sending the DHCP lease offer/responding to DHCP request
	- will ensure that the primary DHCP server, if up, will only serve leases as clients will only accept the first DHCP offer received which will be from the primary as it doesn't have any added delay set
	- can set the delay as low as 200-300ms but up to 2000-4000ms is better to ensure the secondary DHCP server never leases an ip while the primary is up

**This method is far from ideal, but it works** so it can be nice in homelab settings where its not as easy to set up server failover/run secondary DHCP servers