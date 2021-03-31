# Readiness And Liveness Probes

## POD Status

- Pending
- ContainerCreating
- Running

## POD Conditions
boolean array
- PodScheduled
- Initialized
- ContainerReady
- Ready

## Readiness Probe

```yaml
spec:
  containers:
  - name: app
    ports:
      - containerPort: 8080
    readinessProbe:
      httpGet:
        path: /api/ready
        port: 8080
```

### http
```yaml
readinessProbe:
  httpGet:
    path: /api/ready
    port: 8080
```

### tcp
```yaml
readinessProbe:
  tcpSocket:
    port: 3306
```

### cmd
```yaml
readinessProbe:
  ecec:
    command:
      - cat
      - /app/is_ready
```

### initial delay, frequency, fail threshhold
```yaml
readinessProbe:
  httpGet:
    path: /api/ready
    port:
  initialDelaySeconds: 10
  periodSeconds: 5
  failureThreshold: 3
```

# Liveness Probe
test periodically if service is still responsive

### http
```yaml
livenessProbe:
  httpGet:
    path: /api/healthy
    port: 8080
```

### tcp
```yaml
livenessProbe:
  tcpSocket:
    port: 3306
```

### cmd
```yaml
livenessProbe:
  ecec:
    command:
      - cat
      - /app/is_healthy
```

### delay, frequency, threshold
```yaml
initialDelaySeconds: 10
periodSeconds: 5
failureThreshold: 3
```

