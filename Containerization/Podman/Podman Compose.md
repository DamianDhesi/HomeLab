wrapper around docker-compose or community made podman-compose

can do all the usual docker-compose commands

ex:
pull updated images
```
podman compose pull
```

bring up new docker images
```
podman compose up -d
```

remove all unused images
```
podman image prune -af
```

## Restarting on reboot
can set containers to restart on reboot through docker-compose.yml by adding restart defintion
```
image:...
restart: always
```

than then bring up container stack
```
podman compose up -d
```

and enable and start the podman restart service with 
```
systemctl --user enable --now podman-restart.service
```