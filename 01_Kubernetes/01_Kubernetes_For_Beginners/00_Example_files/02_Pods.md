# PODS
- pod is smallest unit in kubernetes
- each pod gets an internal ip address

### start an nginx container from docker hub
kubectl run nginx --image nginx

### get pods info
kubectl get pods
kubectl get pods -o wide
kubectl describe pod nginx



### Create a redis pod with wrong redis123 image from a yaml file
kubectl run redis --image=redis123 --dry-run=client -o yaml > pod.yaml
kubectl apply -f pod.yaml


### correct image name to redis
kubectl edit redis
-> opens vi, correct error, save file.
-> pod automatically restarts
kubectl get pods
