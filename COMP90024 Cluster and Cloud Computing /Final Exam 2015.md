#  Final Exam 2015

## Q1

A)

1. Network is reliable -- This is wrong, the network is unreliable. the message and data sent over the network may not arrive or may be corrupted.
2. Latency is zero -- Wrong. the message takes time to send from one place to another.
3. Bandwidth is infinite. -- Wrong. The amount of data you send 
4. The network is secure. -- Wrong. There are many security problems while transferring data among the network.
5. Transport cost is zero. The transport cost is never free.

B)

Cloud computing can provide scalability and elastic scaling, can provide easier software deploymtot. But some of the problems can not be solved, e.g. 

1. Bandwidth from user/ organization to data center can not be solved
2. Network latency is inevasible.
3. The transport cost can become cheaper but is never free
4. Using many security technique doses't means system secure. Security problems can also arise due to human negligence.
5. General assumptions that typically do not hold in the real world

## Q2

A)

1. Standardized service contract: Services adhere to a communications agreement, as defined collectively by one or more service-description documents.
2. Service loose coupling: Services maintain a relationship that minimizes dependencies and only requires that they maintain an awareness of each other.
3. Service abstraction: Beyond descriptions in the service contract, services hide logic from the outside world.
4. Service reusability: Logic is divided into services with the intention of promoting reuse.
5. Service autonomy: Services have control over the logic they encapsulate.
6. Service statelessness: Services minimize resource consumption by deferring the management of state information when necessary.
7. Service discoverability: Services are supplemented with communicative meta data by which they can be effectively discovered and interpreted.
8. Service composability: Services are effective composition participants, regardless of the size and complexity of the composition.

B)

1. Because the Cloud infrastructures are distributed, direct approach like function calls or object instantiations cannot be used. Using SOA can allow components in Cloud infrastructures to interact in a more loosely-coupled way.
2. In SOA, logic is divided into services, which can be reused.
3. Service statelessness can help minimize resource consumption.

## Question 3

A)

1. ReST allows a greater variety of data formats, whereas SOAP only allows XML  based on WSDL, which is hard to understand by human.

2. ReST is light-weight architecture. It is more of a style to use HTTP than a separate potocol. ReST requires no specific tools for writing as it is very easy to implement.
3. Coupled with JSON, which typically works better with data and offers faster parsing, ReST is generally considered easier to work with.

B)

a. A safe methods do not change the system. Repeating a call is equivalent to not making a call at all.

b. Get

c. Effect of repeating a call is equivalent to making a single call.

d. PUT

e. Post

## Question 4

A)

a. Reading and writing data in parallel. Getting a big data, split it, than handle it.

b. Perform computational tasks in parallel. Use many thread to do many things.

c. The maximum time that a program can run in the HPC.

B)

A job scheduler get jobs from the users and it chooses when and where to run the jobs, monitors their progress, and informs the user upon completion. 

Single:

```
#SPATCH --nodes=1
```

Multiple nodes (suppose 4 nodes):

```
#SPATCH --nodes=4
```

C)

A minimal necessary wall time choices can help optimize the throughput of the cluster. Also, a smaller wall-time can help reduce the queue time. But the wall-time cannot be too small. Not enough wall-time will result in program termination before it finish all the computational tasks.

D)

Task farming: like divide and conquer with master doing both split and join operation.

In single program multiple data, each process executes the same piece of code, but on different parts of the data. It is good to use when the data is huge and data in the dataset is independent to each other.

## Question 5

A)

1. Need to develop generic security solutions to avoid all application areas re-invent their own solution.
2. If the cloud allow users to compile codes that do stuff on physical/virtual machines, the cloud need to considersecurity technologies that scales to meet wide variety of applications.
3. Need to restrict access while allowing scenarios that stretch inter-organisational security.
4. Need to consider the side-effect of sharing  performance.



Technique challenge: API, trust, Single sign-on. There are many authorities in the cloud. None-technique challenge: Policy issues.

**B)**

**a. **

Federated authentication: All the organization in the federation can provice authentication to the services.

Pros:

Convenient. You can access all the distributed services by only providing your identity once to your organization.

Cons: More data secure problem may be raised. The sucurity policy is limited because the secure information it keeps is static.



**b.** 

List security challenges.

## Question 6

A)

IaaS -- Infrastructure as a Service. You have control of Application, Data, Runtime, Middleware and O/S. E.g. Amazon Web Services and Oracle Public Cloud.

PaaS -- Platform as a Service. You have control of Application and Data. E.g. Google App Engine, Microsoft Azure.

SaaS -- Software as a service -- User can only use the software inside. E.g. Gmail and Slack.

B)

Public cloud: 

​	Pros: Utility computing. Can focus on core business. Cost-effective

​	Cons: Security, Loss of control and Possible lock-in.

Private cloud:

​	Pros: Fully control. Consolidation of resources. Easier to secure

​	Cons: Need to pay staff/management overheads, Hardware obsolescence and utilisation challenges.

Hybrid cloud: 

​	Pros: Cloud-bursting: use private cloud, but burst into public cloud when needed.

​	Cons: Many complecate issues. 

C)

How do you move data/resources when needed? 

How to decide (in real time?) what data can go to public cloud? 

Is the public cloud compliant with PCI-DSS (Payment Card Industry – Data Security Standard)?



## Question 7

a.

1. Snapshot is easy. You can create it through dashboard. But the problem is that no history of how the instance is built. 
2. Scripting is harder, you have to know how to write the script. For example, if you use Ansible, you have to learn how to use it. But this gives you more control. But you get complete record of how to build and deploy the system.

b.

Snapshot: Use the dashboard (Horizon) or use openstack APIs(Nova/Glance/Swift etc) and services (Heat etc).

Scripting: Ansible scripting allows to automate software deployment includes tasks and roles.

c.

- Stage 0: **Pre-Migration** - Active VM on Host A
- Stage 1: **Reservation** - Initializa a container on the host B
- Stage 2: **Iterative Pre-copy** - Enable shadow paging, copy dirty pages in successive rounds
- Stage 3: **Stop and copy** - Suspend VM on host A, generate ARP to redirect traffic to host B, sync all remaining VM state to host B
- Stage 4: **Commitment** - VM state on host A is released
- Stage 5: **Activation** - VM starts on Host B, connects to local devices, resumes normal operation



















