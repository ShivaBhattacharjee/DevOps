### <b>Learning Resources</b>

[Documentation](https://kubernetes.io/docs/home/)

[Free code champ](https://www.youtube.com/watch?v=d6WC5n9G_sM&t=243s)

[Kunal Kushwaha](https://www.youtube.com/watch?v=KVBON1lA9N8&t=781s)

[Hitesh Choudhary](https://www.youtube.com/watch?v=7XDeI5fyj3w&t=782s)

### <b>What is kubernetes</b>
Kubernetes is an open-source container orchestration system for automating software deployment, scaling, and management. Originally designed by Google, the project is now maintained by the Cloud Native Computing Foundation

### <b> Configuration management </b>
Configuration management in the context of Kubernetes refers to the management of configuration settings and resources within a Kubernetes cluster using software tools and practices. Kubernetes itself provides native mechanisms for managing configurations, but additional tools can be used to enhance the configuration management process.



### <b>Managing containers</b>
* <b>Monolithic containers</b>
    
    Monolithic applications are traditional software applications that are built as a single, indivisible unit. In a monolithic architecture, all the components of the application, such as the user interface, business logic, and data access layers, are tightly coupled and run as a single process or application. While it is relatively easy to deploy, one drawback is that if any changes are made, the entire code needs to be deployed again. For example, if we scale the business logic, we also need to scale other components like the user interface.

 * <b>Micro services</b>
  
    Microservices architecture is an approach to software development in which a large application is divided into smaller, independent services. Each service has its own responsibility and can be developed, deployed, and scaled independently. These services communicate with each other through well-defined APIs, typically utilizing lightweight protocols like HTTP or messaging systems. The adoption of microservices brings several advantages, including enhanced flexibility, scalability, and fault isolation. Consequently, it allows for scaling individual components without impacting other components.

 * <b>Service Mesh</b>
  
    A service mesh is a dedicated infrastructure layer that handles communication between services in a microservices architecture. It provides capabilities such as service-to-service communication, load balancing, service discovery, encryption, authentication, and observability

### <b>Orchestrators</b>
Orchestrators play a crucial role in dynamically deploying and managing applications. They have the capability to upscale containers, automatically heal them in the event of failures, and enable seamless scaling and real-time updates without any downtime.


### <b> Architecture of kubernetes</b>
   * Cluster: A Kubernetes cluster is a group of servers, called nodes, that work together to run containerized applications. Kubernetes is an open-source container orchestration platform that automates the deployment, scaling, and management of containerized applications. It provides a framework for abstracting away the underlying infrastructure and allows developers to focus on the application logic rather than the operational details.
   In a Kubernetes cluster, there are two main types of nodes:

     *  Master Node: The master node is responsible for managing the cluster and making global decisions. It controls the scheduling and deployment of containers, monitors the health of nodes and containers, and manages scaling and load balancing. The master node runs components such as the Kubernetes API server, the controller manager, the scheduler, and etcd (a distributed key-value store for storing cluster state).
    
      * Worker Nodes: Worker nodes are the machines where containers are deployed and run. Each worker node has a container runtime, such as Docker or containerd, installed on it. These nodes communicate with the master node to receive instructions on which containers to run and how to manage them.

## <b>Kubectl</b>
   Kubectl is a command-line interface (CLI) tool used to interact with Kubernetes clusters. It is the primary tool for managing and controlling Kubernetes clusters from the command line. Kubectl allows you to perform various operations such as creating, inspecting, updating, and deleting Kubernetes resources.

   Kubectl can be interacted with two ways

   Declarative Approach: In the declarative approach, you define the desired state of the Kubernetes resources in a configuration file, typically written in YAML or JSON format. You use kubectl to apply the configuration file to the cluster, and Kubernetes will make the necessary changes to ensure that the actual state matches the desired state.
   For example, you can define a Deployment in a YAML file specifying the number of replicas, container image, ports, and other configuration options. Then, you apply this configuration using kubectl:

  ``` bash
   kubectl apply -f deployment.yaml
   ```

   Imperative Approach: In the imperative approach, you use kubectl commands directly to perform actions on the cluster without using configuration files. You provide specific instructions to kubectl on what actions to take.

   For example, you can run the following command to create a Deployment imperatively:
   ```bash
   kubectl create deployment my-deployment --image=my-container-image
   ```