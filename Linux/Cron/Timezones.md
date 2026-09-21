Cron runs based on the timezone of the host which is typically UTC 
- as most people are not in the UTC timezone and writing cron jobs based on a timezone your not in can rapidly get very confusing, it can be nice to change the timezone on your host

### Changing time zone
see current time zone
```
timedatectl
```

list available timezones
```
timedatectl list-timezones
```

can set the host timezone with 
```
timedatectl set-timezone <timezone>
```
which in my case is
```
timedatectl set-timezone America/Los_Angeles
```

can verify timezone change with 
```
timedatectl
```
which should show the local time as the time zone you set

restart cron so it uses new timezone
```
sudo service cron restart
```