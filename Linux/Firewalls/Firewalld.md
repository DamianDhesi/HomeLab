get active zones
```
sudo firewall-cmd --get-active-zones
```

can configure rich fire wall rules based on source and protocol
ex:
```
sudo firewall-cmd --permanent --add-rich-rule='rule family="ipv4" source address="10.0.0.0/24" service name="https" accept'
```
- all https ipv4 traffic from the 10.0.0.0/24 subnet is accepted through the firewall
- default is to deny all incoming traffic

apply changes by reloading
```
sudo firewall-cmd --reload
```
