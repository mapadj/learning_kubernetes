# Deployments

## commands
```
kubectl get all

kubectl get deployments
kubectl rollout status deployment/<name>
kubectl rollout history deployment/<name>
```


## Strategies
- There are two type of strategies
  - Strategy 1 -> Recreate Strategy -> Bad:
    - Destroy all instances
    - Create newer versions of instances
  - Strategy 2 -> Rolling Update -> Good and Default Update Strategy
    - Destroy not all instances at once
    - instead take down and recreate new version one by one
    - this way application never goes down -> integration seemless

## How do you update your deployment
### update version of image in deployment-definition.yml
- update yaml
- kubectl apply
```
kubectl apply -f deployment-definition.yml
```

### set image command
```
kubectl set image deployment/myapp-deployment \
    nginx=nginx:1.9.1
```

## Rollback Deployment 
```
kubectl rollout undo deployment/myapp-deployment
```