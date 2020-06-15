#  Final Exam 2013

## Question 1

A)

Major trends in research and research computing over the last 20 years that have led to the Cloud computing

1. The pre-internet era (60s to 80s) Focus: send data
2. Mid 90s: Focus application to application communication
3. The web era. The initial scale up.
4. The Grid dream (00s)
5. Web services (10s)
6. The advent of Cloud Computing(10s)

（LMS Discussion Board)

You should also include the "research" and research computing part too in the question, e.g. we are now generating more data than ever and it needs to be stored, processed and we need larger scale infrastructures to support this in a flexible manner etc etc.

B)

?

C)

Idempotent: effect of repeating a call is equivalent to making a single call.

Example: Put method.

## Question 2

a.

Yes, there are many kind of cloud computing for different purposes. 

i.

Depending on the deployment models, there are public cloud, private cloud and hybrid cloud. 

Public cloud is cost-effective and can help companies focus on there core business without worry about budilding infrastructure. It is elastic and can provide you the right size. But there will be more security problem in public cloud. There will be less control and you may be possible lock-in by the cloud provider.

Private cloud can provide you more control. You can protect your sensitive data more easily. But the problem is that you have to pay the staff/management overheads and the hardware you bought will face the problem of obsolescence. And there will be over or under utilisation challenges.

Hybrid clouds can provide more feasibility and can help solve the utilisation problem in private cloud while maintain the advantage of it. But it is harder to build and the strategy to  transfer data between public and private cloud is difficult to design.

ii.

Depending on the delivery model, there are different flavours of “X as a Service (XaaS)”. 

IssA is cost saving and can provide on-demand scalability. However, you only g et the infrastructure, you still have to build and update the software yourself. Also, you have to consider security problem since you don't have any control of the hardware.

- Pros: flexibility and customization 
- Cons: have to manage a lot of the IT stack

PaaS can save you time and money. You don't have to maintain, upgrade, or replace systems and software. But the problem is that not even part of your company's existing infrastructure may be built for the cloud. Data security problem still need to be considered.

- Pros: The benefits of PaaS are very similar to the benefits of IaaS, but PaaS requires less time and skill for management
- Cons: PaaS, like IaaS, can result in unpredictable charges, particularly as applications scale. It offers less flexibility, less customer control and more potential for vendor lock-in than IaaS. 

SaaS:

- Pros: ease of use
- Cons: IT has little or no control

b.

LMS:

Most major cloud interoperability challenges are related to vendor lock-in and lack of standardization (which can be used to lock in customers). Some practical examples are:

- Many Cloud providers don’t use standardized APIs to access their services, making it difficult to communicate with them and port infrastructure or applications to other providers.
- Many Cloud providers push their own internal formats for mission-critical aspects of cloud interoperability like the packaging of virtual machines.
- Providers difficult porting data efficiently (and cheaply) out of their control.
- On the policy side, the ownership of the data is sometimes not clear with cloud providers, putting an additional barrier for moving data out of the provider.
- Lack of single security solution (single sign-on and lack of single CA) and what data can go between clouds, e.g. what is private/public data etc.

## Question 3

A)

Flynn's Taxonomy is about computer architectures. There are four architectures in it: SISD, SIMD, MISD and MIMD.

1. Single Instruction, Single Data Stream (SISD)
2. Single Instruction, Multiple Data Stream (SIMD)
3. Multiple Instruction, Single Data Stream (MISD)
4. Multiple Instruction, Multiple Data Stream (MIMD)

It provide architectures that can be used in HPC servers. HPC server can use MIMD architecture to provide computing resources. Number of processors in the HPC function asynchronously and independently. At any time different processors may be executing different instructions on different pieces of data. Machine can be shared memory or distributed memory categories. Also the SIMD architectures can improve performance of multimedia use such as for image processing.

B)

It allows us to use `#SBATCH --nodes=N` to utilize multiple nodes.

C)

1. The accuracy of the wall-time estimate can help optimize the throughput of the Edward cluster.
2. A smaller wall-time can help reduce a user's queue time.
3. If the wall-time is not enough, the program will be terminated before it finishes.

## Question 4

A)

Gustafson's law gives the theoretical speedup in latency of the execution of a task at fixed execution time that can be expected of a system whose resources are improved. Gustafson's law addresses the shortcomings of Amdahl's law, which is based on the assumption of a fixed problem size, that is of an execution workload that does not change with respect to the improvement of the resources.

B)

128 - 12  = 116

12 + 32 * 116 = 3724

3724 / 128 = 29.1

C)

29.1 times faster

D)

Overheads due to parallelisation, e.g. loops, communications, variables introduced to deal with parallel aspects

Because in practical, we also have to consider the overheads due to parallelization such as the cost of calling MPI methods, process communication overhead and etc.

## Question 5

A)

advantage

When the data is distributed, there will be partion problem. No SQL save coarse-grained data, which is more conductive to partition-tolerance than the fine-grained data in relational database.

Because we can use document to save data, we can save heterogeneity of data.

Using MapReduce to access or process the data in large scale is effective.

disadvantage

Not like traditional databases which is good for ensuring consistency, noSQL databases such as couchDB may not guarantee consistency in case of cluster partition. There will be conflict once the partition is solved if some concurrent requests with the same revision number is sent to the two partitioned nodes. 

B)

a.

HDFS is a fault tolerant file system that has been explicitly designed to span many nodes. It play a core role in Hadoop. A HDFS file is a collection of blocks stored in datanodes, with metadata stored in namenodes. It reduce the need for memory to store metadata, provide more efficient use of the network, reduce need for seek operations on big files and is efficient when most data of a block have to be processed.

b.

The core of Hadoop is a fault tolerant file system that has been explicitly designed to span many nodes

HDFS also maintains the replication factor by creating replica of data on other available machines in the cluster if suddenly one machine fails.

In Hadoop Failure of one node doesn’t affect accessing (read-write operation) of data in datanode. Multiple copies of same Block will be available in other datanode, So failure of one node will not impact our work and we can make use of block from other datanode when one of the datanode(slaves) fails.

## Question 6

a.

Federated authentication: All the organization in the federation can provide authentication to the services.

Single sign-on: Provide identity once and access distributed, autonomous resources. With this property, a user logs in with a single ID and password to gain access to any of several related systems. 

b.

PKI help Internet2 Shibboleth model to authenticate its users and devices in the digital world. The trust is provided by the Certification Authority and certifies the ownership of a pulic key by the named subject of the certificate.

c.

advantages:

Convenient. You can access all the distributed services by only providing your identity once. 

disadvantage:

More data secure problem may be raised. The security policy is limited because the secure information it keeps is static.

d.

The more general access provided, the more security problem may raised. Talk about the challenge of security.

## Question 7

A)

a.

The virtualization layer between the underlying hardware and the virtual machines and guest operating systems it supports.

b.

A representation of real machine using hardware/software that can host a guest operating system

c.

Machine image: A snapshot that can be used to build a virtual machine with specific Guest OS, software and environment.

d.

Object store: It is a computer data storage architecture that manages data as objects. It store arbitrary unstructured data objects.

e.

Volume store: Volume Store provide persistent volume storage to virtual machines and spports creation and management of volume storage devices.

f.

Key-pair: Key-pair is a concept in asymmetric cryprography. A key pair contains a publick key and a private key. The key-pair is complementary, but one can not find out the value of private key from public key.

B)

a.

Through snapshots:

pros: Easy. You can create it through dashboard. Less control.

cons: No record of how the instance is built.

Through Scripting:

pros: Have more control. Complete record of how to build and deploy the system.

 cons: Harder. Need to learn how to write the script.

b.

Snapshot: Openstack APIs(Nova/Glance/Swift etc) and Services(Heat etc).

Scripting: Ansible scripting allows to automate software deployment includes tasks/roles.

















