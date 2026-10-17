can run services at a user's permission level
```
systemctl --user
```

if using "sudo su - username" then it is important to set the environment variables for the DBUS in the user's .bashrc profile or else using systemctl --user will not work

in user's .bashrc
```
export XDG_RUNTIME_DIR="/run/user/$(id -u)"
export DBUS_SESSION_BUS_ADDRESS="unix:path=${XDG_RUNTIME_DIR}/bus"
```
