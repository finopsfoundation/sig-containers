# FinOps for Kubernetes: Unpacking container cost allocation and optimization

Launch Date: Nov 17, 2020 at CloudNativeCon North America

Addressing how and why containers complicate how teams manage the visibility and optimization of container costs, and how to apply FinOps best practices to improve cloud financial management.

## Before you begin reading this paper
You should understand the basics of how cloud computing works, know the key services on your cloud providers, including their common use cases, and have a basic understanding of billing and pricing models. Being able to describe the basic value proposition of running in the cloud and understand the core concept of using a pay-as-you-go consumption model are also necessary.

You’ll also need to have a base level of knowledge of at least one of the three main public cloud providers (AWS, Azure, Google Cloud). For AWS, we recommend AWS Business Professional training or, even better, the AWS Cloud Practitioner certification. For Google, check out the Google Cloud Platform Fundamentals course. For Azure, try the Azure Fundamentals learning path. Each can usually be completed in a full day workshop.

## Introduction
Since containers and container orchestrators are becoming a popular choice for many teams, it’s vital to understand the fundamental impact of these containerized workloads on FinOps practices. Shared resources, like containers, create challenges with cost allocation, cost visibility, and resource optimization.

In the containerized world, traditional FinOps cost allocation (e.g. mapping costs of resources back to teams or projects one-to-one) doesn’t work. You can’t simply allocate the cost of a resource to a tag or label, because resources may be running multiple containers, with each supporting a different application. They also may be attached to different cost centers around the organization.

Whether you’re a part of a team with an established FinOps practice, or are building up the discipline, everyone can relate to the challenges of mapping cloud utilization cost to their drivers one-to-one. And then come containers and Kubernetes. All of a sudden, those foundational cloud finance management practices need to be tweaked a bit. Have no fear though-- the same FinOps principles and practices can help your teams track containerization spending accurately.

We created this whitepaper to cover key questions, challenges, and considerations that any FinOps teams should understand before tackling containerization in the cloud. If you’re already using containerized services, then use this guide to double check that your teams are operating with strong, modern FinOps best practices.

This whitepaper will go over general container terms and concepts. It will also explore and address Kubernetes and container costs from the lens of FinOps core practices:
* **Inform:** Understand how the public cloud providers charge for their Kubernetes services. Learn why performing chargeback and cost allocation in environments with Kubernetes is challenging.
* **Optimize:** Look for ways to continuously optimize your Kubernetes clusters and pods.
* **Operate:** Determine your approach to container cost allocation and build policies to govern container spending, and integrate tooling to help manage container costs alongside traditional cloud spending.

Let’s begin.
