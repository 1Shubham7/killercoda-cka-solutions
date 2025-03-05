```
 k describe pod postgres-deployment-75b4ffc554-x9wdr

 k get cm

k get secret

 k edit deploy postgres-deployment

---
- env:
        - name: POSTGRES_DB
          valueFrom:
            configMapKeyRef:
              key: POSTGRES_DB
              name: postgres-config
        - name: POSTGRES_USER
          valueFrom:
            configMapKeyRef:
              key: POSTGRES_USER
              name: postgres-config
        - name: POSTGRES_PASSWORD
          valueFrom:
            secretKeyRef:
              key: POSTGRES_PASSWORD
              name: postgres-secret
---

```
