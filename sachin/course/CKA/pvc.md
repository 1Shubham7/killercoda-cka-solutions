```

vim pvc.yaml

---
apiVersion: v1
kind: PersistentVolumeClaim
metadata:
  name: red-pvc-cka
spec:
  accessModes:
    - ReadWriteOnce
  volumeMode: Filesystem
  resources:
    requests:
      storage: 30Mi
  storageClassName: manual
---

k apply -f pvc.yaml
```
