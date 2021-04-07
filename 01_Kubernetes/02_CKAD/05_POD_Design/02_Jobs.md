# Jobs

Replicaset -> Always run a certain amount of processes
Job -> Get a certain amount of processess done


## Example Job
```yaml
apiVersion: batch/v1
kind: Job
metadata:
  name: math-add-job
spec:
  template:
    spec:
      containers:
        - name: math-add
          image: ubuntu
          command: ['expr', '3', '+', '2']
      restartPolicy: Never
```
### Start and Check Result
```bash
> kubectl create -f jobs1.yaml
> kubectl get jobs
> kubectl get pods
> kubectl logs math-add-job-smnmh
> kubectl delete job math-add-job
```
Deleting the job will also result in deleting the pod


### Multiple Pods
## Example Job
```yaml
apiVersion: batch/v1
kind: Job
metadata:
  name: random-error-job
spec:
  completions: 3
  template:
    spec:
      containers:
        - name: random-error
          image: kodekloud/random-error
      restartPolicy: Never
```
The standard behaviour is sequenzel. Repeats one after another until three finished with exit code 0

### Parallelism

```yaml
apiVersion: batch/v1
kind: Job
metadata:
  name: random-error-job
spec:
  completions: 3
  parallelism: 3
  template:
    spec:
      containers:
        - name: random-error
          image: kodekloud/random-error
      restartPolicy: Never
```

### BackoffLimit

```yaml
apiVersion: batch/v1
kind: Job
metadata:
  name: random-error-job
spec:
  completions: 3
  parallelism: 3
  backoffLimit: 25
  template:
    spec:
      containers:
        - name: random-error
          image: kodekloud/random-error
      restartPolicy: Never
```