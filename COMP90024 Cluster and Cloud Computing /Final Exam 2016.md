# Final Exam 2016

## Question 1

A)

There are many fundamental challenges associated with large-scale distributed
systems. For example:

1. The network is unreliable.
2. The latency is inevasible.
3. The bandwidth is finite
4. There are many administrator.
5. The network is unsecure.
6. Time is not ubiquitous.
7. The topology will change.
8. Transport cost is not zero.

Cloud computing cannot address many of the above. Many of them are inevasible.
For example, the bandwidth from the user/organization to the data centre is not
set by the cloud provider.

B)

The emergence of ReET-based Web Services provide a light-way architecture for
the services in a cloud. It help the services in the cloud cooperate with each
other in a more loose-couple way.

## Question 2

A)

Gustafson's law gives the theoretical speedup in latency of the execution of a
task at fixed execution time that can be expected of a system whose resources
are improved. Gustafson's law addresses the shortcomings of Amdahl's law, which
is based on the assumption of a fixed problem size, that is of an execution
workload that does not change with respect to the improvement of the resources.

B)

7.3

C)

7.3 times faster than...

D)

Because in practical, we also have to consider the overheads due to
parallelization such as the cost of calling MPI methods, process communication
overhead and etc.

## Question 3

A) high volume,high velocity and high variety (heterogeneity)

a. CouchDB is good for big data. It is a document-oriented DBMS which stores
data as structured documents. It can store documents in different structures
which is good for handling the heterogeneity problem in big data. It is good for
ensuring availability and partition-tolerance. Also, it support MapReduce
queries, which can help do parallel computing on the big data.

b. HDFS is a fault tolerant distributed file system in Hadoop. The block of it
is much larger than blocks used by an ordinary file system. So, it reduce the
need for memory to store matadata when facing the high volume problem in big
data. It is efficient when most data of a block have to be processed. It reduce
the need for seek operations on big data. Also, it support MapReduce jobs and it
work well on simple jobs on large datasets.

c. Apache Spark provide MapReduce which is geared towards performing relatively
complex jobs on large datasets. It is designed to reduce the latency inherent in
the Hadoop approach for execution of MapReduce jobs.

Veracity: the level of trust in the data accuracy

## Question 4

A)

SOA is oriented at services. A service is more processing. The application built
with a SOA combines or composes its outgoing functionality based on
functionality that is in the services. The core processing consists of calling
external services, supplying them with parameters and combining the results with
possibly some extra processing or algorighms for the users. A SOA server is more
heavy-weight than ROA. It have to process the data and provide interface for
other to access its functions. Others need to understand how to use the
interfaces of the SOA server to interact with it.

ROA is oriented at resources. A resource is more static data. An application
built with a Resource Oriented Architecture does more of its processing
internally but uses external resources as input. A ROA server is more
light-weight than SOA. Client can use simple HTTP methods to interact with it.

B)

ReST:

Pros: Allow a greater variety of data formats. ReST is coupled with JSON, which
typically works better with data and offers faster parsing. It is generally
considered easier to work with.

Cons: Can only run on HTTP protocols.

SOAP:

Pros: Support many potocols. It can cover every every aspect of using a remote
service. from service discovery to service description to the actual
request/response.

Cons: It is relatively heavy-weight. Only support XML based on WSDL, which is
hard to understand by human.

C)

Safe: Do not change the state of the server. Repeating a call is equivalent to
not making a call at all. e.g. GET method

Idempotent: Effect of repeating a call is equivalent to making a single call.
e.g. DELETE method.

## Question 5

A)

a.

privileged Instructions: instructions that trap if the processor is in user mode
and do not trap in kernel mode.

sensitive instructions: instructions whose behavior depends on the mode or
configuration of the hardware. They will have different behaviours depending on
whether in user or kernel mode.

Innocuous Instructions: instructions that are neither privileged nor sensitive.

For any conventional third generation computer, a virtual machine monitor may be
constructed if the set of sensitive instructions for that computer is a subset
of the set of privileged instructions

b.

VMM emulates the effect on system/hardware resources of privileged instructions
whose execution traps into the VMM.

Typically achieved by running GuestOS at a lower hardware priority level than
the VMM.

Problematic on some architectures where privileged instructions do not trap when
executed at de-privileged level.

c.

Full virtualisation – allow an unmodified guest OS to run in isolation by
simulating full hardware – Guest OS has no idea it is not on physical machine

e.g. VMWare

Para-virtualisation – VMM/Hypervisor exposes special interface to guest OS for
better performance. Requires a modified/hypervisor- aware Guest OS. Can optimise
systems to use this interface since not all instructions need to be
trapped/dealt with

e.g. Xen

d.

VMM needs to support primary/shadow structures. VMM maintains "shadow" copies of
critical stuctures whose "primary" versions are manipulated by the GuestOS, e.g.
memory page tables. Primary copies needed to insure correct versions are visible
to GuestOS.

Also, it needs to support Memory traces, it provides controlling access to
memory so that the shadow and primary structure remain coherent. The common
strategy is to write-protect primary copies so that update operations cause page
faults which can be caught, interpreted, and addressed.

## Question 6

A)

1. Single sign-on: Provide identity once and access distributed, autonomous
   resources. With this property, a user logs in with a single ID and password
   to gain access to any of several related systems.
2. Federated authentication: All the organization in the federation can provide
   authentication to the services.
3. Authorization: Authorization is concerned with controlling access to
   resources based on policy.
4. Certification authority: A Certificate Authority (CA) (or Certification
   Authority) is an entity that issues digital certificates. The digital
   certificate certifies the ownership of a public key by the named subject of
   the certificate.
5. Identity Provider: An identity provider (abbreviated IdP or IDP) is a system
   entity that creates, maintains, and manages identity information for
   principals while providing authentication services to relying applications
   within a federation or distributed network.

B)

(answer should be AAAA and trust, confidentiality, privacy etc )

There many challenges in supporting finer-grained security in hybrid Cloud
environment.

1. When it comes to data security. It is very hard to decide what data can go to
   the public cloud in real time. Have to make sure the security policy of the
   public cloud is suitable to save the data we store in it.
2. How to move data between private cloud and public cloud will be a problem.
3. Finer-grained security is very hard to achieve. Many challenges like
   authentication, authorisation, auditing, confidentiality, privacy and trust
   need to be considered.
4. If finer-grained security policy contains single sign-on. we also have to
   make sure all the organization have the same level security policy.

## Question 7

A)

a.

1. Nova: Compute service of NeCTAR. Manages the lifecycle of compute instances
   in an OpenStack environment – Responsibilities include spawning, scheduling
   and decommissioning of virtual machines on demand

2. Swift: Object Storage service of NeCTAR. Stores and retrieves arbitrary
   unstructured data objects via RESTful API. Fault tolerant with data
   replication and scale-out architecture.

   - Available from anywhere; persists until deleted

   - Allows to write objects and files to multiple drives, ensuring the data is
     replicated across a server cluster

   Can be used with/without Nova/compute

3. Glance: Image service of NeCTAR. Accepts requests for disk or server images
   and their associated metadata (from Swift) and retrieves / installs (through
   Nova)
4. Keystone: Identity Service of NeCTAR. Provides an authentication and
   authorization service for OpenStack services. Tracks users/permissions –
   Provides a catalog of endpoints for all OpenStack services. Each service
   registered during install. Know where they are and who can do what with them.
   Control project membership.

b.

The researcher can use either API or Dashboard (supported by Horizon) to create
an instance. First, Keystone will check the researcher's identity and provide
him authrization to other services. He get the snapshot from Glance which get
the image files from Swift. Then Nova create the instances for the researcher
using the snapshot. The network connectivity of the instances is provided by
Neutron. If the researcher also need to attach volume to its instances, he can
get the volumes from Cinder.

B)

Locations of data centers used to provide logical view of Cloud.

b.

The volume you create in the NeCTAR must be in the same availability zone asa
the instance.
