# Monitor and Debug

## Some Example Monitoring Solutions
- Metrics server
- Prometheus
- Elastic Stack
- Datadog
- dynatrace

## Metric Server
- in memory monitoring server

- each node runs kubelet
  - each kubelet runs a cAdvisor

### activate minikube metrics-server
```bash
> minikube addons enable metrics-server
```

### activate metrics-server on other clusters
```bash
> git clone https://github.com/kubernetes-incubator/metrics-serve
kubectr create -f deploy/1.8+/
```

### get info
```bash
> kubectl top node 
```
