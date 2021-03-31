# Helm
https://helm.sh/
https://artifacthub.io/

### What is Helm
- Package Manager for Kubernetes
- to package yaml files and distribute them in public and private repos



Example Project

Kubernets Cluster
- my-app pod
- my-app service
- elastic stack for logging

needs:
- stateful set
- ConfigMap
- Secret
- K8s User with permissions
- Services


### What is Helm Charts
- Bundle of YAML Files
- Create your own Helm Charts with Helm
- Push them to Helm Repository
- Download and use existing ones
- You can reuse configuration


### Commonly used Helm Charts
- Database Apps
  - MongoDB
  - MySQL
  - Elasticsearch
- Monitoring Apps
  - Prometheus

### Find Helm Charts with cli
```bash
> helm search <keyword>
```

### Find Helm Charts on Helm Hub
https://artifacthub.io/
https://helm.sh/docs/helm/helm_search_hub/

### Helm Chart Private Repositories


# Second Feature: Templating Engine
Usecase:
 - Deployment and Service Configs almost the same
 - version and name differ

 - create common blue prints for all microservices
 - dynamic values are replaced by placeholders

 ## Templating Engine Example

 - Template YAML config
 ```yaml
 apiVersion: v1
 kind: Pod
 metadata:
   name: {{ .Values.name }}
spec:
   containers:
   - name: {{ .Values.container.name }}
     image: {{ .Values.container.image }}
     port: {{ .Values.container.port}}
 ```
- Value are in values.yaml
 ```yaml
name: my-app
container:
  name: my-app-container
  image: my-app-image
  port: 9001
 ```

 Values can also be defined with --set flag

 ### CI/CD Pipelines

 In your build you can replace the values on the fly

 ### Same Apps accross different environments
 Imagine Microservice cluster on DevStageProd

- instead of deploying the individual yamls on each cluster
- package them up to make your own application chart
- use chart to deploy in different environments
- can also make the whole deployment process easier

