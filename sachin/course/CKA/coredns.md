```
 k create ns dns-ns

vim rs.yaml

---
apiVersion: apps/v1
kind: ReplicaSet
metadata:
  namespace: dns-ns
  name: dns-rs-cka
  labels:
    tier: cka
spec:
  replicas: 2
  selector:
    matchLabels:
      tier: frontend
  template:
    metadata:
      labels:
        tier: frontend
    spec:
      containers:
      - name: dns-container
        image: registry.k8s.io/e2e-test-images/jessie-dnsutils:1.3
        command:
        - sh
        - -c
        - sleep 3600
---

k exec -it dns-rs-cka-ftjks -n dns-ns -- nslookup kubernetes.default > dns-output.txt

```
