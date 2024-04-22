# Kubernetes rails example app

## Notes

### Create docker image
```
$ eval $(minikube docker-env) # To be able to use the locally built image later
$ docker build -t kubernetes-rails-example:latest .
```

To run image localy and expose rails app at `localhost:3000`:
```
$ docker run -p 3000:3000 kubernetes-rails-example:latest
```

### Start Minikube
```
$ minikube start
```
Check that kubectl can connect to the cluster:
```
$ kubectl version
$ kubectl cluster-info
```

### Create the Kubernetes Objects
```
$ kubectl create -f .k8s/secrets.yaml
$ kubectl create -f .k8s/deployment.yaml
$ kubectl create -f .k8s/service.yaml
```

### Check if pods are running
```
$ kubectl get secrets,deployments,pods,services
```


### Open app in browser
```
$ minikube service kubernetes-rails-example-service
```
