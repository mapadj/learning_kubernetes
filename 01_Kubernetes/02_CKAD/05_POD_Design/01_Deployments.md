# Deployments

## Commands


### Record History
```bash
> kubectl create -f deployment-definition.yml --record=true
> kubectl apply -f deployment-definition.yml --record=true
> kubectl set image deployment/myapp-deployment nginx-container=nginx:1.12-perl
```

### Rollout status
```bash
> kubectl rollout status deployment/myapp-deployment
```

###


### History
```bash
> kubectl rollout history deployment/my-app-deployment
```

### Delete
```bash
> kubectl delete deployment my-app-deployment
```

### Describe Deployments
```bash
> kubectl describe deployments
```

### Rollback
```bash
> kubectl rollout undo deployment/myapp-deployment
```
If you check history, you will notice, that the last revision command disappears and gets a new revision number.