## How to learn docker

<a href="https://docs.docker.com/get-started/overview/">Docker Docs</a>
<br/>
<a href="https://www.youtube.com/watch?v=17Bl31rlnRM&t=3895s">Kunal Kushwaha</a>
<br/>
<a href="">Hitesh</a>


### <b>What is docker?</b>
Docker is a software platform that allows you to build, test, and deploy applications quickly. Docker packages software into standardized units called containers that have everything the software needs to run including libraries, system tools, code, and runtime.

### <b> What problem docker solves and why do we need it</b>
Applications running in docker containers can be deployed easily to multiple different operating systems and hardware platforms. DevOps teams know applications in containers will run the same, regardless of where they are deployed. Containers allow applications to be more rapidly deployed, patched, or scaled.

### <b>What is docker container</b>
A container is an isolated environment for your code. This means that a container has no knowledge of your operating system, or your files. It runs on the environment provided to you by Docker Desktop. This is why a container usually has everything that your code needs in order to run, down to a base operating system. You can use Docker Desktop to manage and explore your containers.

<i>Solves it works on my machine </i>

### <b> How to run container in docker</b>
``` 
Step 1 : Pull an image from docker hub

$ sudo docker pull ubuntu 

step 2 : Run the image 

$ sudo docker run -it ubuntu
```

### <b> Docker vs Virtual machines </b>
<br/>
<br/>
<img src="./images/Docker-vs..png">
VMs have the host OS and guest OS inside each VM. A guest OS can be any OS, like Linux or Windows, irrespective of the host OS. In contrast, Docker containers host on a single physical server with a host OS, which shares among them. Sharing the host OS between containers makes them light and increases the boot time. Docker containers are considered suitable to run multiple applications over a single OS kernel; whereas, virtual machines are needed if the applications or services required to run on different OS. 