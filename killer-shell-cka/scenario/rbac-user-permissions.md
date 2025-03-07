```
k create role -n applications  app-role --resource=pods --resource=deployments --resource=statefulsets --verb=create --verb=delete

 k create rolebinding -n applications app-rb --role=app-role --user=smoke

controlplane:~$ k auth can-i create deploy -n applications --as smoke
yes

k get ns                
NAME                 STATUS   AGE
applications         Active   5m37s
default              Active   23d
kube-node-lease      Active   23d
kube-public          Active   23d
kube-system          Active   23d
local-path-storage   Active   23d

k create rolebinding --clusterrole=view rb --user smoke -n applications
k create rolebinding --clusterrole=view rb --user smoke -n kube-public
k create rolebinding --clusterrole=view rb --user smoke -n kube-node-lease
k create rolebinding --clusterrole=view rb --user smoke -n default
k create rolebinding --clusterrole=view rb --user smoke -n local-path-storage 


```
