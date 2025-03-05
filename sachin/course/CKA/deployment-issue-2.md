```
k apply -f frontend-deployment.yaml 
Error from server (NotFound): error when creating "frontend-deployment.yaml": namespaces "nginx-ns" not found

 k create ns nginx-ns

k apply -f frontend-deployment.yaml 
```
