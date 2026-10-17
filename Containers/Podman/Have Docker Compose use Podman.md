## For Rootless
start rootless podman socket service
```
systemctl --user enable --now podman.socket
```

export DOCKER_HOST variable pointing to user's runtime directory
```
export DOCKER_HOST="unix://${XDG_RUNTIME_DIR}/podmanpodman.sock"
```
- good to add this to user .bashrc so it is set permanently 