```

vim sc.yaml

---
apiVersion: storage.k8s.io/v1
kind: StorageClass
metadata:
  name: green-stc
provisioner: kubernetes.io/no-provisioner
volumeBindingMode: WaitForFirstConsumer
allowVolumeExpansion: true
---

k apply -f sc.yaml
```
