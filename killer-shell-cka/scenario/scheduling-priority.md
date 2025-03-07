```
k get po -n management -o yaml  | grep -i priority
    preemptionPolicy: PreemptLowerPriority
    priority: 200000000
    priorityClassName: level2
    preemptionPolicy: PreemptLowerPriority
    priority: 300000000
    priorityClassName: level3


# higher number is higher priority 

k delete pod -n management sprinter 
```
