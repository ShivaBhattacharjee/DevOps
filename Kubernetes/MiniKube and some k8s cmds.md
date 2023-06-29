### <i>In Minikube, a Kubernetes cluster is composed of one VM. A cloud is composed of one or more VM(s)</i>


### <b>Start Minikube</b>

```bash
$ minikube start
```

### <b>Check Minikube status</b>

```bash
$ minikube status
```
#### <b>Get kubectl cluster info</b>

```bash
$ kubectl cluster-info
```
### <b>Get all </b>
```bash
$ kubectl get all
```
### <b>Get pods</b>

```bash
$ kubectl get pods
```

### <b>Get namespaces</b>
note: In Kubernetes (K8s), namespaces are a way to logically partition and isolate resources within a cluster.Resources in one namespace are usually not aware of or accessible to resources in other namespaces.

```bash
$ kubectl get namespaces
```
### <b>Get pods inside a namespace</b>
```bash
$ kubectl get pods --namespace= namespace-name
```
### <b>Get deployments</b>

```bash
$ kubectl get deployments
```

### <b>Check nodes</b>

```bash
$ kubectl get nodes
```

### <b>K8S dashboard</b>

```
$ minikube dashboard
```

### <b>Check docker env</b>

```bash
$ minikube docker-env
```

### <b>Check container running in minikube</b>

```bash
$ minikube ssh

$ docker ps
```

### <b>Check kubectl config</b>

```bash
$ kubectl config view
```

### <b>Get Current-Context</b>
Note: A Kubernetes context is a group of access parameters that define which cluster you're interacting with, which user you're using, and which namespace you're working in. It's helpful if you need to access different clusters for different purposes or if you want to limit your access to certain parts of a cluster.

```bash
$ kubectl config current-context
```

### <b>Delete pods</b>
```bash
$ kubectl delete pod <pod_name>
```


### <b>Create pods</b>
Note: here run nginx mean name of the image and image=nginx means the image that 
is to be pulled from docker hub
```bash
$ kubectl run nginx image=nginx
```

### <b>Get pods information</b>

```bash
$ kubectl describe pods <pod.name>
```