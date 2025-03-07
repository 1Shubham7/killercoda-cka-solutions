```
 k create sa app-account

k create role app-role-cka --resource=pods --verb=get -n default

k create rolebinding app-role-binding-cka -n default  --role=app-role-cka --serviceaccount=default:app-account
```
