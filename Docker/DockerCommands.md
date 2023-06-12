### Pull an image from docker hub 

```bash
$ docker pull <image.name>

example:- $ docker pull ubuntu 
```

### Run an image 
it stands for interactive background bascially dont take up my terminal run this container in background

#### Output as you can see i am able to run ubuntu inside  fedora  using docker same can be done for other images like mongo db 

```bash
$ docker run -it ubuntu  
```
<img src="./images/Screenshot%20from%202023-06-12%2008-14-30-min.png " >


### List all the running container

```bash 
$ docker -ps 
or
$ docker container ls
or
$ docker container list
```

### List all stop  containers
```bash
$ docker ps -a
```

### How to remove a  container

```bash
$ docker rm container.id
or
$ docker remove container.id
```

### Get information about a container

```bash
$ docker inspect container.id
or
$ docker inspect container-name
```

### Stop a  container 

```bash 
$ docker stop container.id
```