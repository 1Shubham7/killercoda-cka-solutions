```
k get netpol allow-green-and-blue -o yaml > n.yaml

vim n.yaml

---
apiVersion: networking.k8s.io/v1
kind: NetworkPolicy
metadata:
  annotations:
    kubectl.kubernetes.io/last-applied-configuration: |
      {"apiVersion":"networking.k8s.io/v1","kind":"NetworkPolicy","metadata":{"annotations":{},"name":"allow-green-and-blue","namespace":"default"},"spec":{"ingress":[{"from":[{"podSelector":{"matchLabels":{"run":"green-pod"}}},{"podSelector":{"matchLabels":{"run":"blue-pod"}}}]}],"podSelector":{"matchLabels":{"run":"red-pod"}},"policyTypes":["Ingress"]}}
  creationTimestamp: "2025-03-07T02:28:53Z"
  generation: 1
  name: allow-green-and-blue
  namespace: default
  resourceVersion: "4520"
  uid: 577455fb-f4ae-4c8d-b5ef-b55a432b94c5
spec:
  ingress:
  - from:
    - podSelector:
        matchLabels:
          run: green-pod
  podSelector:
    matchLabels:
      run: red-pod
  policyTypes:
  - Ingress
---


```
