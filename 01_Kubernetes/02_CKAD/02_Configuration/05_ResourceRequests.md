# Resource Requests
https://kubernetes.io/docs/tasks/configure-pod-container/assign-memory-resource
### Example:
```yaml
apiVersion: v1
kind: Pod
metadata:
  name: simple-webapp-color
  labels: 
    name: simple-webapp-color
spec:
  containers:
  - name: simple-webapp-color
    image: simple-webapp-color
    ports:
      - containerPort: 8080
    resources:
      requests:
        memory: "1Gi"
        cpu: 1
      limits:
        memory: "2Gi"
        cpu: 2

```


### Default CPU RANGE
https://kubernetes.io/docs/tasks/administer-cluster/manage-resources/cpu-default-namespace/
```yaml
apiVersion: v1
kind: LimitRange
metadata:
  name: cpu-limit-range
spec:
  limits:
  - default:
      cpu: 1
    defaultRequest:
      cpu: 0.5
    type: Container
```

### Default MEM LIMIT RANGE
https://kubernetes.io/docs/tasks/administer-cluster/manage-resources/memory-default-namespace/
```yaml
apiVersion: v1
kind: LimitRange
metadata:
  name: mem-limit-range
spec:
  limits:
  - default:
      memory: 512Mi
    defaultRequest:
      memory: 256Mi
    type: Container
```