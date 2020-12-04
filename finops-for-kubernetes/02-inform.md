# Inform: How container and Kubernetes costs are generated

Your first focus should be to generate reporting that determines the cost of individual containers on the clusters that teams are operating. This is a foundational step toward building visibility into your container spending.

## How container cost allocation is different
Cloud service providers will charge your teams for every server instance that makes up a cluster. These charges are incurred when containers are deployed into a cluster, as they consume some amount of the cluster’s resource capacity. The moment a process is run, a charge is incurred. It’s similar to when you provision a server with your cloud service provider. You pay for that server resource, whether you use it or not.

In order to allocate the individual costs of a container that runs on a cluster, you’ll need some way to determine how much of the underlying server the individual container consumed. You also need to understand the satellite costs of a running cluster. These include management nodes, data stores used to track cluster states, software licensing, backups, and potential disaster recovery costs. These costs are all part of running clusters and must be taken into account in your cost allocation strategy.

## Container features bring up cost complexity
What users enjoy about container orchestration services is that they can greatly simplify:
* Scheduling how your teams spin up containers based on utilization requirements
* Managing network scaling and connection at various granularities
* Autoscaling and automating node creation and deletion to adapt to your changing workloads

You can run Kubernetes on virtual machine (VM) services provided by all major cloud providers, or use their native offerings to manage Kubernetes clusters. Examples include:
* Amazon Elastic Kubernetes Service (Amazon EKS) on AWS
* Google Kubernetes Engine (GKE) on Google Cloud
* Microsoft Azure: Azure Kubernetes Service (AKS)
* IBM Cloud: IBM Cloud Kubernetes Service
* Oracle Cloud Infrastructure: Oracle Container Engine for Kubernetes
* Alibaba Cloud: Container Service for Kubernetes (ACK)

Every provider will offer their own levels of support and service, including helping your teams migrate to the cloud. All of these services are like other cloud services: pay-as-you-go. Though pay-as-you-go cloud billing can be convenient, the ability of a cluster to run multiple projects from multiple teams can make cloud financial management and cost allocation a challenge.

The traditional approach to billing for managed kubernetes services is to charge per cluster per hour, plus the additional underlying resources that the cluster consumes. This makes container cost management especially challenging since you can’t simply look at your cloud bill and see which resources are being consumed by a container cluster.

## Why is it harder to bill and report on Kubernetes costs?

Allocating costs in a container environment surfaces additional challenges than traditional cloud environments. In a traditional cloud environment, FinOps practitioners can tag non-container resources one-to-one, allowing reporting tools to easily map services to cost centers. Assigning accountability for those apps is simply a mapping exercise of app vendor tags to a team.

With Kubernetes, one-to-one mappings of tags to teams don’t cover some of the complex use cases that container utilization can create. Most Kubernetes clusters are shared services with applications run by any number of teams. This means there’s no direct cost to a specific container; a series of them are coming together to generate costs per cluster of work. There is no easy way to map cloud charges to specific container usage.

![A high-level look at how containerized services can be labeled and mapped]()
*Figure 2: A high-level look at how containerized services can be labeled and mapped.*
*Source: Debo Aderibigbe, Billing Product Manager, Google Compute Cloud, [FinOps Summit: Cost Visibility and Optimization in Kubernetes](https://kccnceu20.sched.com/overview/type/FinOps+Summit), KubeCon, CloudNativeCon EU 2020.*

Containers are deployed in Kubernetes clusters, which consume cloud resources (such as compute) just as any other tenant would. The challenge lies in the fact that, within each cluster, you generally have multiple teams consuming portions of those underlying resources.

Additionally, containerized environments are much more dynamic than non-containerized ones, with the [average lifespan of a container being one day](https://www.google.com/url?q=https://www.datadoghq.com/container-report/&sa=D&ust=1606873149474000&usg=AOvVaw31ESoO5kTZWVAy7WoBpCQA) versus a typically much longer utilization time for a VM. Given the dynamic nature of the Kubernetes scheduler, workloads can be rescheduled across instance type, zone, or even region. This makes cost management even more complex, as you must keep up with the rapid pace of change.

## Tracking shared cluster and off-cluster resource costs together

![An example of shared and off-cluster resources]()

*Figure 3: Applications with Shared Infrastructure and Services (Kubernetes)*
*Source: Casey Doran, “FinOps Summit: Cost Visibility and Optimization in Kubernetes”*

So, how do we unravel this complexity and improve how we manage container costs? First, let’s quickly review how our teams are billed for Kubernetes usage.

## Cost allocation practices and policy examples to govern container spending

**With cloud financial management, predictability is king.** Experienced FinOps practitioners will keep costs within budget and minimize surprises. Teams that are used to data center costs know that they are fixed and recurring. The transition to cloud services changes this expectation, and containerization further complicates things.

## Container classes within Kubernetes
Cluster orchestration solutions like Kubernetes allow you to set different resource guarantees on the scheduled containers called Quality of Service (QoS) classes.

### Guaranteed resource allocation
For critical service containers, you might use guaranteed resource allocation to ensure that a set amount of vCPU and memory is available to the pod at all times. You can think of guaranteed resource allocation as reserved capacity. The size and shape of the container do not change.

### Burstable resource allocation
Spikey workloads can benefit from having access to more resources only when required, letting the pod use more resources than initially requested when the capacity is available on the underlying server instance. Burstable resource allocation is more like the burstable server instances offered by some cloud service providers (T-series from AWS and f1-series from GCP), which give you a base level of performance but allow the pod to burst when needed.

### Best effort resource allocation
Additionally, development/test containers can use best-effort resource allocation, which allows the pod to run while there is excess capacity, but stops it when there isn’t. This class is similar to preemptible VMs in GCP or spot instances in AWS.

When the container orchestrator allocates a mix of pods with different resource allocation guarantees onto each server instance, you get higher server instance utilization. You can allocate a base amount of resources to fixed resource pods, along with some burstable pods that may use up to the remainder of the server resources, and some best effort pods to use up any spare capacity that becomes available.

Now that we’ve covered some basics, the next part of this section will start to explore some tactics to begin container cost allocation. We’ll cover:

* Creating better understanding between dev, ops, and finance to work toward a more predictable budget. Using tools to automate away human error and use containerization services with more cloud financial accuracy
* Using resource or application-defined aggregation: Stopping individual teams from creating many unique projects and instead, using defined and dedicated clusters
* Assigning teams to namespaces can help provide accurate means to charge back container costs to respective projects and teams
* Taking cloud service tagging to the next level with container cluster labels

![A look at how complicated container cost allocation can be]()

*Figure 3: A look at how complicated cost allocation for containers can be.*
*Source: Debo Aderibigbe, Billing Product Manager, Google Compute Cloud, FinOps Summit: Cost Visibility and Optimization in Kubernetes, KubeCon, CloudNativeCon EU 2020.*

In any FinOps or cloud financial management strategy, flexibly understanding costs can drive more accountability. The goal: to help users see their container cost drivers by both services used and container workload. Combining these two layers helps teams determine their Total Cost of Ownership.

## Taking a deeper look at specific containerization costs
One method, recommended by Debo Aderibigbe, a Google Cloud Billing Product Manager, is to break down costs by:
* **Billing Hierarchy:** Organizations, folders, projects, normalizing them with cross-cloud concepts: Linked Accounts, Tags, Subscriptions, etc.
* **Resources:** Compute cores, RAM, GPU, TPU, Load Balancers, Persistent Disk, Custom Machines, Network Egress
* **Namespaces:** labeling specific, isolated containers
* **Labels:** Teams, cost centers, app names, environment, and more

With a deep labeling and tagging of all of these cost drivers, users can improve the accuracy of how they invoice teams, audit costs, allocate costs, optimize overrun costs, model budgeting scenarios, or fit workload costs within quotas or under budget caps.

## How LiveRamp addressed containerization costs on GKE
The LiveRamp team migrated on-prem services to Google Cloud Platform, scaling up container services (and costs), which caught the eye of the Finance team. They completed a successful technical migration, but a month later, budgets were overrun. They needed a way to explain  what happened.

At that time, LiveRamp was missing the cultural shift to FinOps, and developers didn’t understand their new responsibilities were to cloud finances. To increase this understanding, container-focused FinOps principles helped rationalize cloud cost and operational decisions in different ways. They had to overcome challenges that came up due to every team having their own accounts and setups.

After much FinOps-focused work, new policies were built in, such as enforced namespacing for large clusters and better tagging and labeling to improve accuracy of allocation, both key FinOps practices. It also helps to find tooling that suits your teams needs in managing cloud financial management, e.g. Cloudability, CloudHealth, native tools, etc.

*-Sasha Kipervarg, (former) Head of Global Cloud Operations, LiveRamp*

## Consistent labeling and namespace strategy to improve allocation
Once you’ve implemented a consistent and robust labeling and namespace strategy, you can start to consider how you will allocate cluster costs. Unless you’re using GKE, you can’t easily see which groups are driving costs within a cluster.

A common methodology will be to look at the proportional resources consumed by each group (label, namespace, etc) and use that to allocate the cluster costs to those groups. For example, if you have four namespaces in a cluster that each consume 25% of the cluster resources, you could decide to allocate 25% of the total cluster costs back to each of those namespaces. 

In the real world, any environment will never be this simple or straightforward. One additional layer of complexity is answering the question of how are you determining cluster resource utilization? Will you base it off CPU, memory, or a combination of the two? Do you want to consider requests or actual consumption?

There are pros and cons to each of these approaches, as outlined in the table below.

|             |                                                       **Resource Requests**                                                      |                                                                                               **Actual Usage**                                                                                              |
|-------------|:----------------------------------------------------------------------------------------------------------------------------:|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|
|  Advantages | Allocate all costs Incentivize teams to only provision what they need There are tools to help!(e.g. vertical pod autoscaler) | Each team / app only pays for what they use                                                                                                                                                             |
|  Challenges | Some organizations are not using resource request fields yet May also incentivize under-specifying requirements              | Who pays for the rest (idle time / cycles)? What do we do about overprovisioning? Can incentivize teams to provision more just in case, and not pay for it Can set unrealistic goal of 100% utilization |

## Going beyond the Core Cluster Costs
When allocating the costs out to the consumers of the cluster, it’s important to consider not only the cost of the compute nodes the container operated upon, but also the satellite costs of operating the cluster. 

### Management / Cluster Operational costs
Costs charged by the cloud service provider for managing the cluster or costs incurred by running self managed container orchestrator nodes should be considered. Edge services like WAF, Load Balancers, etc also contribute to the overall cost of running a workload on a cluster.

### Storage Costs
Containers consume storage even if this is treated as ephemeral by the services running inside the container. Outside of the container however, consider the host OS on the nodes and any backup or data retrieval storage that is used in operating a production cluster can be allocated back to the workloads running on the cluster.

### Licensing
Licensing costs are always a fun topic, if you are running licensed operating systems for the host node. License costs may be included in the charge by your cloud service provider. However, if you operate these using bring your own license (BOYL), the license cost will need to be allocated from the external spend. Alongside the host operating system, consider any software packages running on the host OS that incurs a license fee. The workload itself running inside the container may also be using licensed software that may need to be allocated.

### Observability
Often, metrics and logs are sent from the cluster to a service which your teams are able to visualise, monitor, and alert upon. This data is sent either to services operated by the cloud service provider or even 3rd party SaaS solutions like (Splunk Cloud, Sumo Logic, Datadog, SignalFx, etc). 

### Security
The major cloud service providers now have very extensive security related services to assist in maintaining a secure cloud environment. Enabling these security features however does not often come for free, and these additional costs may need to be allocated to your teams.

Tempting as it may be to include every individual dollar from all of the above sources in your cost allocation strategy, as with everything FinOps, we recommend you start simple and grow your practice over time (Crawl, Walk, Run). It can become overwhelming to implement all of these cost allocation items at once, and as you develop both a process to allocate costs and the understanding of the allocation around your organization, the divide and conquer approach will be more likely to succeed.

## Addressing static versus runtime container costs
Containerization costs are also broken up into two primary types: Static and Runtime costs.

### Static costs
For static costs, you need to consider the creation of the solution within the container to ensure the quality of the solution to the project but also how it affects the CPU, Network and Storage when deployed. Static container costs can be further defined by stateless and stateful containers: Stateless examples of these include: 

* Web servers with static resources: Apache, Nginx, IIS, 
* Application servers, stateless applications: Tomcat, nodeJS, JBoss, Symphony, .NET
* Microservices;  Spring Boot, Play, Quarkus
* Tools: Maven, Gradle, scripts, tests

### Application servers with stateful applications
There is often a need to store user sessions in an application. Two approaches to handling this case are to use a load balancer with session affinity to ensure the user always goes to the same container instance or to use an external session persistence mechanism which all container instances share.

There are also some components that provide native clustering such as portals or persistence layer caches. It’s usually best to let the native software manage synchronization and states between instances. Having the instances on the same overlay network allows them to communicate with each other in a fast, secure way.

### Databases
Databases usually need to persist data on a filesystem. The best practice is to only containerize the database engine while keeping its data on the container host itself. This can be done using a host volume, for example: $ docker run -dit -v /var/myapp/data:/var/lib/postgresql/data postgres.

Kubernetes can also be used as an alternative to managed database services. For example, a cluster dedicated to MongoDB or Elasticsearch can deliver something similar to a fully-managed service for a fraction of the cost.

### Applications with shared file systems
Content Management Systems (CMS) use filesystems to store documents such as PDFs, pictures, Word files, etc. This can also be done using a host volume which is often mounted to a shared filesystem so several instances of the CMS can access the files simultaneously.

### Runtime costs
Runtime costs by most are assumed to be static for containers. How you run your containers will affect your bottom line. Examples of these costs from cloud service providers include:
* Bandwidth is often overlooked or underappreciated in estimating cloud computing charges.
* Leaving a containerized application deployed that you forgot about is a surefire way to get a surprising bill. Once you put applications or data into the cloud, they continue to cost you money, month after month, until such time as you remove them. It’s very easy to put something in the cloud and forget about it
* Compute charges are not based on usage.
* Polling data in the cloud is a costly activity and incurs transaction fees. Very soon the costs could add up based on the quantity of polling.
* Unintended traffic in the form of DOS attacks or spiders etc. could increase traffic in unexpected ways. The best way to deal with such unintended charges is to audit the security of the application and provide measures of controls such as CAPTCHAs.
* Management: Regularly monitor the health of your applications and its billing. Regularly review whether what’s in the cloud still needs to be in the cloud. Regularly monitor the amount of load on your applications. Adjust the size of your deployments to match load.

## Considerations for container savings in production
Containerized deployments can realize up to 90% in discounts compared to on-demand prices for running stateless and fault-tolerant applications. Containers that shall be ephemeral and stateless adhere to a graceful startup and graceful shutdown.

With these qualities, serverless deployments become more attractive due to the fact that these deployments are only charged when running. Another way to think about it is that you’re charged nothing while in a dormant state. Just deploying the contents to a serverless API is not enough as you must obtain equal functionality with performance. The cold start becomes your nemesis.

However, new boundaries are opening up that allow universal batch serverless loads to run on cloud providers, such as Apache Beam. Once enabled, many new areas from IT will be able to participate in the savings, following sophisticated data-parallel processing pipelines that enable execution across a diversity of cloud provider engines, or runners.