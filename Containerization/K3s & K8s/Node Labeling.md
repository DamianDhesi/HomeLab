show all node labels
```
kubectl get nodes --show-labels
```

add label to node
```
kubectl label nodes <node_name> <key>=<value>
```

remove label
```
kubectl label nodes <node_name> <key>-
```