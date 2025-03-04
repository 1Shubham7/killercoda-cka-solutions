```
k get po -o wide

k describe node controlplane | grep -i taints

k edit daemonset cache-daemonset

---
tolerations:
      - key: "node-role.kubernetes.io/control-plane"
        operator: "Exists"
        effect: "NoSchedule"
---

k get po
```
