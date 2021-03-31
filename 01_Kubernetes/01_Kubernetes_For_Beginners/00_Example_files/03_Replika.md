### Replikation Controller
- helps us to replicate pods to have fail safety

- Replication Controller and Replica Set
  - Replica Set is the new Replication Controller

# Replication Controller

### Create Replikation Controller as yaml
rc-definition.yml

### Start RC
```
kubectl create -f rc-definition.yml
```

### View RC
```
kubectl get rc
kubectl get replicationcontrollers
kubectl describe rc <name>
```


### Delete Rc
```
kubectl delete rc <name>
kubectl delete replicationcontroller <name>
```


# Replicaset

### Create a Replica Set as yaml
replicaset-definition.yml

### start RS
```
kubectl create -f replicaset-definition.yml
```

### view rs
```
kubectl get rs
kubectl get replicasets
kubectl describe rs <name>
```

### replace rs
```
kubectl replace -f replicaset-definition.yml
```

### delete rs
```
kubectl delete rs <name>
kubectl delete replicaset <name>
```



# Scale
## Scale Running Replica Set by changing yml
- change yaml file
- replace yaml file with
```
kubectl replace -f replicaset-definition.yml
```

## Scale Running ReplicaSet by using scale command
- the scale method does not update the yml file. It only changes the running set.
```
kubectl scale --replicas 6 -f replicaset-definition.yml
kubectl scale --replicas 6 replicaset myapp-replicaset
```

