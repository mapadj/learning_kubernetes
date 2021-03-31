# Node Selectors


### Example

```yaml
apiVersion: v1
kind: Pod
metadata:
  name: myapp-pod
spec:
  containers:
  - name: data-processor
    image: data-processor
  
  nodeSelector:
    size: Large
```

- size is a label on the node

### Label the nodes
```bash
kubectl label nodes <node-name> <label-key>=<label-value>
kubectl label nodes node-1 size=Large
```

- if pod is now created, it will be launched on node-1


# Node Selector Limitations

- U cannot distinguish complex stuff like threshold or OR statements
- for this we use Node Affinity
