#  Final Exam 2013

## Question 1

A) 

1. Grid computing is a processor architecture that combines computer (may be heterogeneous or hypogeneous) resources from various domains to reach a main objective. In grid computing, the computers on the network can work on a task together, thus functioning as a supercomputer.
2. Cluster computing is when two or more computers serve as a single resource. This improves performance and provides redundancy. Typically, the nodes in the cluster is connect via LAN which can provide low latency. 

3. Cloud computing is a model for enable ubiquitous, convenient, on-demand network access to a shared pool of configurable computing resources that can be rapidly provisioned and released with minimal management effort or service provider interaction.

B)

There are many challenges of large-scale distributed system. For example, the network is unreliable, the latency is not zero, bandwidth is finite, the network is unsecure and etc. Cloud computing can provide scalability and elastic scaling, can make software deployment easier adn can provide many tools like load balancers. However, it doesn't solve many of the problems. For example, the bandwidth from user to data center cannot be controled and secure problems caused by User's unintentional leak cannot be solved.

## Question 2

A)

Amdahl's law: The theoretical maximum speed up is determined by the non-parallelizable part. Problem always bound by limitation caused by sequential part; no matter how many cores thrown at problem will be limited to the sequential part of program. 

Challenges: Sometimes it is hard to predict the length of time required for jobs. And it assumes a fixed problem size.

B)

1. The performance vary because sometimes the tasks may get stuck in queue; Many people may using it. Not all the nodes in the cluster is identical. 

2. Provide multiple queues(Cloud & physical) dedicated to certain types of jobs. Queueing system only schedule jobs when resources free; Modules set up with main libraries installed. 
3. Load right module; Set minimal necessary wall-time. Benchmark small data then scale up to appropriately large value; Avoid demanding large scale resources. 
4. Shared facility so not just for the user and can't guarantee runs same; Benchmarking apps is hard, results varied widely. Code is different and applications are implemented in a different way.

## Question 3

A)

Only two of Consistency, Availability and Partition-Tolerance can be guaranteed at the same time. It forces us to consider trade-offs among different options.

B)

Availability, Partition-tolerance.

Availability, Consisentcy

Advantage of MapReduce: It is particularly suited to parallel computing of the Single-Instruction, Multiple-Data type. Its advantage lies in moving the process to where data are, greatly reducing network traffic. 

## Question 4

A)

Both of them use HTTP, hence can run over the web. But SOAP often run over other protocols as well.

ReST allows a greater variety of data formats, whereas SOAP only allows XML based on WSDL, which is hard to understand by human.

SOAP is built upon the Remote Procedure Call paradigm.  It is heavy-weight. Everytime you have to learn how to use the interface to interact with the server. It is a stack of protocols that covers every aspect of using a remote service, from service discovery, to service description, to the actual request/response. 

ReST is centered around resources, and the way they can be manipulated remotely. It is a light-weight architecture and is more of a style to use HTTP than a separate protocol. ReST is coupled with JSON, which typically works better with data and offers faster parsing, ReST is generally considered easier to work with.

B)

PUT is a safe method. It will not change the state of the server. Repeating calling PUT method is equivalent to not making a call at all;

POST is a neither safe nor idempotent method.

## Question 5

1. The virtualisation layer between the underlying hardware and the virtual machines and guest operating systems it supports. 

2. Allow an unmodified guest OS to run in isolation by simulating full hardware. The Guest OS has no idea it is is not on physical machine in Full virtualisation. .

3. VMM/Hypervisor exposes special interface to guest OS for better performance. Requires a modified/hypervisor-aware Guest OS.

4. A shadow page table is a pseudo-page table within a computer's main page table which allows a system to run more than one kind of operating system concurrently.

5. Hardware virtualization can lower virtualisation overheads. And Software virtualization is much simple. The VMM would manage the "shadow" page tables but this add additional management overhead.

6. Advantage: 

   1. Application containment and horizontal scalability.
   2. Can use multiple operating system environments on the same computer.
   3. When you create your virtual machine, you create a virtual hard disk. So, everything on that machine can crash, but if it does, it won’t affect the host machine.

   Disadvantage: 

   1. The vitualization itself cost resources. The guest OS and binaries can give rise to  duplications between VMs wasting server processors, memory and disk space and limitng the number of VMs each server can support.
   2. Virtual machines are less efficient than real machines because they access the hardware indirectly.  
   3. When several virtual machines are running on the same host, performance may be hindered if the computer it’s running on lacks sufficient power.

7. 

   1. Stage 0: Pre-Migration
   2. Stage 1: Reservation
   3. Stage 2: Iterative Pre-copy
   4. Stage 3: Stop and copy
   5. Stage 4: Commitment
   6. Stage 5: Activation

## Question 6

A)

1. Provide identity once and access distributed, autinimous resources.
2. Public Key Infrastructure (PKI) is a technology for authenticating users and devices in the digital world. The basic idea is to have one or more trusted parties digitally sign documents certifying that a particular cryptographic key belongs to a particular user or device.
3. A Certificate Authority (CA) (or Certification Authority) is an entity that issues digital certificates. The digital certificate certifies the ownership of a public key by the named subject of the certificate.
4. A registration authority (RA) is an authority in a network that verifies user requests for a digital certificate and tells the certificate authority (CA) to issue it.
5. An **identity provider** (abbreviated IdP or IDP) is a system entity that creates, maintains, and manages **identity** information for principals while providing authentication services to relying applications within a federation or distributed network.

B)

- Authentication
- Authorisation
- Audit
- Confidentiality
- Privacy
- Fabric management
- Trust
- Single sign-on: 
  - The Grid model needed
  - Currently not solved for Cloud-based Iaas
  - Onus is non-Cloud developers to define this
- Auditing: logging, intrusion detection, auditing of security in external computer facilities
- Deletion: 
  - data deletion with no direct hard disk
  - scale of data
- Liabiliry
- Licensing: 
  - many license models
  - challenges with the cloud delivery model

## Question 7

A)

There are many challenges of "Big data", not only the "size" problem:

1. Volume: the amount of data is huge.
2. Velocity: the frequency at which new data is being brought into the system and analytics performed is high.
3. Variety: the variability and complexity of data schema. The more complex the data schemas you have, the higher the probability of them changing along the way, adding more complexity.
4. Veracity: the level of trust in the data accuracy; The more diverse sources you have, the more unstructured they are, the less veracity you have.

B)

1. Reading and writing distributed datasets.
2. Preserving data in the presence of failing data nodes
3. Supporting the execution of MapReduce tasks
4. Being fault-tolerant
5. Coordinating the execution of tasks across a cluster



















