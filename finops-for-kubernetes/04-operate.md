# Operate: Build policies and practices to manage Kubernetes costs

Now that Kubernetes costs can be accurately allocated, and ways to optimize those costs are known, it’s time to build a sustainable practice to enforce FinOps-focused policies and exercises. For example, scheduling development containers to be turned on and off around business hours, finding and removing idle containers, and maintaining container labels/tags by enforcement are just some of the practices to teach and empower teams to utilize.

---

## Cloud Cost POV: Start your FinOps team with a strong foundation

Before adding practices and policies to better track containerization costs, ensure that your teams have strong cloud financial management fundamentals. Work with your finance team and overall center of cloud cost of excellence to get aligned and have strong answers to the following questions:

* Do you have established reporting capabilities and KPIs across the infrastructure?
* Do your teams consistently run checks to ensure cloud financial governance and policies are being followed (understanding how to use namespaces, tagging untagged resources, using semantic tags to relate to projects/teams, automating tag correction to reduce errors)?
* How well do your teams provision only what they need? Can they explain what those costs are based on and report on them accurately?
* Who pays for shared, common services?
* Do your teams actively and frequently identify opportunities to optimize cloud resource utilization (and are they empowered to do so?)?

Answering these questions not only requires implementing key FinOps best practices, so catch up on those first. They might also cloud cost management solutions to help teams see the same utilization and cost reporting and act together to increase efficiency.

*Courtesy of Jonathan Morin, Sr. Product Manager, CloudHealth by VMware*

---

## Tooling option to manage container costs
Most companies on the path toward mastering FinOps for cloud services, including container costs, often take one of three paths. Whether it’s building in-house tooling to DIY their way to success, using native tooling provided by a cloud service provider, or using a cloud financial management platform, every choice has its pros and cons.

### DIY tracking of container costs
If your teams have the talent and resources to do so, creating a DIY approach to tracking cloud financial data, including container costs, can be a way to make sense of this spending. Companies at massive scale are doing this today, including Spotify, who run their own set of cloud management tools via [backstage.io](https://backstage.io).

This also might make sense if your teams are in early stages of cloud utilization and generate billing data that can be managed this way.

### Using native tooling to track costs
Using native tooling, often in conjunction with internal tools, can be another path toward FinOps success. As long as there’s a means to access and digest cloud cost data to generate chargeback and reporting that makes sense to your business, you will likely be in good shape. Unfortunately, if your teams are running a multi-cloud infrastructure, you’ll likely have to use each respective tool provided by each platform.

You might also need another data visualization or analysis tool to aggregate all of this cross-cloud financial data into one view.

### Using a cloud financial management platform
When you get to a certain scale, manual efforts can cause more pain than good and it’s time to use native tooling or a dedicated cloud financial management platform. This takes away manual human error and leaves allocation work (assuming everything is tagged and named accurately) to the tooling.

This can improve visibility into shared Kubernetes clusters and their costs. It can also improve how costs are allocated by teams or projects. Cloud financial management platforms often have features that support multi-cloud billing data as well.

However, a large part of your FinOps practice will be locked into the feature sets and pricing provided by the third-party tool. You might also have to annually make business sense of pricing, contracts, and negotiations to get a fair deal that makes sense for the size of your cloud infrastructure. A good starting place is to look at the FinOps Certified Platforms at the FinOps Foundation.

## Empower and incentivize developers to track their Kubernetes utilization
With a well tagged and labeled infrastructure, this should provide the foundation for  Dev and FinOps teammates to build their own custom reporting to track utilization data. Whether it’s assisted via API from native tools or cloud financial management tools, empowering teams to create and manage their own monitoring can help quite a bit.

Most likely, your developers are already tracking key infrastructure metrics that help people monitor service uptime and performance in real-time. Augmenting these existing metrics with cost data can enable them to incorporate this information in their decision making process without major workflow changes. 

>“Piping in cost as a first-class citizen alongside this data is an advanced FinOps move that lets engineers easily measure the impact of infrastructure and application-level changes. ” - Webb Brown, CEO Kubecost

Beyond costs that track spending and utilization, empower developers to further make their Kubernetes setups even more efficient by leveraging tools that are already part of their existing workflows. Oftentimes, this means embracing  container-focused open source tools. Application management tools like Helm, monitoring solutions like Prometheus, container workflow engines like Argo, and service mesh solutions like Linkerd can really help engineer teams get actionable visibility for their Kubernetes clusters in near real-time.