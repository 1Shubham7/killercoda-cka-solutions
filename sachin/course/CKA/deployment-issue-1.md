```

k get pod


k get cm


k edit deploy nginx-deployment

---
initContainers:
      - command:
        - sh
        - -c
        - echo 'Welcome To KillerCoda!'
...

volumes:
      - configMap:
          defaultMode: 420
          name: nginx-configmap
        name: nginx-config
---


k delete po nginx-deployment-5bf48dd9b5-g5754 nginx-deployment-74dbdb77f8-46w6g

```
