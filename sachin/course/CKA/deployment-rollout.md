vim d.yaml:

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  creationTimestamp: null
  labels:
    app: cache
  name: cache-deployment
spec:
  replicas: 2
  selector:
    matchLabels:
      app: cache
  strategy: {}
  template:
    metadata:
      creationTimestamp: null
      labels:
        app: cache
    spec:
      containers:
      - image: redis:7.0.13
        name: redis
  strategy:
   type: RollingUpdate
   rollingUpdate:
     maxUnavailable: 30%
     maxSurge: 45%
status: {}
```

`k apply -f d.yaml`

`k set image deploy/cache-deployment redis=redis:7.2.1`

```
controlplane $ kubectl rollout history deployment/cache-deployment
deployment.apps/cache-deployment 
REVISION  CHANGE-CAUSE
1         <none>
2         <none>
```

`echo "2" > /root/total-revision.txt`
