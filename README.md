# Example Distribution Simple War to Kubernetes

### Deploy resources to kubernetes

```bash
kubectl create -f deployment.yaml
```

### Capture node INTERNAL-IP running the command

```bash
kubectl get node -o wide
```

In our case, INTERNAL-IP is `192.168.99.100`

### Application should be [running](http://192.168.99.100:30800/SampleWebApp/)

## Example running in Docker

### Prepare docker image

```bash
docker image build -t ashumilov/sample-war ./
```

### Push image to dockerhub

```bash
docker push ashumilov/sample-war
```

### Test image running container

```bash
docker container run -it --publish 8081:8080 ashumilov/sample-war
```

### Application should be [running](http://localhost:8081/SampleWebApp)