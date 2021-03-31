# Cloud Services

- Google Kubernetes Engine (GKE)
- Azure Kubernetes Service (AKS)
- Amazon Elastic Kubernetes Service (EKS)

# AWS

 - install aws cli
 - create iam role with EKS Cluster preset
 - create aws access key
 ```
 aws --version
 aws configure
 ```

- find aws cluster region and cluster name
 ```
 aws --region <region> describe-cluster --name <name> --query cluster.status
 ```


- configure kubectl with eks api server credential
```
aws eks --region <region> update-kubeconfig --name <cluster>
aws eks --region eu-central-1 update-kubeconfig --name first-cluster
```
