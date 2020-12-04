# Optimize: Build in cost efficiencies for your Kubernetes environment

Like the inform phase, the optimize phase in the container world is a direct adaptation of your original FinOps practices built for cloud platforms, but applied with the complexities of containers in mind.  

One can argue that containerization solves the rightsizing problem. Having more workloads running on the same server instance appears more cost-effective. But as you’ve seen so far, it’s a complex task to measure which teams or projects generate these costs, or whether or not you’re getting savings from your clusters. 

Let’s take a look at how your FinOps practices have to evolve in order to be successful. 

Once you’ve successfully charged back your kubernetes costs, the next step is to look for ways to optimize your kubernetes environments to reduce costs. There are several steps FinOps practitioners can partner with DevOps teams on to ensure that kubernetes costs don’t accelerate out of control.

## Pod / Container Rightsizing
Ensure that your containers are asking for an appropriate amount of resources. Since asking for too little means your application is not able to perform, often there is some buffer between the requests or limits configured for a container and what it really needs.

When this buffer is larger than necessary is when there is opportunity for cost savings. The Vertical Pod Autoscaler (VPA) is an example of an open source project that will help you by automatically adjusting the requests and limits configuration based on how much a container is seen to use, thereby saving you resources and cost while reducing overhead. 

The Horizontal Pod Autoscaler (HPA) is meant to scale out and in rather than up and down for the workloads. Caution here is to make sure the VPA and HPA policies don’t interfere with each other.

Binning and packing density settings are important and should be reviewed when designing clusters for purpose or business class tier of service where development or cost-focused clusters are meant to get as many containers per host. Meanwhile costs where production or performance clusters settings would be scoped for different needs and patterns. Having the ability to match the right quantity of pods and namespaces per instance family for your app is a good way to build a reference model that ensures proper capacity, availability, overhead, and economics. 

Another thing to look out for is making sure Ingress controller settings for ensuring proper traffic shaping and load mgmt to containers are being leveraged. 

## Node Rightsizing
Next is the choice of worker node type for the cluster. This becomes a type of bin packing problem except with all the complexities of the various platform choices.

Often simply making incremental improvements, for example when you notice that your nodes always have excess memory, it can make sense to switch to a node type that is the same but offers slightly less memory. In practice however this can be more complex. For example, if you have workloads that often consume more than they requested and distinguish the difference between those cases where it was needed and where it was only consumed because it was available but wasn’t critically needed.

Consider using instance weightings scores while you are producing a whitelist of instance size/types that are a good fit to run. The instance weighting will be useful when you are relying on diversified allocation strategies in a spot market where pricing may be the same but will help ensure the right value for your code is going to be provisioned based on weight values. 

## Autoscaling Adjustments
Something that makes Kubernetes especially powerful is the wealth of autoscaling options and the ability to respond dynamically to different conditions, such as increased or decreased demand. This can take some architecting and iterative adjustments to get right for your application, and there is room for waste along the way. However, the more tightly your horizontal pod autoscaling (when we need more / less pods) and cluster autoscaling (when do we need more / less nodes) are configured, the less waste and unnecessary cost to run your application.

### Discount types
Most cloud environments offer discount options that can offer significant savings, so long as the terms work for you and your application. 

### Spot / Low Priority / Preemptible worker nodes
These go by different names but typically provide a discount for workloads that may disappear on short notice. This allows cloud providers a way to incentivize filling all capacity pockets while being able to adjust for incoming workloads of priority that will pay on demand rates.

The declarative nature of Kubernetes makes it more conducive to taking advantage of spot discounts, as interruptions in the worker node fleet will be noticed and replaced. Still, some applications may not be tolerant of these interruptions. Applications that may fit this profile include data intensive workloads that may run in batches or are not as time sensitive such as machine learning training.

### Commitment discounts
These also go by several names and mechanisms such as Reserved Instances, Savings Plans, Committed Use Discounts, Subscription Discounts, etc., but all typically offer a discount to users in exchange for a long term commitment to spend with that cloud provider. These commonly cover compute resources, and for users who expect to have consistent usage for a year or more on a given cloud (and in some cases for a given workload type), this is an option to lower your cluster costs.

The ability to enable a purchase method mix and declare the split percentage of on demand, committed, and spot variable pricing is a great way to automate that into a cost efficiency blueprint.

For example: 10% committed use for control plane, 90% spot for workers/replicas for non prod, 50/50 for prod etc.

Producing the pre-built helm charts or launch plans ahead of time and publishing for reusability, with all the various optimizations included, ensures the wisdom can be put into practice with minimal experience and friction.

“Kubeless” or “Serverless Containers” are an emerging option where the cloud provider is providing a higher order service that is consumed and may solve skills shortages by the customer in operating and administering Kubernetes clusters. Others have looked to Kubeless solutions on FPGA type instances where results are dramatically faster, much lower cost, and without the operating system (OS) and container drag along of what is needed to log, patch, monitor, and maintain an OS and Kubernetes cluster.

---

## Cloud Cost Perspective: Unraveling complexities from large-scale, multi-cloud enterprise container utilization

Just when you think you have containerization and cluster costs somewhat under control, a merger and/or acquisition comes along and adds another cloud service provider or two. This can complicate how the company conducts complete chargebacks and cost allocation.

Having a cloud cost management platform, whether native tooling or a dedicated application, can reduce the complexity and friction of allocating container costs. Cloud cost management platforms are most effective when the fundamentals are covered:
* Observing utilization by Kubernetes constructs and associating it with cloud billing data
* Use Label Key/Value pairs in Kubernetes to align with internal cost centers
* Unifying Kubernetes label keys with traditional key tags to deepen the allocation model

With these fundamentals in place, FinOps teams can account for Kubernetes cost in a holistic way, no matter how complex an enterprise’s infrastructure might be. They can analyze costs by cluster or namespace, by cost center, and fully and accurately allocate these costs correctly.

*-Casey Doran, Director of Product, Apptio Cloudability*

---