# Container Glossary 

Annotation
> A key-value pair that is used to attach arbitrary non-identifying metadata to objects.
The metadata in an annotation can be small or large, structured or unstructured, and can include characters not permitted by labels. Clients such as tools and libraries can retrieve this metadata.

Applications
> Computer software package that performs a specific function directly for an end         user or, in some cases for another applications. In kubernetes it refers to the layer where various containerized applications run.

Business/Product Owner 
> This is one of the FinOps persona where the participants are usually Business and Product Owner team members, such as Director or Cloud Optimization, Cloud Analyst, or Business Operations Manager.

Certified Images
> Images that have been verified to contain specific contents (data) from a trusted publisher.

cgroup (control group)
> A group of Linux processes with optional resource isolation, accounting and limits. cgroup is a Linux kernel feature that limits, accounts for, and isolates the resource usage (CPU, memory, disk I/O, network) for a collection of processes.

Cloud-native
> Describes distributed applications, and the approach to building and running them, that take advantage of the cloud computing model for elastic scalability and increased availability. Cloud-native apps are typically open source or built on open source components and run as microservices in containers, where they can be dynamically orchestrated to optimize resource utilization.

Cluster
> A set of worker machines, called nodes, that run containerized applications. Every cluster has at least one worker node.
The worker node(s) host the Pods that are the components of the application workload. The control plane manages the worker nodes and the Pods in the cluster. In production environments, the control plane usually runs across multiple computers and a cluster usually runs multiple nodes, providing fault-tolerance and high availability.

Common Vulnerabilities and Exposures CVE System
> CVE, short for Common Vulnerabilities and Exposures, is a list of publicly disclosed computer security flaws. When someone refers to a CVE, they mean a security flaw that's been assigned a CVE ID number. Security advisories issued by vendors and researchers almost always mention at least one CVE ID.

ConfigMap
>An API object used to store non-confidential data in key-value pairs. Pods can consume ConfigMaps as environment variables, command-line arguments, or as configuration files in a volume. A ConfigMap allows you to decouple environment-specific configuration from your container images, so that your applications are easily portable.

Container
> A lightweight and portable executable image that contains software and all of its dependencies.

Container Breakouts
> When a container has bypassed isolation checks, accessing sensitive information from the host or gaining additional privileges. This means the process running inside the container is able to access anything outside the namespace meaning they can access anything else running inside other containers or on the host. With this information and the kernel capability it is possible to walk the host’s filesystem tree until you find the object you wish to open and then extract sensitive information like passwords.

Container Environment Variables
> Container environment variables are name=value pairs that provide useful information into containers running in a pod. Container environment variables provide information that is required by the running containerized applications along with information about important resources to the containers. For example, file system details, information about the container itself, and other cluster resources such as service endpoints.

Container Lifecycle Hooks
> The lifecycle hooks expose events in the Container management lifecycle and let the user run code when the events occur. Two hooks are exposed to Containers: PostStart which executes immediately after a container is created and PreStop which is blocking and is called immediately before a container is terminated.

Container Orchestrator
> A tool for monitoring and managing a set of containers, usually in an automated fashion. Kubernetes is currently the dominant container orchestrator.

Container network interface (CNI)
> Container network interface (CNI) plugins are a type of Network plugin that adheres to the appc/CNI specification.

Container Runtime
> The container runtime is the software that is responsible for running containers. Kubernetes supports container runtimes such as containerd, CRI-O, and any other implementation of the Kubernetes CRI (Container Runtime Interface).

Container runtime interface (CRI)
> The container runtime interface (CRI) is an API for container runtimes to integrate with kubelet on a node.

Container Run-time security
> Looking at real-time activity of containers, network, system, etc to detect and block unexpected or unwanted activity or behavior on hosts or inside your containers. This is separate from static scanning or continuous scanning which just looks for vulnerabilities in containers or on hosts.
The isolation and portability of containers also make it very difficult to see what’s actually going on inside of them. Run-time security provides a layer of visibility and allows you to detect unwanted activities/behaviors from users and programs, and then take actions like stopping or pausing a container to block the attack.

Container Storage Interface (CSI)
> The Container Storage Interface (CSI) defines a standard interface to expose storage systems to containers. CSI allows vendors to create custom storage plugins for Kubernetes without adding them to the Kubernetes repository (out-of-tree plugins). To use a CSI driver from a storage provider, you must first deploy it to your cluster. You will then be able to create a Storage Class that uses that CSI driver.

Containerd
> A container runtime with an emphasis on simplicity, robustness and portability. containerd is a container runtime that runs as a daemon on Linux or Windows. containerd takes care of fetching and storing container images, executing containers, providing network access, and more.

CRI-O
> A tool that lets you use OCI container runtimes with Kubernetes CRI. CRI-O is an implementation of the Container runtime interface (CRI) to enable using container runtimes that are compatible with the Open Container Initiative (OCI) runtime spec.
Deploying CRI-O allows Kubernetes to use any OCI-compliant runtime as the container runtime for running Pods, and to fetch OCI container images from remote registries.

Cost Center
> A cost center is a department within a business to which costs can be allocated.

Crawl
> This is a FinOps Maturity designation to identify where an Organization is currently operating from an adoption measure. 

CVE Scanning
> A vulnerability scan will reveal the issue so an administrator can adjust the system's configuration to improve security. Vulnerability scanning is important because systems on the Internet are constantly scanned and attacked.

DaemonSet
> Ensures a copy of a Pod is running across a set of nodes in a cluster. Used to deploy system daemons such as log collectors and monitoring agents that typically must run on every Node.

Deployment
> An API object that manages a replicated application, typically by running Pods with no local state.
Each replica is represented by a Pod, and the Pods are distributed among the nodes of a cluster. 

Distributed system
> Any system or application that operates across a network of services or nodes. A distributed system is a natural fit for microservices running in containers.

Docker
> Docker (specifically, Docker Engine) is a software technology providing operating-system-level virtualization also known as containers. Docker uses the resource isolation features of the Linux kernel such as cgroups and kernel namespaces, and a union-capable file system such as OverlayFS and others to allow independent containers to run within a single Linux instance, avoiding the overhead of starting and maintaining virtual machines (VMs).

Dockershim
> The dockershim is a component of Kubernetes version 1.23 and earlier. It allows the kubelet to communicate with Docker Engine. Starting with version 1.24, dockershim has been removed from Kubernetes. 

Docker Hub
> A service for finding and sharing container images.

Ephemeral Container
> A Container type that you can temporarily run inside a Pod. If you want to investigate a Pod that's running with problems, you can add an ephemeral container to that Pod and carry out diagnostics. Ephemeral containers have no resource or scheduling guarantees, and you should not use them to run any part of the workload itself.

Executives
> This is one of the FinOps persona where the executives, such as a VP/Head of Infrastructure, Head of Cloud Center of Excellence, CTO, or CIO, focus on driving accountability and building transparency, ensuring teams are being efficient, and not exceeding budgets.

Engineering and Operations
> FinOps persona where the engineers and Operations team members, such as Lead Software Engineers, Principal Systems Engineers, Cloud Architects, Service Delivery Managers, Engineering Managers, or Directors of Platform Engineering, focus on building and supporting services for the organization. Cost is introduced as a metric in the same way that other performance metrics are tracked and monitored. Members of these teams consider the efficient design and use of resources via activities like rightsizing ( the process of resizing cloud resources to better match the workload requirements), allocating container costs, finding unused storage and compute, and identifying whether spending anomalies are expected. 

FinOps Practitioner
> FinOps practitioner persona bridges business, IT and FInance teams by enabling evidence-based decisions in near-real time to help optimize cloud use and increase business value. They focus on establishing a FinOps culture and enabling stakeholder teams by demonstrating a working knowledge of the Principles and Capabilities of the FinOps Framework, a prescriptive model of actions and best practices.  

Finance/Procurement                                                
> This is a FinOps persona. The Finance and procurement team members, including Technology Procurement Managers, Global Technology Procurement, Financial Planning and Analyst Managers, and Financial Business Advisors, use the reporting provided by the FinOps team for accounting and forecasting. They work closely with FinOps practitioners to understand historic billing data so that they can build increasingly accurate cost models. They use their forecasts and expertise from the FinOps team to engage in rate negotiations with cloud service providers.

Image
> Stored instance of a Container that holds a set of software needed to run an application. A way of packaging software that allows it to be stored in a container registry, pulled to a local system, and run as an application. Meta data is included in the image that can indicate what executable to run, who built it, and other information.

Image Scanning (static analysis)
> A procedure in which a scanning provider analyzes each layer of the container image, indexes it, and compares the data against a Common Vulnerabilities and Exposures (CVE) database.

Init Container
> One or more initialization containers that must run to completion before any app containers run. Initialization (init) containers are like regular app containers, with one difference: init containers must run to completion before any app containers can start. Init containers run in series: each init container must run to completion before the next init container begins.

Job
> A Job creates one or more Pods and will continue to retry execution of the Pods until a specified number of them successfully terminate. As pods successfully complete, the Job tracks the successful completions.Deleting a Job will clean up the Pods it created. Suspending a Job will delete its active Pods until the Job is resumed again.

Kubecost
> Kubecost started in early 2019 as an open-source tool to give developers visibility into Kubernetes spend. 

Kubelet
> An agent that runs on each node in the cluster. It makes sure that containers are running in a Pod. The kubelet takes a set of PodSpecs that are provided through various mechanisms and ensures that the containers described in those PodSpecs are running and healthy. The kubelet doesn't manage containers which were not created by Kubernetes.

Label
> Labels are key/value pairs that can identify attributes of objects that are meaningful and relevant to users, but do not directly imply semantics to the core system. Each object can have a set of key/value labels defined. Each Key must be unique for a given object. These can be helpful when you want to group more than one namespace, for example.

LimitRange
> Provides constraints to limit resource consumption per Containers or Pods in a namespace. LimitRange limits the quantity of objects that can be created by type, as well as the amount of compute resources that may be requested/consumed by individual Containers or Pods in a namespace.

Namespace
> Another Kubernetes concept, a namespace is a virtual cluster where pods/containers can be deployed separately from other namespaces. Namespaces are used to organize objects in a cluster and provide a way to divide cluster resources.An abstraction used by Kubernetes to support isolation of groups of resources within a single cluster.
Names of resources need to be unique within a namespace, but not across namespaces. Namespace-based scoping is applicable only for namespaced objects (e.g. Deployments, Services, etc) and not for cluster-wide objects (e.g. StorageClass, Nodes, PersistentVolumes, etc).

Node
> A worker node may be a VM or physical machine, depending on the cluster. It has local daemons or services necessary to run Pods and is managed by the control plane. A node is a worker machine in Kubernetes. 

OpenCost
> OpenCost is a vendor-neutral open source project for measuring and allocating infrastructure and container costs in real time. Built by Kubernetes experts and supported by Kubernetes practitioners, OpenCost shines a light into the black box of Kubernetes spend.

Persistent container storage
> Any data storage device that retains data after cycling power. This is an important concept with containerization because ephemeral containers lack persistent storage and present challenges in working with stateful applications like databases that must remain available beyond the life of the program.
Persistent Volume
> A Persistent Volume(PV) is a piece of storage in the cluster that has been provisioned by an administrator or dynamically provisioned using Storage Classes. It is a resource in the cluster just like a node is a cluster resource. PVs are volume plugins like Volumes, but have a lifecycle independent of any individual Pod that uses the PV.

Pod
> The smallest and simplest Kubernetes object. A Pod is typically set up to run a single primary container. It can also run optional sidecar containers that add supplementary features like logging. Pods are commonly managed by a Deployment.

Pause Container
> Every Kubernetes Pod includes an empty pause container, which bootstraps the Pod to establish all of the cgroups, reservations, and namespaces before its individual containers are created. The pause container image is always present, so the pod resource allocation happens instantaneously as containers are created.

Registry
> A container registry is a single repository for your team to manage container images, perform vulnerability analysis, and decide who can access what with fine-grained access control.

Resource Limits and Requests
> When you specify a Pod, you can optionally specify how much of each resource a container needs. The most common resources to specify are CPU and memory (RAM); there are others.
When you specify the resource request for containers in a Pod, the kube-scheduler uses this information to decide which node to place the Pod on. When you specify a resource limit for a container, the kubelet enforces those limits so that the running container is not allowed to use more of that resource than the limit you set. The kubelet also reserves at least the request amount of that system resource specifically for that container to use.
For each container, you can specify resource limits and requests, including the following:
* spec.containers[].resources.limits.cpu
* spec.containers[].resources.limits.memory
* spec.containers[].resources.limits.hugepages-\<size>
* spec.containers[].resources.requests.cpu
* spec.containers[].resources.requests.memory
* spec.containers[].resources.requests.hugepages-\<size>

ReplicaSet
> A ReplicaSet (aims to) maintain a set of replica Pods running at any given time.
Workload objects such as Deployment make use of ReplicaSets to ensure that the configured number of Pods are running in your cluster, based on the spec of that ReplicaSet.

Rolling deployment
> A deployment strategy in which the new version of an application gradually replaces an old one. During this time, new and old versions coexist without affecting functionality or user experience. Rolling deployment of an application running as microservices in containers allows the app to be updated piece by piece, without any downtime. If there is an issue with the new version of a microservice, it can be temporarily reverted to its original version.

Run
> This is a FinOps Maturity designation to identify where an Organization is currently operating from an adoption measure. 

Security Context
> The securityContext field defines privilege and access control settings for a Pod or container. 
In a securityContext, you can define: the user that processes run as, the group that processes run as, and privilege settings. You can also configure security policies (for example: SELinux, AppArmor or seccomp).
The PodSpec.securityContext setting applies to all containers in a Pod.

Self-healing
> Any device, software, or system that has the ability to perceive that it is not operating correctly and, without human intervention, make the required adjustments to restore itself to normal operation. For example, the Kubernetes container orchestrator replaces containers that fail, kills containers that don't respond to kubelet health checks, and doesn't advertise them to clients until they are once again ready to serve.

Server instance/node
> A cloud server (e.g., EC2 instance, virtual machine).

Service
> An abstract way to expose an application running on a set of Pods as a network service.The set of Pods targeted by a Service is (usually) determined by a selector. If more Pods are added or removed, the set of Pods matching the selector will change. The Service makes sure that network traffic can be directed to the current set of Pods for the workload.

Shared Cluster
> This implies there are several users of the same cluster sharing it’s resources.

Sidecar
> A sidecar is just a container that runs on the same Pod as the application container, because it shares the same volume and network as the main container, it can “help” or enhance how the application operates. Common examples of sidecar containers are log shippers, log watchers, monitoring agents among others.

Signed Images
> You can use trust to do client-side certification of any image you’re pulling from a registry. Image signing gives you the ability to guarantee an image hasn’t been altered since it was signed. It can be used to prevent images from starting that haven’t been signed.

StatefulSets
> StatefulSet is the workload API object used to manage stateful applications.

Storage Classes
> A StorageClass provides a way for administrators to describe the "classes" of storage they offer.

Tagging
> Also known as labels is the application of meta data in the form of key-value pairs to objects including containers. Tags allow you to assign business-context details to specific resources and then to analyze that information to answer your company-specific questions. Cost management and optimization related tags can include cloud accounting models, ROI calculations, cost tracking, budgets, alerts, recurring spend tracking and reporting, post-implemention optimizations, and cost-optimization tactics.

Unit Economics
> To measure cloud spend against a business metric, such as total revenue, deliveries made, paid subscribers, customer orders completed, etc.

Walk
> This is a FinOps Maturity designation to identify where an Organization is currently operating from an adoption measure. 

Workload
> A workload is an application running on Kubernetes. Various core objects that represent different types or parts of a workload include the DaemonSet, Deployment, Job, ReplicaSet, and StatefulSets objects.
For example, a workload that has a web server and a database might run the database in one StatefulSet and the web server in a Deployment.





