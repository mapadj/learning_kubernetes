# Services

### Rules
- ports is an array
- u can have multiple portmappings within one service
- mapping pods to service via spec/selector for pod labels

### Start Service
```
kubectl create -f service-definition.yml
```
### View Services
```
kubectl get svc
kubectl get services
kubectl get services -o wide
```
### Access Service
- `kubectl get svc` -> ip:port
or
- `minikube service myapp-service --url`

```
kubectl expose deployment simple-webapp-deployment --name=webapp-service --target-port=8080 --type=NodePort --port=8080 --dry-run=client --nodeport=30080 -o yaml > svc.yaml
```


kubectl apply -f svc.yaml