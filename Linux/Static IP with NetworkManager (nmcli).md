check connection to set with static ip
```
nmcli connection show
```

configure static ip
```
sudo nmcli connection modify <connection_name> ipv4.method manual ipv4.addresses <ip_addr>/<prefix> ipv4.gateway <gateway_ip> ipv4.dns "<dns_ip_1>,<dns_ip_2>,..."
```

apply the changes
```
sudo nmcli connection up <connection_name>
```