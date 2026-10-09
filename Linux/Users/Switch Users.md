as a user with sudo permissions can use the su command to switch users

create a new shell and login as root
```
su -
```

create a new shell and login as a user
```
su - <username>
```

can switch to a different user without a login shell by using
```
su <username>
```
could cause PATH/permission related issues though as that information will be carried over from the previous session before using su

[further options](https://www.geeksforgeeks.org/linux-unix/switch-users-on-linux-with-the-su-command/)
- run command as a user
- etc.