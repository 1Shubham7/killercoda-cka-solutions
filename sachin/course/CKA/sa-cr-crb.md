```
k edit clusterrole group1-role-cka   

---
apiVersion: rbac.authorization.k8s.io/v1
kind: ClusterRole
metadata:
  creationTimestamp: "2025-03-08T02:23:46Z"
  name: group1-role-cka
  resourceVersion: "3047"
  uid: b7f4e661-bd92-4848-bee0-bdd6119c3996
rules:
- apiGroups:
  - apps
  resources:
  - deployments
  verbs:
  - get
  - create
  - list
---


```
