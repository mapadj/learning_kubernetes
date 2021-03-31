# Multi Container Pods

## When?
- Sometimes you need one service and another work together
- They share the same lifecycle and local network
- created together and destroyed together

## Different Patterns
- Ambassador
- Adapter
- Sidecar

### SideCar
logging agents, sending to central log server

### Adapter
before sending to logserver, we convert logs using an adapter

### Ambassador 
If you have different stages (Dev/Test/Prod), you can refer database to a local container, that proxies to different setups

## Where?
- Containers section under spec is an array.

## Examples

### SideCar Pattern
```yaml
apiVersion: v1
kind: Pod
metadata:
  name: simple-webapp
  labels: simple-webapp
spec:
  containers:
  - name: simple-webapp
    image: simple-webapp
    ports:
      - containerPort: 8080
  - name: log-agent
    image: log-agent

```