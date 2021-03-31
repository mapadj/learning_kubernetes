### start minikube

minikube start --driver=hyperv
or
minikube start --driver=virtualbox

### delete minikube
if something failed, delete with
minikube delete

### check status
minikube status

kubectl get po -A

minicube dashboard


### check nodes
kubectl get nodes

### check nodes with additional info
kubectl get nodes -o wide

### Deploy applications
kubectl create deployment hello-minikube --image=k8s.gcr.io/echoserver:1.4
kubectl expose deployment hello-minikube --type=NodePort --port=8080

### check deployment
kubectl get deployments

### check service
kubectl get services hello-minikube

### get service url
minikube service hello-minikube --url

### lauch webbrowser pointing to service url
minikube service hello-minikube

### use kubectl to forward port
kubectl port-forward service/hello-minikube 7080:8080

### test service in webbrowser
http://localhost:7080/

### pause and stop
minikube pause
minikube stop



### increase memory
minikube config set memory 16384

### browse catalog of services
minikube addons list

### create second cluster running older kubernetes release
minikube start -p aged --kubernetes-version=v1.16.1

### delete all of the minikube clusters:
minikube delete -all



