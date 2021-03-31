# Node Affinity


### Example equivalent to Node Selector Example

```yaml
apiVersion: v1
kind: Pod
metadata:
  name: myapp-pod
spec:
  containers:
  - name: data-processor
    image: data-processor
  
  affinity:
    nodeAffinity:
      requiredDuringSchedulingIgnoredDuringExecution:
        nodeSelectorTerms:
        - matchExpressions:
          - key: size
            operator: In
            values:
            - Large
```


### Not in
```yaml
- matchExpressions:
  - key: size
    operator: NotIn
    values:
    - Small
```

### Not in
```yaml
- matchExpressions:
  - key: size
    operator: NotIn
    values:
    - Small
```

### Exists
```yaml
- matchExpressions:
  - key: size
    operator: Exists
```

# Type of no Infinity
Available:
- requiredDuringSchedulingIgnoredDuringExecution
- prefferedDuringSchedulingIgnoredDuringExecution
Planned:
- requiredDuringSchedulingRequiredDuringExecution