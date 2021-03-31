# Docker

### Run Image from docker hub and exit immediately
```
docker run ubuntu
```

### watch running containers
```
docker ps
```

### watch all containers including those which are stopped
- ubuntu is in an exited state
- 
```
docker ps -a
```

### Containers

- Container are not meant to run an operating system
- Container are meant to run a specific task or process
- unlike virtual machine
- once task done, container exits
- container lives as long as process runs
- if process stops or crashed, container exits
