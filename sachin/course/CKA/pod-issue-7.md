```
vim application-deployment.yaml

---
apiVersion: v1
kind: Pod
metadata:
  name: redis-pod
spec:
  containers:
    - name: redis-container
      image: redis:latest
      ports:
        - containerPort: 6379
  tolerations:
  - key: "nodeName"
    operator: "Equal"
    value: "workerNode01"
    effect: "NoSchedule"
---

k apply -f application-deployment.yaml 

```
