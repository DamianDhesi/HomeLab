a host will renew its DHCP lease once it is halfway through the lease time
- ex: for 24 hour lease, the host will request a lease renewal at 12 hours

## Force DHCP Renewal
### Windows
to release all dhcp leases
```
ipconfig /release
```

to renew all dhcp leases
```
ipconfig /renew
```

## iOS
turn wifi off for a few seconds and the turn it back on
- iphone should automatically requests a new dhcp lease from dhcp server, although that assigned ip may not change