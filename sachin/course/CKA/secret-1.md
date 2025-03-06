```

k get secret -n database-ns database-data  -o yaml
apiVersion: v1
data:
  DB_PASSWORD: c2VjcmV0
kind: Secret
metadata:
  creationTimestamp: "2025-03-06T06:00:35Z"
  name: database-data
  namespace: database-ns
  resourceVersion: "2618"
  uid: f80e1941-023a-4b08-86f1-f538212ab416
type: Opaque

echo c2VjcmV0 | base64 -d

echo secret > decoded.txt

```
