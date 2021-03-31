# Namespaces
- default namespace ist default
- system namespace ist kube-system

### Get Namespaces
```
kubectl get ns
```


### Create Namespace
```
create namespace dev -o yaml --dry-run=client > namespace-dev.yaml
```


### View pods of namespace
```
kubectl get pods --namespace=kube-system
```

### Create pod in specific namespace
```
kubectl create -f pod-definition.yml --namespace=dev
```


### Define Namespace in yaml
- add `namespace: <namespace>` to metadata tag

### switch namespace
just reset context and add namespace definition
```
kubectl config set-context $(kubectl config current-context) --namespace=dev
```

# Resource Quota
- To limit resources to a namespace, create a resource quota
- create ResourceQuota Yaml and create it
```
kubectl create -f compute-quota.yaml
```