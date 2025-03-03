```
k expose pod/nginx-pod --name=nginx-service

k port-forward service/nginx-service 80:80

curl localhost:80
```
