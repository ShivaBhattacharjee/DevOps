### <b>Installation and learning resources</b>

<a href="https://docs.docker.com/engine/install/">Install docker</a>
<br/>
<a href="https://docs.docker.com/get-started/overview/">Docker Docs</a>
<br/>
<a href="https://www.youtube.com/watch?v=17Bl31rlnRM&t=3895s">Kunal Kushwaha</a>
<br/>
<a href="https://www.youtube.com/watch?v=rr9cI4u1_88&t=9082s">Hitesh Choudary</a>
<br/>
<a href="https://www.youtube.com/watch?v=kTp5xUtcalw">Freecodechamp Docker + Kubernetes</a>

### <b>What is docker?</b>
Docker is a software platform that allows you to build, test, and deploy applications quickly. Docker packages software into standardized units called containers that have everything the software needs to run including libraries, system tools, code, and runtime.

### <b> What problem docker solves and why do we need it</b>
Applications running in docker containers can be deployed easily to multiple different operating systems and hardware platforms. DevOps teams know applications in containers will run the same, regardless of where they are deployed. Containers allow applications to be more rapidly deployed, patched, or scaled.

### <b>What is docker container</b>
A container is an isolated environment for your code. This means that a container has no knowledge of your operating system, or your files. It runs on the environment provided to you by Docker Desktop. This is why a container usually has everything that your code needs in order to run, down to a base operating system. You can use Docker Desktop to manage and explore your containers.

<i>No more  it works on my machine  </i>



### <b> How to pull and run docker image</b>
``` bash
Step 1 : Pull an image from docker hub

$ docker pull hello-world 

step 2 : Run the image 

$ docker run  hello-world
```

#### &nbsp; Expected output

```
Hello from Docker!
This message shows that your installation appears to be working correctly.

To generate this message, Docker took the following steps:
 1. The Docker client contacted the Docker daemon.
 2. The Docker daemon pulled the "hello-world" image from the Docker Hub.
    (amd64)
 3. The Docker daemon created a new container from that image which runs the
    executable that produces the output you are currently reading.
 4. The Docker daemon streamed that output to the Docker client, which sent it
    to your terminal.

To try something more ambitious, you can run an Ubuntu container with:
 $ docker run -it ubuntu bash

Share images, automate workflows, and more with a free Docker ID:
 https://hub.docker.com/

For more examples and ideas, visit:
 https://docs.docker.com/get-started/

```
### <b> Docker and Virtual machines </b>
<br/>
<br/>
<img src="./images/Docker-vs..png">
VMs have the host OS and guest OS inside each VM. A guest OS can be any OS, like Linux or Windows, irrespective of the host OS. In contrast, Docker containers host on a single physical server with a host OS, which shares among them. Sharing the host OS between containers makes them light and increases the boot time. Docker containers are considered suitable to run multiple applications over a single OS kernel; whereas, virtual machines are needed if the applications or services required to run on different OS. 
<br/>
<br/>

### <b>Docker run time</b>

Runtime allows to start and stop containers 
There are two types of runtime
<li>Runc</li>
It lies in a lower-level runtime and operates with the operating system to start and stop the containers.

<li>Containerd</li>
Containerd is a higher-level runtime that manages container lifecycles, including creation, execution, and termination. It handles container and image management, executes containers using low-level runtimes like runc, enforces security and isolation, and provides an interface for higher-level runtimes like Docker to interact with container operations.

<br/>

### <b>Docker Engine</b>

Docker Engine, also known as Docker Daemon or Docker runtime, is the core component of the Docker platform. It is responsible for building, running, and managing Docker containers. Docker Engine provides an environment where containers can be created, executed, and interacted with.

### <b>Orchestation</b>

In simple words, orchestration allows us to manage containers, and its usage is prominent in Kubernetes.

### <b>Docker Image and container</b>

A Docker image contains instructions to create a container, whereas a container is a running instance of an application. We can create a Docker image using a Dockerfile, which includes instructions for building the image.

<b>Here is an example of a DockerFIle for a react application made in vite </b>

```
# Choose a base image with Node.js pre-installed
FROM node:14-alpine

# Set the working directory in the container
WORKDIR /app

# Copy the entire project to the working directory
COPY . .

# Install dependencies
RUN npm i

# Expose the desired port (e.g., 3000 for a Node.js app)
EXPOSE 3000

# Define the startup command
CMD ["npm", "run","dev"]

```

