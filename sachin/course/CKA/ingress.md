```
vim i.yaml

---
apiVersion: networking.k8s.io/v1
kind: Ingress
metadata:
  name: nginx-ingress-resource
  annotations:
    nginx.ingress.kubernetes.io/rewrite-target: /
    nginx.ingress.kubernetes.io/ssl-redirect: "false"
spec:
  rules:
  - http:
      paths:
      - path: /shop
        pathType: Prefix
        backend:
          service:
            name: nginx-service
            port:
              number: 80

---

k apply -f i.yaml 
```
