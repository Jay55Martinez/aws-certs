# 01 — Foundations: Introduction to the Cloud

## Client–Server Model

In the **client–server model**, a client sends a request to a server, and the server processes the request and sends back a response.

```text
Client                         Server
  |                               |
  | -------- Request -----------> |
  |                               |
  | <------- Response ----------- |
  |                               |
```

- **Client:** An application or device that requests a service or resource.
- **Server:** A system that receives requests and returns data or performs operations.

## Cloud Computing

**Cloud computing** is the on-demand delivery of IT resources over the internet, typically with pay-as-you-go pricing.

Instead of purchasing and maintaining all your own hardware, you can use computing, storage, databases, networking, and other services from a cloud provider such as AWS.

### Deployment Types

| Type | Description |
| --- | --- |
| **Cloud** | Resources hosted and managed through a cloud provider. |
| **On-premises** | Infrastructure operated in an organization's own facilities. |
| **Hybrid** | A combination of cloud and on-premises infrastructure. |

## Six Main Benefits of AWS Cloud Computing

1. **Variable costs:** Pay for resources as you use them instead of making large upfront investments.
2. **Economies of scale:** Benefit from AWS's large-scale infrastructure and purchasing power.
3. **Elastic capacity:** Increase or decrease resources to match demand.
4. **Speed and agility:** Provision and deploy resources quickly, then scale as needed.
5. **Reduced data-center management:** Spend less time buying, operating, and maintaining physical infrastructure.
6. **Global reach:** Deploy applications in multiple geographic locations around the world.

## AWS Global Infrastructure

AWS operates data centers around the world to provide resilient and highly available services.

- **Region:** A geographic area containing multiple Availability Zones (AZs).
- **Availability Zone (AZ):** One or more physically separate data centers with redundant power, networking, and connectivity.
- **High availability:** Designing systems to remain accessible even when individual components fail.

Deploying workloads across multiple AZs helps protect against failures affecting a single AZ. **Redundancy improves availability but does not guarantee 100% uptime.**

## AWS Shared Responsibility Model

AWS and the customer share responsibility for security:

| AWS: Security **of** the Cloud | Customer: Security **in** the Cloud |
| --- | --- |
| Physical data centers and hardware | Data and access permissions |
| Underlying infrastructure and networking | IAM users, roles, and policies |
| Infrastructure that runs AWS services | Application configuration and security |

The exact responsibilities vary by service. For example, AWS manages more of the underlying infrastructure for a managed service like Lambda than for an EC2 instance.

## Cloud in Real Life

Cloud computing powers everyday applications such as streaming, online storage, websites, and mobile applications. These services can use cloud infrastructure to handle changing demand, serve users across regions, and reduce the need to operate their own data centers.

---

## Key Takeaways

- Clients send **requests**; servers return **responses**.
- Cloud computing delivers IT resources **on demand over the internet**.
- Deployment models include **cloud, on-premises, and hybrid**.
- AWS provides **elasticity, speed, variable pricing, and global infrastructure**.
- Multiple **Availability Zones** support fault tolerance and high availability.
- AWS secures the infrastructure **of** the cloud; customers secure their workloads and data **in** the cloud.
