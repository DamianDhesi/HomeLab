On certain distros (usually older) will have to edit /etc/resolv.conf to add dns servers when using static ip addresses

ex of /etc/resolv.conf
```
nameserver 10.0.0.1
nameserver 8.8.8.8
```

may need to update all interfaces by running
```
ifreload -a
```