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


### <b>Some terminology</b>
   Note: A control plane which was knows as master node manages kubernetes cluster
   * Cluster: A Kubernetes cluster is a group of servers, called nodes, that work together to run containerized applications. Kubernetes is an open-source container orchestration platform that automates the deployment, scaling, and management of containerized applications. It provides a framework for abstracting away the underlying infrastructure and allows developers to focus on the application logic rather than the operational details.
   In a Kubernetes cluster, there are two main types of nodes:

     *  Master Node / Control plane: The master node or control plane is responsible for managing the cluster and making global decisions. It controls the scheduling and deployment of containers, monitors the health of nodes and containers, and manages scaling and load balancing. The master node runs components such as the Kubernetes API server, the controller manager, the scheduler, and etcd (a distributed key-value store for storing cluster state).
    
      * Worker Nodes: Wo rker nodes are the machines where containers are deployed and run. Each worker node has a container runtime, such as Docker or containerd, installed on it. These nodes communicate with the master node to receive instructions on which containers to run and how to manage them.

### <b>Kubectl</b>
   Kubectl is a command-line interface (CLI) tool used to interact with Kubernetes clusters. It is the primary tool for managing and controlling Kubernetes clusters from the command line. Kubectl allows you to perform various operations such as creating, inspecting, updating, and deleting Kubernetes resources.

   Kubectl can be interacted with two ways

   * Declarative Approach: In the declarative approach, you define the desired state of the Kubernetes resources in a configuration file, typically written in YAML or JSON format. You use kubectl to apply the configuration file to the cluster, and Kubernetes will make the necessary changes to ensure that the actual state matches the desired state.
   For example, you can define a Deployment in a YAML file specifying the number of replicas, container image, ports, and other configuration options. Then, you apply this configuration using kubectl:

      ``` bash
      kubectl apply -f deployment.yaml
      ```

   * Imperative Approach: In the imperative approach, you use kubectl commands directly to perform actions on the cluster without using configuration files. You provide specific instructions to kubectl on what actions to take.
   For example, you can run the following command to create a Deployment imperatively:

      ```bash
      kubectl create deployment my-deployment --image=my-container-image
      ```

### <b>Pods in kubernetes</b>
In Kubernetes, a Pod is the smallest and most basic unit of deployment. It represents a single instance of a running process in a cluster. A Pod encapsulates one or more containers, along with shared resources such as storage volumes, IP address, and environment variables.
Pods are used to deploy and manage containerized applications in Kubernetes. They provide an abstraction layer that allows you to run and scale your containers within the cluster. Each Pod in Kubernetes has a unique IP address and shares the same network namespace, which means all containers within a Pod can communicate with each other using localhost.We run containers inside pod we can run each application in one pod or multiple application in one pod

### <b>Controller Manager</b>
The Controller Manager is a component of Kubernetes that manages various controllers responsible for maintaining the desired state of the system. One of the primary responsibilities of the Controller Manager is to manage the control loops for running containers inside pods. These control loops ensure that the actual state of the system matches the desired state specified by the user or the system.

The Controller Manager typically performs the following four functionalities:

   * Desired State: The Controller Manager continuously monitors the desired state of the system, as specified by the user or the system itself. It keeps track of the desired number of pods, their configuration, and other relevant parameters.
   
   * Current State: The Controller Manager also monitors the current state of the system by interacting with the Kubernetes API server. It retrieves information about the existing pods, their status, and other relevant details.

   * Differences: By comparing the desired state with the current state, the Controller Manager determines any differences or discrepancies that exist. It identifies pods that need to be created, updated, or deleted to align the current state with the desired state.

   * Making Changes: Once the differences are identified, the Controller Manager takes the necessary actions to make the required changes. It creates new pods, updates existing ones, or terminates pods that are no longer required. It interacts with the Kubernetes API server to perform these operations and ensures that the system converges towards the desired state.

### <b>Scheduler</b>
In Kubernetes, the scheduler is a core component responsible for assigning pods to nodes in the cluster. Its primary function is to ensure that pods are scheduled onto appropriate nodes based on resource requirements, node capacity, and various other constraints.

When a new pod is created or when an existing pod needs to be rescheduled (e.g., due to node failure or scaling operations), the scheduler evaluates the available nodes and selects the most suitable node for the pod to run on. The scheduling process takes into consideration several factors, including:

   * Resource Requirements: The scheduler considers the CPU and memory requests and limits specified for the pod. It looks for nodes with sufficient available resources to accommodate the pod's requirements.

   * Node Affinity and Anti-affinity: Node affinity allows pods to be scheduled on nodes based on labels or node selectors. It enables requirements like running specific pods on nodes with certain hardware or in specific regions. Anti-affinity, on the other hand, allows for pod spreading across nodes to achieve fault tolerance.

   * Pod Interference: The scheduler takes into account whether the pod has any affinity or anti-affinity requirements with other running pods to avoid placing them on the same node, ensuring better performance and fault tolerance.

   * Taints and Tolerations: Nodes can be "tainted" to indicate certain limitations or restrictions. Pods can specify "tolerations" to indicate that they can tolerate being scheduled on tainted nodes, allowing for specialized or isolated nodes in the cluster.

   * Node Capacity and Utilization: The scheduler considers the capacity and utilization of nodes in the cluster to distribute pods evenly and avoid resource imbalances.

   * Quality of Service Requirements: Pods can have different quality of service classes, such as Guaranteed, Burstable, or BestEffort. The scheduler takes these classes into account while making scheduling decisions.

   * Custom Scheduling Preferences: Administrators can define custom scheduling preferences using configuration options or custom plugins to influence the scheduling decisions based on specific requirements or policies.

The scheduler operates in a continuous loop, constantly monitoring the cluster for unscheduled pods and making decisions to assign them to appropriate nodes. Once a suitable node is selected, the scheduler updates the pod's assignment in the Kubernetes API server, and the kubelet on the assigned node takes care of launching and managing the pod.

### <b>Kube Proxy</b>

Kube-proxy is a network proxy and load balancer in Kubernetes that runs on each node in the cluster. Its primary purpose is to handle network connectivity and routing for services in the cluster.

Here are the key functions of kube-proxy:

   * Service Proxy: Kube-proxy acts as a proxy for Kubernetes services. It watches the Kubernetes API server for changes in the service configuration and ensures that network traffic to services is correctly forwarded to the appropriate backend pods. It sets up the necessary IP routing rules to enable communication between clients and service endpoints.

   * Load Balancing: Kube-proxy distributes incoming traffic across multiple pods that belong to a service, providing load balancing functionality. It uses various load balancing algorithms, such as round-robin, to evenly distribute requests among the available pods. This helps to distribute the workload and improve the overall performance and availability of the service.

   * IP Tables or IPVS Modes: Kube-proxy can operate in different modes depending on the underlying network implementation and configuration. In the IP Tables mode, it configures IP tables rules on each node to redirect traffic to the appropriate backend pods. In the IPVS (IP Virtual Server) mode, kube-proxy uses the IPVS kernel module for more efficient load balancing and network traffic handling.

   * Service Discovery: Kube-proxy maintains a local cache of service endpoints and their associated pods. This allows it to quickly route traffic to the correct pod without the need for querying the Kubernetes API server for every request. The cache is updated periodically or whenever changes to services occur.

   * Health Checking: Kube-proxy periodically checks the health of backend pods associated with a service. If a pod becomes unhealthy or goes offline, kube-proxy removes it from the pool of available endpoints, ensuring that traffic is not routed to it until it becomes healthy again.

   * High Availability: Kube-proxy supports high availability by running in a distributed mode or using tools like keepalived to ensure that proxy functionality is available even if a node fails. In this way, it helps to maintain the availability of services in the cluster.

### <b> K8s dns</b>
In Kubernetes, DNS (Domain Name System) is a built-in service that provides name resolution for resources within the cluster. It allows you to refer to other Kubernetes objects by their names instead of using IP addresses, making it easier to manage and communicate between different components of your applications.
    DNS Resolution: Each Kubernetes cluster has a DNS server, typically running as a Kubernetes service named "kube-dns" or "coredns." This DNS server provides name resolution services for the cluster.

   * Service Discovery: When you create a Kubernetes service, a DNS record is automatically created for that service. The DNS record includes the service name and a namespace-specific domain name. For example, if you have a service named "my-service" in the "my-namespace" namespace, its DNS name would be "my-service.my-namespace.svc.cluster.local".

   * Pod DNS Names: Every pod in the cluster is assigned a hostname that follows the format "pod-name.pod-namespace.pod.cluster.local." Pods can resolve the DNS names of other pods within the same cluster using these hostnames.

   * DNS Caching: To optimize performance, DNS responses are cached by the kube-dns or CoreDNS service. This helps reduce the number of DNS queries made to the DNS server for repeated requests.

   * Cluster Domain: By default, the cluster domain is set to "cluster.local." This domain is appended to the DNS names for services and pods in the cluster. However, you can configure a different cluster domain if desired.

   * External DNS Resolution: Kubernetes DNS also supports external DNS resolution. This means that pods can resolve DNS names of external resources, such as external services or endpoints outside the cluster, as long as the DNS server used by the cluster can resolve those names.

### <b>Minikube</b>

Minikube is a tool used to run a single-node Kubernetes (K8s) cluster locally on your machine. It is designed to simplify the setup and testing of Kubernetes applications in a development or learning environment.

Minikube creates a virtual machine on your local system and deploys a minimal Kubernetes cluster inside it. This allows you to interact with and manage the cluster using the kubectl command-line tool just as you would with a full-scale Kubernetes cluster.

Minikube provides a lightweight and convenient way to experiment with Kubernetes features and workflows without the need for a complex multi-node cluster. It enables developers to develop and test their applications locally before deploying them to a production Kubernetes environment.

Some key features of Minikube include:

   * Single-node cluster: Minikube runs a single-node Kubernetes cluster on your local machine, allowing you to test and experiment with Kubernetes features.

   * Isolation: Minikube creates an isolated environment for your cluster, ensuring that the local setup does not interfere with any existing Kubernetes deployments.

   * Easy setup: Minikube simplifies the setup process by automatically configuring the required components, such as the Kubernetes API server, container runtime, and networking.

   * Cluster management: Minikube provides commands to start, stop, and delete the local Kubernetes cluster. It also offers options to configure cluster parameters such as CPU, memory, and Kubernetes version.

   * Add-on support: Minikube supports various Kubernetes add-ons, such as an ingress controller, dashboard, metrics server, and more. These add-ons enhance the functionality of your local cluster.

 [MiniKube Commands](https://github.com/ShivaBhattacharjee/DevOps/blob/master/Kubernetes/MiniKube%20and%20some%20k8s%20cmds.md)
