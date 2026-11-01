patch yaml
```
talosctl machineconfig patch <input>.yaml --patch @<patch_yaml> --output <output>.yaml
```

validate patch
```
talosctl validate --config <patchec>.yaml --mode metal
```

apply patch (to node in mainteance mode)
```
talosctl apply-config --insecure --nodes <node_ip> --file <patch>.yaml
```
- can add --dry-run to do a test of applying the patch
