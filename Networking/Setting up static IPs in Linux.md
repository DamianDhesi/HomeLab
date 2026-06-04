ip Older distros use /etc/network/interfaces for handling interfaces 
- In order to set up static ip, need to 
	- bring up the desired NIC (network interface card)
	- set it to take a static ip
	- provide the static ip and default gateway (usually the router ip)

ex:
```
auto lo
iface lo inet loopback

auto nic0
iface nico inet static
	address 10.10.10.10
	gateway 10.10.10.254
```
- brings up the lo interface as the loopback (127.0.0.1)
- brings up the nic0 interface as a static ip with 10.10.10.10 as its ip and 10.10.10.254 as its gateway
- **important that this ip is not used for any other interfaces on the host or else networking will not work**

after changing /etc/network/interfaces the networking service will need to be restarted for 
## Static IP on Proxmox with ethernet adapter
default vmbr0 bridge interface created by proxmox needs to be set as the master of the ethernet adapter interface to connect proxmox host to network

```
iface <adapter_name> inet manual

auto vmbr0
iface vmbr0 inet static
	address 10.10.10.10
	gateway 10.10.10.254
	bridge-ports <adapter_name>
	bridge-stp off
	bridge-fd 0
```

if need, creating the vmbr0 bridge can be down with
```
ip link add name vmbr0 type bridge
```
and confirm with
```
ip link show
```

## Static IP with netplan
some distros may have netplan instead and thus not have /etc/network/interfaces 

netplan config files are in /etc/netplan as .yaml

can set a static ip using format from this example on [netplan docs](https://netplan.readthedocs.io/en/stable/using-static-ip-addresses/)
```
network:
  version: 2
  ethernets:
    enp6s0:
      dhcp4: false
      dhcp6: false
      accept-ra: false
      link-local: []
      addresses:
        - 172.16.0.1/24
      routes:
        - to: default
          via: 172.16.0.254
      nameservers:
        search:
          - netplanlab.local
        addresses:
          - 172.16.0.254
          - 172.16.0.253
```
- use "netplan get" to get configuration
- "netplan apply" to apply new netplan configuration