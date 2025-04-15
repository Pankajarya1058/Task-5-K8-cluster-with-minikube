## Task-5-K8-cluster-with-minikube

In this repo, I have created kubernetes cluster with minikube and then create deployment for nginx and accessing from browser.
Following are the steps to perform this task.

### Install docker 
- [docker](https://docs.docker.com/engine/install/)

### Install & Setup minikube 
- [minikube](https://minikube.sigs.k8s.io/docs/start/?arch=%2Flinux%2Fx86-64%2Fstable%2Fdebian+package)

### After installation and setup the minikube cluster
```
git clone https://github.com/Pankajarya1058/Task-5-K8-cluster-with-minikube.git
```

### First apply namespace.yml file
```
kubectl apply -f namespace.yml
```

### apply deployment and service file
```
kubectl apply -f service.yml
kubectl apply -f deployment.yml
```

### Run following command to check 
```
kubectl get ns
```
```
kubectl get deployment -n web-app
```
```
kubectl get pods -n web-app
```
```
kubectl describe pods -n web-app
```
```
kubectl get svc -n web-app
```

### To Scale the deployment
```
kubectl scale deployment/nginx-deployment --replicas=<desired-number> -n web-app
```

### To access the nginx pod/container through browser, run the following command
```
kubectl port-forward --address 0.0.0.0 deployment/nginx-deployment 8080:80 -n web-app
```

### To access the site from browser
```
http://<ip-of-server>:8080
```
