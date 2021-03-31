

# Service Accounts

Accounts:
- User -> Admin, Developer
- Service  -> Prometheus, Jenkins



### Create service Account
```bash
> kubectl create serviceaccount dashboard-sa
```


### View service Account
```bash
> kubectl get serviceaccount
```
- there is a default service account
- each namespace has its own service account
- whenever a pod is created, a default service account and its token are automatically mounted as volumes

### Describe
```bash
> kubectl describe serviceaccount <service-account-name>
```

creating service account automatically creates token

### Describe secret token
```bash
> kubectl describe secret <service-account-name>-token-kbbdm
```


```bash
> kubectl exec -it my-kubernetes-dashboard ls /var/run/secrets/kubernetes.io/serviceaccount
ca.crt  namespace   token
```

```bash
> kubectl exec -it my-kubernetes-dashboard cat /var/run/secrets/kubernetes.io/serviceaccount/token
AxMKbWluaWt1YmVDQTCCASIwDQYJKoZIhvcNAQEBBQADggEPADCCAQoCggEBAKrX
PoIcyQzLGiMEfRt8mOaFmfXWHNikF+K3rEY6B3TL92//2rO8X9s1QQYRL7kIlNMP
WDU03H6wduh2Xgf1Bmsoj5FamfuQF00jfBVWnnH3d02RKjtQL9RZd6H6mf+13Qgz
1r/47o8WDvWV6z6xrGlwejQs/QXMVSmUbA1+L9No/eMWvJrG77HXbh7sdoQ7oCyj
u8/ENnZa4S+Bbwyka/Q7M7dXcrTt8DJ/ZLBK9iXAc+1ZBF5mffZfQw8kq8bxkbmY
dRjI6UQouj6ezIYQDPEUo4nKCd34X52bYsFa4aRJZDeN1kGPhV0PaDPZXp57uRxg
WN5mD3FlOi1Og3nYKx0CAwEAAaNhMF8wDgYDVR0PAQH/BAQDAgKkMB0GA1UdJQQW
MBQGCCsGAQUFBwMCBggrBgEFBQcDATAPBgNVHRMBAf8EBTADAQH/MB0GA1UdDgQW
BBQH5xACd/iPjQpJQrMJslpjKaYLzzANBgkqhkiG9w0BAQsFAAOCAQEAlLfELVEk
YTSwkTxzpx6s6Xc48IOUnARJ9EN0ksZ30mobi7+oHlWsKoZi3sD7PB19QHTvBX2R
```



### Specify Service Account in pod

```yaml
apiVersion: v1
kind: Pod
metadata:
  name: my-kubernetes-dashboard
spec:
  containers:
    - name: my-kubernetes-dashboard
      image: my-kubernetes-dashboard
  serviceAccount: dashboard-sa
```

- you cannot edit a service account of an existing pod
  - u must delete, edit and recreate the pod

- you can edit deployment, because it retriggers deployment.


### Deactivate AutomountServiceAccountToken

```yaml
apiVersion: v1
kind: Pod
metadata:
  name: my-kubernetes-dashboard
spec:
  containers:
    - name: my-kubernetes-dashboard
      image: my-kubernetes-dashboard
  automountServiceAccountToken: false
```