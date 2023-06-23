#### In Minikube, a Kubernetes cluster is composed of one VM. A cloud is composed of one or more VM(s)

<br/>

### <b>Start Minikube</b>

```bash
$ minikube start
```

### <b>Check Minikube status</b>

```bash
$ minikube status
```

### <b>Get pods</b>

```bash
$ kubectl get pods
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
Note: A Kubernetes context is a group of access parameters that define which cluster you're interacting with, which user you're using, and which namespace you're working in. It's helpful if you need to access different clusters for different purposes or if you want to limit your access to certain parts of a cluster.3

```bash
$ kubectl config current-context
```