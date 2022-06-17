# Container Label Dictionary

This label dictionary is to support the goal of FinOps to support the allocation of resources. 

The label dictionary should serve as inspiration for labels to build out schemas, and also shows the mapping of variants see "Label alias" with similar purpose to one distinct label. 

It is “the” place for collecting all relevant cost allocation labels and their aliases, while it remain open for any further contributions from the community to grow over time so finops practioners can explore and pick their own labels from here to build out their schemas to be used. 

The [finops.org label schema](../label-schemas/README.md) is one of the first examples that you can that was merged out of many label schemas from the community ready to be used for container cost allocation purposes.

## Overview

At the heart of the label is to support a wide variety of Use Case involving four [personas](https://www.finops.org/framework/personas/) across the [maturity](https://www.finops.org/framework/maturity-model/) model.

The four personas are:

- Executives ([CEO](https://www.finops.org/framework/personas/#ceo),[CTO](https://www.finops.org/framework/personas/#cto),[CIO](https://www.finops.org/framework/personas/#cfo))
- Business/Product Owners ([Product Owner](https://www.finops.org/framework/personas/#product-owner))
- Engineering and Operations ([Engineering Lead](https://www.finops.org/framework/personas/#engineering-lead))
- Finance/Procurement ([IT Finance Management](https://www.finops.org/framework/personas/#itfm), [Procurement](https://www.finops.org/framework/personas/#procurement))

The labels are also broken into the three maturity levels. This give guidance on where to start.


## Dictionary

### Crawl stage
--

#### application

The Label support organizing your spend around application architecture hierarchy
<table>
<tr>
    <td>Context</td>
    <td>App / Service Hierarchy</td>
</tr>
<tr>
    <td>Common Resources to Label</td>
    <td>namespace, pod, deployment</td>
</tr>
<tr>
    <td>Label alias
    <td>application<br>app<br>application-name<br>application-id  </td>
</tr>
<tr>
    <td>Example Values</td>
    <td>ACME Fitness</td>
</tr>
<tr>
    <td>Personas</td>
    <td>Business / Product Owner<br>Finance / Procurement<br>Engineering and Operations</td>
</tr>
<tr>
    <td>Maturity Level</td>
    <td>1 - Crawl</td>
</tr>
</table>

### cost-center

Cost-centers aligns to a business structure and help define the various areas that are driving the company expenses.

<table>
<tr>
<td>Context</td>
<td>Business organization</td>
</tr>
<tr>
<td>Common Resources to Label</td>
<td>namespace, pod, deployment</td>
</tr>
<tr>
<td>Label alias
<td>psp-element, cost-center
</tr>
<tr>
<td>Example Values</td>
<td>[alpha-numeric codes]</td>
</tr>
<tr>
<td>Personas</td>
<td>Finance/Procurement</td>
</tr>
<tr>
<td>Maturity Level</td>
<td>1 - Crawl</td>
</tr>
</table>

### team

Team Label help identify groups within an organization that are responsible for this spend.
<table>
<tr>
<td>Context</td>
<td>Business organization</td>
</tr>
<tr>
<td>Common Resources to Label</td>
<td>namespace, pod, deployment</td>
</tr>
<tr>
<td>Label alias
<td>team<br>squad<br>group<br>owner<br>maintainer<br>contact</td>
</tr>
</tr>
<tr>
<td>Example Values</td>
<td>[team name]<br>[team id]</td>
</tr>
<tr>
<td>Personas</td>
<td>Executives<br>Business / Product Owner<br>Finance / Procurement<br>Engineering and Operations</td>
</tr>
<tr>
<td>Maturity Level</td>
<td>1 - Crawl</td>
</tr>
</table>

### Walk stage

#### product

Product label organizes spend to align on the "products" a firm customer consume. This label helps organize applications and services that support the product.
<table>
<tr>
<td>Context</td>
<td>App / Service Hierarchy</td>
</tr>
<tr>
<td>Common Resources to Label</td>
<td>namespace, pod, deployment</td>
</tr>
<tr>
<td>Label alias
<td>product<br>workload<br>project</td>
</tr>
</tr>
<tr>
<td>Example Values</td>
<td>ACME Fitness Store<br>ACME Fitness + Video Streaming</td>
</tr>
<tr>
<td>Personas</td>
<td>Business / Product Owner<br>Finance / Procurement</td>
</tr>
<tr>
<td>Maturity Level</td>
<td>2 - Walk</td>
</tr>
</table>

### department

Department applies to business organization. Some organization use terms like Business Unit. The meaning is very organization dependent.
<table>
<tr>
    <td>Context</td>
    <td>Business organization</td>
</tr>
<tr>
    <td>Common Resources to Label</td>
    <td>namespace, pod, deployment</td>
</tr>
<tr>
    <td>Label alias
    <td>business-unit<br> department<br> business-domain<br>domain</td>
</tr>
<tr>
    <td>Example Values</td>
    <td>retail BU<br> streaming BU</td>
</tr>
<tr>
    <td>Personas</td>
    <td>Business / Product Owner<br>Finance / Procurement</td>
</tr>
<tr>
    <td>Maturity Level</td>
    <td>2 - Walk</td>
</tr>
</table>

### environment

Environment support calculating Cost of Good Sold (COGS) and aligns how organization deploy code. e.g. production versus development
<table>
<tr>
    <td>Context</td>
    <td>Platform + Operations</td>
</tr>
<tr>
    <td>Common Resources to Label</td>
    <td>namespace, pod, deployment</td>
</tr>
<tr>
    <td>Label alias
    <td>stage<br>environment<br>env</td>
</tr>
<tr>
    <td>Example Values</td>
    <td>dev<br> staging<br>prod</td>
</tr>
<tr>
    <td>Personas</td>
    <td>Business / Product Owner<br>Engineering and Operations</td>
</tr>
<tr>
    <td>Maturity Level</td>
    <td>2 - Walk</td>
</tr>
</table>

### customer

Customer label can identify that that are consuming a product/service.  This can support multi-tenant environment as well as silo tenant environments
<table>
<tr>
    <td>Context</td>
    <td>Business organization</td>
</tr>
<tr>
    <td>Common Resources to Label</td>
    <td>namespace, pod, deployment</td>
</tr>
<tr>
    <td>Label alias
    <td>customer</td>
</tr>
<tr>
    <td>Example Values</td>
    <td>[customer-id]<br>[customer-name]</td>
</tr>
<tr>
    <td>Personas</td>
    <td>Business / Product Owner<br>Engineering and Operations</td>
</tr>
<tr>
    <td>Maturity Level</td>
    <td>2 - Walk</td>
</tr>
</table>

#### Run stage

### service

Service label adds a layer to app/service hierarchy around how firms  organize product/applications into sub-components.
<table>
<tr>
    <td>Context</td>
    <td>App / Service Hierarchy</td>
</tr>
<tr>
    <td>Common Resources to Label</td>
    <td>pod, deployment</td>
</tr>
<tr>
    <td>Label alias
    <td>service<br>service-id</td>
</tr>
<tr>
    <td>Example Values</td>
    <td>Point of Sale<br>Store Shopping Cart<br>Store Catalog</td>
</tr>
<tr>
    <td>Personas</td>
    <td>Finance/Procurement<br>Engineering and Operations</td>
</tr>
<tr>
    <td>Maturity Level</td>
    <td>3 - Run</td>
</tr>
</table>

### component

Component label adds a layer to app/service hierarchy around how firms organize "Microservice / Component / Function" that support application or services
<table>
<tr>
    <td>Context</td>
    <td>App / Service Hierarchy</td>
</tr>
<tr>
    <td>Common Resources to Label</td>
    <td>namespace, pod</td>
</tr>
<tr>
    <td>Label alias
    <td>component<br>tier</td>
</tr>
<tr>
    <td>Example Values</td>
    <td>database<br>storage</td>
</tr>
<tr>
    <td>Personas</td>
    <td>Business / Product Owner<br>Engineering and Operations</td>
</tr>
<tr>
    <td>Maturity Level</td>
    <td>3 - Run</td>
</tr>
</table>

### tech-stack

Tech-Stack help bring context of spend to the view of platform or operations by purpose
<table>
<tr>
    <td>Context</td>
    <td>Platform + Operations</td>
</tr>
<tr>
    <td>Common Resources to Label</td>
    <td>namespace, pod, deployment</td>
</tr>
<tr>
    <td>Label alias
    <td>stack<br>servicegroup</td>
</tr>
<tr>
    <td>Example Values</td>
    <td>observability<br>build-tools<br>automation<br> security</td>
</tr>
<tr>
    <td>Personas</td>
    <td>Business / Product Owner<br>Finance / Procurement<br>Engineering and Operations</td>
</tr>
<tr>
    <td>Maturity Level</td>
    <td>3 - Run</td>
</tr>
</table>
