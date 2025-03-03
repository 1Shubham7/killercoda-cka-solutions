```
kubectl config use-context kubernetes-admin@kubernetes

kubectl rollout undo deployment/redis-deployment

k describe deploy redis-deployment

echo "redis:7.0.13" > rolling-back-image.txt

k scale deploy redis-deployment  --replicas=3
```
