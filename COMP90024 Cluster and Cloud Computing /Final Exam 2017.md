# Final Exam 2017

## Question 1

A)

Gustafson's law gives the theoretical speedup in latency of the execution of a
task at fixed execution time that can be expected of a system whose resources
are improved. It propose that programmers tends to set the size of the problems
to use the avaiable equipment to solve problems within a practical fixed time.
Faster equipment available larger problems can be solved in the same time.

Gustafson's law addresses the shortcomings of Amdahl's law, which is based on
the assumption of a fixed problem size, that is of an execution workload that
does not change with respect to the improvement of the resources.

B)

22.85

C)

22.85 times faster

D)

Because in practical, we also have to consider the overheads due to
parallelization such as the cost of calling MPI methods, process communication
overhead and etc.

E)

MPI_INIT: Initiate an MPI computation.

MPI_FINALIZE: Terminate a computation.

MPI_COMM_SIZE: Determine number of processes.

MPI_COMM_RANK: Determine the current process identifier.

MPI_SEND: Send a message.

MPI_RECV : Receive a message.

## Question 2

A)

a. CouchDB

pros:

1. It guarantee partition-tolerant and availability.
2. It is a document-oriented DBMS. It can handle the high variety problem since
   it can store data in different structures including semi structures and
   unstructured data.
3. It support MapReduce which can help process a huge among of data. (To deal
   with the high volume problem)

cons:

1. Cannot guarantee consistency. Have to handle conflict.
2. Store coarse-grained data.

b. HDFS

Pros:

1. Support MapReduce which can help process a huge among of data. (To deal with
   the high volume problem)
2. It is fault tolerant.
3. It is designed to handle the high volume problem. It reduce need for memory
   to store metadata. It provide efficient use of the network and reduce need
   for seek operations on big files. It is efficient when most data of a block
   have to be processes.

Cons:

Not good at handling complex jobs.

c. Apache Spark

Pros:

1. Support MapReduce which can help process a huge among of data. (To deal with
   the high volume problem)
2. It reduce the latency inherent in the hadoop approach for execution of
   MapReduce jobs.

Cons:

Not efficient while handling simple jobs.

B)

triggers RDD evaluations: Transformations

not triggers: Actions

C)

Set the `group_level` parameter to the specific level.

For example:

```http
http://localhost:5984/exampledb/_design/example/_view/wc2 ?group_level=2&startkey=[“a”,null]&endkey=[“c”,{}]
```

## Question 3

**A)**

Services in both ROA and SOA use HTTP, hence can run over the web. But ROA has a
style of supporting ReSTful services that allows clients to interact/navigate
their functionality (HATEOS etc.). Servers of SOA often include processing of
data while servers of ROA may only provide the data and the client have to do
data processing itself.

**B)**

SOAP

pros:

1. can run over many protocols.
2. It is a stack of protocols that covers every aspect of using a remote
   service, from service discovery, to service description, to the actual
   request/response.

cons:

1. SOAP only allows XML based on WSDL, which is hard to understand by human.
2. SOAP is relatively a heavy-weight architecture. SOAP is built upon the Remote
   Procedure Call paradigm. It is heavy-weight. Everytime you have to learn how
   to use the interface to interact with the server.

ReST

pros:

1. ReST allows a greater variety of data formats
2. ReST is centered around resources, and the way they can be manipulated
   remotely. It is relatively light-weight architecture. ReST requires no
   specific tools for writing as it is very easy to implement.
3. Coupled with JSON, which typically works better with data and offers faster
   parsing, ReST is generally considered easier to work with.

cons:

1. Only support HTTP protocols. It is more of a style to use HTTP than a
   separate protocol.

**C)**

safe: The method will not change the state of the server. Repeating a call is
equivalent ot not making a call at all. (e.g. GET method)

idempotent: The effect of repeating a call is equivalent to making a single
call. (e.g. DELETE method)

## Question 4

**A)**

a.

Privileged Instructions: instructions that trap if the processor is in user mode
and do not trap in kernel mode

Sensitive Instructions: instructions whose behaviour depends on the mode or
configuration of the hardware – Different behaviours depending on whether in
user or kernel mode.

Innocuous Instructions: instructions that are neither privileged nor sensitive.

For any conventional third generation computer, a virtual machine monitor may be
constructed if the set of sensitive instructions for that computer is a subset
of the set of privileged instructions.

b.

To realize these principles. VMM needs to support:

- De-privileging -- VMM emulates the effect on system/hardware resources of
  privileged instructions whose execution traps into the VMM. Typically achieved
  by running GuestOS at a lower hardware priority level than the VMM.
- Primary/shadow structures -- VMM maintains “shadow” copies of critical
  structures whose “primary” versions are manipulated by the GuestOS. Primary
  copies needed to insure correct versions are visible to GuestOS
- Memory traces -- Controlling access to memory so that the shadow and primary
  structure remain coherent. Common strategy is to provide write-protect primary
  copies so that update operations cause page faults which can be caught,
  interpreted, and addressed.

c.

Full virtualisation: allow an unmodified guest OS to run in isolation by
simulating full hardware. (e.g. VMWare)

Para-virtualization: VMM/Hypervisor exposes special interface to guest OS for
better performance. Require a modified/hypervisor-aware Guest OS. (e.g. Xen)

d.

i.

Advantages:

- Lightweight – Many more VMs on same hardware
- Can be used to package applications and all OS dependencies into container

Disadvantages:

- Can only run apps designed for the same OS – Cannot host a different guest OS
- Can only use native file systems – Uses same resources as other containers

ii.

Docker Image is a blueprint for a container. Docker Container is a process that
behaves like an independent machine. It is a runtime instance of a docker image.

## Question 5

A)Types:

- Local: example: RCS;
  - Advantages:
    - Easy to set up
    - Cheap to run
  - Disadvantages:
    - Error prone
    - Unsafe (stored locally)
    - Not suitable for team projects
- Centralized: example: CVS;
  - Advantages:
    - Reasonably easy to set up
    - Various options (proprietary and open source)
    - Allows for file sharings amongst team members
    - Project is stored on a more reliable server (possibly cloud)
    - Admin can control the use and structure of the repository
  - Disadvantages:
    - Single point of failure (if server fails then changes will not be
      available)
    - File conflicts due to updates from different people
- Decentralized: example: Git;
  - Advantages:
    - Reliable (everyone has a copy of all versions)
    - Allows for file share amongst team members
    - Various Options available
  - Disadvantages
    - More complex to use/set up
    - Heavy on Local Storage

B)

a. Commit: `git commit` command records or snapshots the file permanently in the
version history.

b. Checkout: `git checkout` is used to switch from one branch to another.

c. Branch: `git branch` lists all the local branches in the current repository.

d. Tag: `git tag` is used to give tags to the specified commit.

e. Rebase: Rebase specializes in integrating changes from one branch onto
another.

C)

The difference between the two commands is that `clone` works to fetch code from
a remote repository, alternatively `checkout`works to switch between versions of
code already on the local system.

## Question 6

A)

a.

i. Nova: the Sompute Service -- Manages the lifecycle of compute instances in an
OpenStack environment. Responsibilities include spawning, scheduling and
decommissioning of virtual machines on demand

ii. Swift: the Object Storage Service -- Stores and retrieves arbitrary
unstructured data objects via RESTful API.

iii. Glance: the Image Service -- Accepts requests for disk or server images and
their associated metadata (from Swift) and retrieves / installs (through Nova)

iv. Keystone: the Identity Service -- Provides an authentication and
authorization service for OpenStack services. Provides a catalog of endpoints
for all OpenStack services.

b.

A researcher can create an instance through API or Dashboard(Horizon). Keystone
is responsible for verifying the identity of the researcher. The Glance will
accept requests for disk, and the snapshot and their associated metadata from
Swift and Nova will help create the instance with the snapshot. Neutron will
provide network connectivity, and Cinder will offer volumes to the instance. All
the authentication for using the resources and services talked above is granted
by Keystone.

B)

a.

Availability zones: Locations of data centers used to provide logical view for
Cloud.

b.

The volume you create in the NeCTAR must be in the same availability zone as the
instance.

## Question 7

a. One can build an SaaS over the infrastructure created by IaaS.

b.

- Snapshot

- - Benefits: easy to create snapshot and copy the state of one VM to another,
    no need to write script, easy to operate when deploying small number of VMs
  - Drawbacks: Requires mass labor work when have hundreds of instances to
    deploy. Deploying complex cloud systems requires a lot of moving parts. Easy
    to forget what software you installed, and what steps you took to configure
    the system

- Automation

- - Benefits: Provides a record of what you did, Codifies knowledge about the
    system, Makes process repeatable and programmable. It is more flexible and
    provide more control.
  - Drawbacks: Have to program and test the scripts manually. More labor work.

c.

The deployment and update of the software in the SaaS model can be automate
finished by scripting the specific tasks in the Ansible script.

(LMS: Create a playbook that contains YAML files. Typical contents include
variables, inventories and roles/tasks/templates. Inventories will include the
servers/database used for the software etc etc. Then say how you would run the
script using openrc.sh etc. Note 2 points so massive amounts of detail not
needed.)

d.

Build different template files according to the software we support in our SaaS
model. User the template-driven service(Heat) to manage the lifecycle of that
software. Besides we can still use automation tools like Chef, Ansible, or
Puppet to deploy or update our software as well since Heat can be integrated
with them.

(LMS: This was shown in the lecture directly (see week 8.2 and slides 19-21))
