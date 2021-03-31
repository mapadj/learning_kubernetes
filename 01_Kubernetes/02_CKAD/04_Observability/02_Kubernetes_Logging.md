# Logging

### with one container in a pod
```bash
> kubectl logs -f <pod-name>
> kubectl logs -f event-simulator-pod
```

### with more than one container in a pod
```bash
> kubectl logs -f <pod-name> <container-name>
> kubectl logs -f event-simulator-pod event-simulator
```