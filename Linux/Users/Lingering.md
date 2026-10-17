Can set user to lingering state with sudo/root perms which treats them as being logged in/active
```
sudo loginctl enable-linger <user>
```

can check if lingering enabled and user state
```
loginctl list-users
```