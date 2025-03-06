```
vim np.yaml

---
spec:
    egress:
    - to:
      - namespaceSelector:
          matchLabels:
            kubernetes.io/metadata.name: level-1000
        podSelector:
          matchLabels:
            level: 100x
    - to:
      - namespaceSelector:
          matchLabels:
            kubernetes.io/metadata.name: level-1001
        podSelector:
          matchLabels:
            level: 100x
    - to:
      - namespaceSelector:
          matchLabels:
            kubernetes.io/metadata.name: level-1002
        podSelector:
          matchLabels:
            level: 100x
---

```
