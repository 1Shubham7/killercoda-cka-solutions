```

k get po my-pod-cka  -o yaml > p.yaml

vim p.yaml

---
spec:
  containers:
  - image: nginx
    imagePullPolicy: Always
    name: nginx-container
    resources: {}
    terminationMessagePath: /dev/termination-log
    terminationMessagePolicy: File
    volumeMounts:
    - mountPath: /var/www/html
      name: shared-storage
    - mountPath: /var/run/secrets/kubernetes.io/serviceaccount
      name: kube-api-access-9nfrf
      readOnly: true
  - name: sidecar-container
    image: busybox
    command: ["sh", "-c", "tail -f /dev/null"]
    volumeMounts:
    - mountPath: /var/www/shared
      name: shared-storage
      readOnly: true
---

 k apply -f p.yaml --force
```
