Talos does not have a storage provisioner by default, can verify with
```
kubectl get storageclass
```

will need to install a provisioner ([ex: rancher's local-path provisioner](https://docs.siderolabs.com/kubernetes-guides/csi/local-storage))
- best to create [user volumes](https://docs.siderolabs.com/talos/v1.13/configure-your-talos-cluster/storage-and-disk-management/disk-management/user) that the provisioner creates permanent volume claims from


