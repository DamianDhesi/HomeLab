edit /etc/systemd/logind.conf and uncomment
```
#HandleLidSwitch=suspend
```
and change it to
```
HandleLidSwitch=ignore
```

then restart the service
```
systemctl restart systemd-logind
```
optionally check service status after 
```
systemctl status systemd-logind
```