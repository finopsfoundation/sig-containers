# Kubernetes FinOps Label Schema

Just as [there are recommended labels for Kubernetes objects](https://kubernetes.io/docs/concepts/overview/working-with-objects/common-labels/), there is a need for FinOps based labels to assist in allocating the cost for Kubernetes workloads.

## Labels

| Key                      | Description                 | Example                   | Type   | Maturity  |
| :----------------------- | :-------------------------- | :------------------------ | :----: | :-------: |
| `finops.org/application` | Application Name            | `acme fitness`            | string | 1 - Crawl |
| `finops.org/product`     | Product Name                | `acme fitness store`      | string | 2 - Walk  |
| `finops.org/service`     | Service                     | `store shopping cart`     | string | 3 - Run   |
| `finops.org/component`   | Component                   | `database`                | string | 3 - Run   |
| `finops.org/department`  | Department                  | `retail`                  | string | 2 - Walk  |
| `finops.org/cost-center` | Cost Center                 | `acme-1001`               | string | 1 - Crawl |
| `finops.org/team`        | Team                        | `road-runner`             | string | 1 - Crawl |
| `finops.org/environment` | Environment                 | `production`              | string | 2 - Walk  |
| `finops.org/tech-stack`  | Technology Stack by Purpose | `application`             | string | 3 - Run   |
| `finops.org/customer`    | Customer Name               | `acme`                    | string | 2 - Walk  |

## Examples

To illustrate different ways to use these labels the following examples have varying complexity based on the concepts of the [FinOps Maturity Model](https://www.finops.org/framework/maturity-model/).

### Crawl

During the Crawl stage, you would be looking to implement the most basic high level labels to provide the beginning of some cost visibility within your Kubernetes infrastructure. This could be done at a high level like namespace if that works for the way you are using Kubernetes. It could also be done throughout the Kubernetes hierarchy enabling different personas to better understand the costs at different levels.

#### [namespace-crawl.yaml](./namespace-crawl.yaml)

```yaml
kind: Namespace
apiVersion: v1
metadata:
  name: acme-fitness
  labels:
    finops.org/application: acme-fitness
    finops.org/cost-center: acme-1001
    finops.org/team: road-runner
```

#### [deployment-crawl.yaml](./deployment-crawl.yaml)

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: acmefit-frontend
  namespace: acme-fitness
  labels:
    finops.org/application: acme-fitness
    finops.org/cost-center: acme-1001
    finops.org/team: road-runner
```

### Walk

The Walk stage builds on the labels that we implemented during the Crawl stage. The intent is to provide further detail about the resources thereby extending the visibility and enabling more granular reporting on costs and efficiency.

#### [namespace-walk.yaml](./namespace-walk.yaml)

```yaml
kind: Namespace
apiVersion: v1
metadata:
  name: acme-fitness
  labels:
    finops.org/application: acme-fitness
    finops.org/cost-center: acme-1001
    finops.org/team: road-runner
    finops.org/product: acme-fitness-store
    finops.org/department: retail
    finops.org/environment: production
    finops.org/customer: acme
```

#### [deployment-walk.yaml](./deployment-walk.yaml)

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: acmefit-frontend
  namespace: acme-fitness
  labels:
    finops.org/application: acme-fitness
    finops.org/cost-center: acme-1001
    finops.org/team: road-runner
    finops.org/product: acme-fitness-store
    finops.org/department: retail
    finops.org/environment: production
    finops.org/customer: acme
```

### Run

Run builds on top of the Crawl and Walk stages to provide the deepest level granularity and reporting of your Kubernetes costs across environments, resources, and personas.

#### [namespace-run.yaml](./namespace-run.yaml)

```yaml
kind: Namespace
apiVersion: v1
metadata:
  name: acme-fitness
  labels:
    finops.org/application: acme-fitness
    finops.org/cost-center: acme-1001
    finops.org/team: road-runner
    finops.org/product: acme-fitness-store
    finops.org/department: retail
    finops.org/environment: production
    finops.org/customer: acme
    finops.org/component: full stack
    finops.org/tech-stack: application
```

#### [deployment-run.yaml](./deployment-run.yaml)

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: acmefit-frontend
  namespace: acme-fitness
  labels:
    finops.org/application: acme-fitness
    finops.org/cost-center: acme-1001
    finops.org/team: road-runner
    finops.org/product: acme-fitness-store
    finops.org/department: retail
    finops.org/environment: production
    finops.org/customer: acme
    finops.org/service: frontend
    finops.org/component: frontend
    finops.org/tech-stack: application
```
