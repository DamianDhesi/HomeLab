```
chown <user>:<group> <file>
```
ex:
```
chown fred:bestgroup testing.txt
```

can do a recursive 
```
chown -R <user>:<group> <directory>
```


user and group do not have to exist to chown files to them 
- can be useful for setting up files for a not yet created user
- restricting the file permissions of services without creating a new user
- etc.

