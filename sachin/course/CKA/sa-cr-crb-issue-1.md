```
k auth can-i  list service --as prod-sa

k edit role prod-role-cka

k edit role prod-role-cka

---
resources:
  - services
  verbs:
  - create
  - list
  - get
---
```
