# Looking at Kubernetes costs from a FinOps angle
When you look at the challenges that containerization poses for FinOps—cost visibility, cost showback/chargeback, and cost optimization—you quickly realize that you’re encountering the same difficulties you faced as you moved into the cloud.

Containers represent another layer of virtualization on top of cloud virtualization, which creates a new wrinkle of complexity when it comes to tracking its costs. We’ll be using fundamental FinOps practices to solve these challenges.

This paper will walk through container and Kubernetes FinOps challenges into the same **inform, optimize, and operate** lifecycle that you would apply to the broader cloud FinOps.

## Relevant Terms and Concepts
Let’s quickly run through the basics for anyone not familiar with containers or Kubernetes before we go further. It will also be helpful to create a common understanding of these components throughout this whitepaper. 

***Note:** While there are many similarities between AWS Elastic Container Service (ECS) and Kubernetes, there are different terms used within each. For simplicity—besides when talking about Kubernetes specifically—we refer to “containers” and “server instances” where Kubernetes would refer to “pods” and “nodes.”*

Containers are, quite simply, a way to package software. All of the requirements and settings are baked into a deployable image. Container orchestration tools like Kubernetes help engineers deploy containers to servers in a manageable and maintainable way. 

There are a few key terms we will use throughout this chapter:

| **Term**                   | **Definition**                                                                                                                                                                                                                                                                                                                                                       |
|-------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Image                   | A template of a container with the software that needs to be run.                                                                                                                                                                                                                                                                                                |
| Container               | An instance of a container image; you can have multiple copies of the same image running at the same time.                                                                                                                                                                                                                                                       |
| Server instance/node    | A cloud server (e.g., EC2 instance, virtual machine).                                                                                                                                                                                                                                                                                                            |
| Pod                     | This is a Kubernetes concept. A pod consists of a group of containers and treats them as a single block of resources that can be scheduled and scaled on the cluster.                                                                                                                                                                                            |
| Container orchestration | An orchestrator manages the cluster of server instances, and also maintains the lifecycle of containers/pods. Part of the container orchestrator is the scheduler, which schedules a container/pod to run on a server instance. Examples include Kubernetes or AWS ECS.                                                                                          |
| Cluster                 | A group of server instances, managed by container orchestration.                                                                                                                                                                                                                                                                                                 |
| Namespace               | Another Kubernetes concept, a namespace is a virtual cluster where pods/containers can be deployed separately from other namespaces.                                                                                                                                                                                                                             |
| Pod labels              | Pod labels are key/value pairs that can identify attributes of objects that are meaningful and relevant to users, but do not directly imply semantics to the core system. Each object can have a set of key/value labels defined. Each Key must be unique for a given object. These can be helpful when you want to group more than one namespace, for example.  |

![Here's an example Dev and Staging cluster](/img/dev-staging.png)

*Figure 1: Basic view of a Kubernetes cluster*

A Kubernetes cluster (see Figure above) consists of a number of nodes (server instances) that run containers inside pods. Each pod can be made up of a varying number of containers. The nodes themselves support namespaces used to isolate groups of pods.