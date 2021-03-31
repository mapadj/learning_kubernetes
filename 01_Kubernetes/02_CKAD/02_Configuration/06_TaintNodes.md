# Taint and Tolerations

### Format
```bash
> kubectl taint nodes <node-name> <key>=<value>:<taint-effect>
```

### Taint Effects
- NoSchedule
- PreferNoSchedule
- NoExecute

### Example imperativ
```bash
> kubectl taint nodes node1 app=blue:NoSchedule
```

### Example as yaml
```yaml
apiVersion: v1
kind: Pod
metadata:
  name: myapp-pod
spec:
  containers:
    - name: nginx-container
      image: nginx
  
  tolerations:
  - key: "app"
    operator: "Equal"
    value: "blue"
    effect: "NoSchedule"
```

### Check for Taints
```bash
> kubectl describe node controlplane | grep Taint
```

### Untaint
```bash
> kubectl taint nodes controlplane node-role.kubernetes.io/master:NoSchedule-
```

