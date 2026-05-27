Debian based distros used /etc/network/interfaces for handling interfaces 
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
