### Pull an image from docker hub 

```bash
$ docker pull <image.name>

example:- $ docker pull ubuntu 
```

### Run an image 
-it is a combination of two options: "i" (interactive) and "t" (terminal). It allows you to interact with the container's command prompt.

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

###  Remove a  container
note:- no need to copy the entire container id copying first few characters gets the job done
```bash
$ docker rm container.id 
or
$ docker remove container.id
```
### Delete all stopped containers

```bash
$ docker container prune -f
```
### Get information about a container

```bash
$ docker inspect container.id
or
$ docker inspect REPOSITORY.name
```

### Get logs 

```bash
$ docker logs container.id
```

### Get logs for first few seconds
Note:- replace 5s with the timing you need
```
$ docker logs --since 5s container.id
```
### Stop a  container 

```bash 
$ docker stop container.id
```

### Remove an image

```bash
$ docker rmi image.id
or
$ docker rmi REPOSITORY.name
```

### Runing docker image on detatched mode
Note: The "-d" option is used for detached mode, which runs the container in the background. The "-p" option is used to specify the port configuration.It takes two arguments: "3030" is the port you want to expose externally, and "80" is the default port inside the container.

```bash
$ docker run -d -p 3030:80 nginx
```