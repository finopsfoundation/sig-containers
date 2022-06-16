# FinOps Foundation SIG Containers

Primary Authors: Bala Kaliamurthy, David Sterz 

Reviewed and Contributed to by: All Members

# Introduction

The SIG Containers will take on all questions around containerized workloads of any environment in the context of FinOps from cost visibility, cost optimization and operations. All Personas are welcome to contribute by sharing their container stories, asking questions about their day to day challenges with containers so we all learn from each other.

# Terms and definitions
The SIG Containers maintains their ([glossary](glossary/README.md)) with the definitions within the context of container technologies.

# Mission Statement

Empower organizations to confidently deploy containers to accelerate innovation while being constantly aware of the costs associated with those containers and how to manage/optimize them.
Focus should be on solving the current challenges as well as the best practices for container cost allocation and optimization. 
Clarify any further concepts of containers within the FinOps scope.

1. **Clarify and inform.** Provide valuable and objective information to the TAC, End Users and Projects of the FinOps Foundation regarding areas considered in-scope. Strengthen the project ecosystem to meet the needs of end users and project contributors. Educate and inform users with unbiased, effective, and practically useful information.
2. **Collaborate and interrelate.** Effectively interface with other related groups internal and external to the FinOps Foundation and connect the dots to facilitate meaningful collaborative progression of relevant topics. Engage more communities and create an on-ramp to effective TAC contribution &amp; recognition.
3. **Assist and attract projects.** Helping to maintain the continued health of FinOps Foundation containers-related definitions. Focus attention and resources on helping foster project maturity, systematically across FinOps Foundation projects. Clarify relationship between projects, FinOps Foundation project staff, and community volunteers. Identify gaps in the landscape of FinOps Foundation containers definitions. Find and attract projects to fill these gaps through invitation to present, diligence on proposed projects, and in essence, act as a funnel for TAC project reviews in this area.
4. **Afford impartial stewardship.** Provide and maintain a vendor neutral venue for relevant thought validation, discussion, and project feedback. Establish procedures to assist where necessary.

# End User Education:
* White paper, blogs, eBooks etc. 
* Videos or other forms of training clarifying the container terminologies
* Common or recommended best practices
  * Instrumentation
  * Allocation
  * Optimization
  * Governance and management in the context of cost management for containers

# Problem Space:
* General cloud problems map to containers (Cloud within a cloud)
* Challenges with the shift from cloud to containers 
* Challenges around cost allocation and accountability?
* Pairing the K8s constructs with what you are actually billed, Shared resource allocation (Network egress, storage), Idle cost distribution etc.
* Challenges with New K8s versions 
* Container Optimization/Rightsizing
* Node level rightsizing with Autoscaling 
* How can I optimize cluster management?
* Container pain points, Primary use cases etc.
* What does a proper chargeback, tagging or allocation model look like? 
* What’s idle? How should the different types of overhead (idle resources, admin nodes, managed service fees) be accounted for?
* Challenges with resource utilization on clusters and namespaces?
* Chargeback accuracy?
* Cost allocation for on-prem K8s clusters
* Impact of Security/Privacy on cost management
* New features that can have cost implications 
* Challenges with updates to billing files. 
* Budget and forecast for K8s
* Challenges with Multi TenancyMultitenancy
* Low Priority/Preemptible worker nodes
* Developers and Administrators - training 
* The shared resource model 
* ...

# Documented Best Practices and Failure examples:
* Tag/label hygiene
* How should we think about Namespaces versus labels, which of these works best when?
* Rightsizing 
* Automation best practice 
* Autoscaling
* ...

White Paper Example Topics:

* [Finops for Containers](https://github.com/finopsfoundation/sig-containers/tree/main/finops-for-kubernetes) 
* [Calculating Container costs](https://www.finops.org/projects/calculating-container-costs/)

## In Scope

- All container related technologies with a strong focus on kubernetes but not limited to it.
- Container workload related cloud resources such as database, storage, network

### FinOps Foundation Containers Working Groups

- (active) [Container Cost Allocation](wg-container-cost-allocation/README.md)
- (planned) Container Cost Optimization

## Out of Scope

- Cloud providers Software-as-a-Service (SAAS) resources

# Overlap and Relations with other Groups and Projects

- Slack Channel ([#sig-containers](https://finopsfoundation.slack.com/archives/C01D5HBNQVA))
- Slack Channel ([#containers-kubernetes](https://finopsfoundation.slack.com/archives/C0180PC67T2))
- Slack Channel ([#finops-for-engineers](https://finopsfoundation.slack.com/archives/C014CFZTE1W))
- Slack Channel ([#adopting-finops](https://finopsfoundation.slack.com/archives/CMZG5KZ8Q))
- Slack Channel ([#wg-reducing-waste](https://finopsfoundation.slack.com/archives/C029SCMA50B))
- Slack Channel ([#shared-cost](https://finopsfoundation.slack.com/archives/C022JKKCK0Q))

# Responsibilities and Deliverables

Clarify and further concepts of containers within the FinOps scope.

## Responsibilities

- Educating vendor neutral on best practices for all container runtimes and their cost related topics.
- Provide practical guidance and examples that can be applied in short time for any maturity level.

## Deliverables

- [FinOps label schema presentation at FinOps March'22 Summit](https://youtu.be/q0iuFU7qh8M?t=3868)
- [Sig-containers glossary](glossary/README.md)
- [Label dictionary](wg-container-cost-allocation/label-dictionary/README.md)
- [Label schemas](wg-container-cost-allocation/label-schemas/README.md)
- (coming in Q3 2022) - container use cases and stories
- ...

# Governance and Operations

This SIG follows the [standard operating model](https://github.com/finopsfoundation/tac/blob/master/sigs/readme.md#operating-model) provided by the TOC unless otherwise stated here.

# Operating Model

## Chairs:

- TAC Liaison: Jeremy Ung
- Tech Leads: Bala Kaliamurthy
- Chairs: David Sterz

In accordance with the [elections and terms](https://github.com/finopsfoundation/tac/blob/master/sigs/readme.md#elections)

## Communications

- Slack Channel ([#sig-containers](https://finopsfoundation.slack.com/archives/C01D5HBNQVA))
- Repo: [https://github.com/finopsfoundation/sig-containers](https://github.com/finopsfoundation/sig-containers)
- Meetings: 
	- (active) WG Container Cost Allocation
  		- Timing: Weekly at Thursday 8:30 AM PST / 11:30 AM ET / 5:30 PM CEST - 30 Minutes 
		- Location: Zoom - lookup [Event](https://www.finops.org/resources/events/) - FinOps - Container Cost Allocation Working Group Session
	  - Meeting Minutes: shared via mail and/or Slack ([#wg-#wg-container-cost-allocation](https://finopsfoundation.slack.com/archives/C02BDFZR3V4))
  - (idea) sig-containers general

## Main Contributors *(In alphabetical order)*

- Bala kaliamurthy
- Dan Casson
- David Sterz
- Erik Peterson
- Hannah Raikes
- Jonathan Morin
- Kevin Mueller
- Laila Majidi
- Noah Abrahamas
- Pavan Chavva
- Roi Rav-Hon
- Sean Pomeroy
- Stephen Arthur
- Stuart Davidson
- Youssef Ibrahim