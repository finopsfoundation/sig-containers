# Container Label Dictionary

This label dictionary os to support the goal of FinOps to support the allocation of resource is. The label dictionary should serve as inspiration for labels and schemas, also for mapping different others (alias column) with similar context to one distinct (label column). It’s “the” place for new labels and their alias contributions from where people can and should create their own label set from. The finops.org label schema that you can find here is one of this.

## Overview

At the heart of the label is to support a wide variety of Use Case involving four personas across the maturity model (crawl, walk, and run).

The four personas are:

- Executives
- Business/Product Owners
- Finance/Procurement
- Engineering and Operations

## Dictionary

### Application

The Label support organizing your spend around the application architecture hierarchy
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
    <td>Crawl</td>
</tr>
</table>

### Cost-center

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
<td>Crawl</td>
</tr>
</table>

### Team

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
<td>Crawl</td>
</tr>
</table>

### Product

Product label organizes spend to align on the "products" a firm has and help organize application and service that support the product.
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
<td>Walk</td>
</tr>
</table>

### Department

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
    <td>Walk</td>
</tr>
</table>

### Environment

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
    <td>Walk</td>
</tr>
</table>

### Customer

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
    <td>Walk</td>
</tr>
</table>

### Service

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
    <td>run</td>
</tr>
</table>

### Component

Component label adds a layer to app/service hierarchy around how firms  organize "Microservice / Component / Function"
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
    <td>run</td>
</tr>
</table>

### Tech-stack

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
    <td>run</td>
</tr>
</table>


