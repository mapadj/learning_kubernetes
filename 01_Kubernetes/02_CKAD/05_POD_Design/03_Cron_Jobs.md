# Cron Jobs

### The Time String
"* * * * * command to execute"
Stars in following order:
- minute (0-59)
- hour (0 - 23)
- day of the month (1 - 31)
- month (1 - 12)
- day of the week (0 - 6) (Sunday to Saturday; 7 is also Sunday on some systems)

### Job Template:
```yaml
apiVersion: batch/v1
kind: Job
metadata:
  name: reporting-job
spec:
  completions: 3
  parallelism: 3
  template:
    spec:
      containers:
        - name: reporting-tool
          image: reporting-tool
      restartPolicy: Never
```

### Cron Job Definition
```yaml
apiVersion: batch/v1beta1
kind: CronJob
metadata:
  name: reporting-cron-job
spec:
  scedule: "*/1 * * * *"
  jobTemplate:
  spec:
    completions: 3
    parallelism: 3
    template:
        spec:
            containers:
                - name: reporting-tool
                image: reporting-tool
            restartPolicy: Never
```