```
k create deploy my-web-app-deployment --image=wordpress --replicas=2


k expose deploy my-web-app-deployment  --name=my-web-app-service --type=NodePort --port=80 --dry-run=client -o yaml > s.yaml


vim s.yaml


---
apiVersion: v1
kind: Service
metadata:
  creationTimestamp: null
  labels:
    app: my-web-app-deployment
  name: my-web-app-service
spec:
  ports:
  - port: 80
    protocol: TCP
    targetPort: 80
    nodePort: 30770
  selector:
    app: my-web-app-deployment
  type: NodePort
status:
  loadBalancer: {}
---


k apply -f s.yaml

curl 172.30.2.2:30770
```
