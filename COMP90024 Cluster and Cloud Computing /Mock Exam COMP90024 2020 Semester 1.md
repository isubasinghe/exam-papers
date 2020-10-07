# Mock Exam COMP90024 2020 Semester 1

## Question 1

A.) In the context of distributed databases, explain the concepts of:

Consistency [1] Availability [1]
B.) Give an example of a database technology that supports Availability in the
presence of a (network) partition. [1]

C.) In the context of CouchDB clusters what is the meaning of:

Replica number [1] Number of shards [1] Read quorum [1] Write quorum [1] D.)
Describe the three different Apache SPARK runtime modes:

Local [1] Cluster [1] Client [1]

### Answer

A)

1. Consistency: In distributed databases, consistency means that no matter which
   nodes in the database cluster a node sends requests to, it will get the same
   answer.

2. Availability: Client can access the distributed database from any nodes in
   the cluster

B)

MVCC (Multi-Version Concurrency Control)

C)

1. The number of copies of the same shard kept in the cluster.

2. The number of "horizontal" partitions of a database

3. Minimum number of node that have to give the same result to a read operation
   for it to be declared valid and sent back to the client.

4. Minimum number of nodes that have to concur on a write operation for it to be
   accepted

D)

1. In local mode, every Spark component runs within the same JVM. Local mode is
   good when developing/debugging.

2. In cluster mode, every component, including the driver program, is executed
   on the cluster. This is the common way of running non-interactive Spark jobs.

3. In client mode, the driver program talks directly to the executors on the
   worker nodes. Client mode must be used when the applications are interactive,
   as happens in the Python or Scala Spark shells.

## Question 2

A) The NeCTAR Research Cloud is based on the OpenStack technology. Describe the
role and features of the following OpenStack components: Nova [1] Horizon [1]
Heat [1] Glance [1] Swift [1] Keystone [1] Neutron [1] B) Describe the interplay
between these components that allows a researcher to create an instance of a
virtual machine through a pre-existing snapshot from a non-public NeCTAR Cloud
image, e.g. a snapshot created by a user. [3]

### Answer

A)

1. Nova provides the Compute service of NeCTAR. It is responsible for managing
   the lifecycle of compute instances in an OpenStack environment.
   Responsibilities include spawning, scheduling, and decommissioning of virtual
   machines on demand.

2. Horizon provides the Dashboard service of NeCTAR. It provides a web-based
   self-service portal to interact with underlying OpenStack services.

3. Heat provides orchestration service of NeCTAR. It provides template-driven
   service to manage the lifecycle of applications deployed on Openstack.

4. Glance provides the image service of NeCTAR. It accepts requests for disk or
   server images and their associated metadata (from Swift) and
   retrieves/installs (through Nova).

5. Swift provides the Object Storage service of NeCTAR. It stores and retrieves
   arbitrary unstructured data objects via RESTful API. It is fault-tolerant and
   can be used with/without Nova/compute.

6. Keystone provides the Identity service of NeCTAR. It provides an
   authentication and authorization service for OpenStack services and provides
   a catalog of endpoints for all OpenStack services.

7. Neutron provides the Networking service of NeCTAR. It provides a web-based
   self-service portal to interact with underlying OpenStack services, such as
   launching an instance, assigning IP addresses and configuring access
   controls. It is based on Python/Django web application.

B)

First the user login to NeCTAR through Keystone. Then he interacts with the
dashboard provided by Horizon. He gets the snapshot through the Image Service,
Glance, which gets the snapshot file from Swift. Then the Glance returns the
snapshot image to the Nova. Novacreate the virtual machines for the user. If the
user needs volumes, the Cinder will provide the volume for the user. The network
setting of the virtual machine with the snapshot is managed by Neutron. Since
the snapshot is a non-public NeCTAR, the Keystone would check the user's
identification and grant access for the user to the snapshot and all the servers
mentioned above (Authorization process).

## Question 3

A) Describe some of the current challenges associated with large-scale
distributed systems. [4]

B) Cloud computing solves some of these issues but not all. Explain. [4]

C) What are availability zones in NeCTAR and what restrictions do they impose on
NeCTAR Cloud-based application developers? [2]

### Answer

A)

1. The network is unreliable. The messages used to communicate between nodes may
   not arrive.

2. Latency problem. Systems distributed in different locations have to have
   latency issues. In a system with many nodes, each link can have different
   latencies.

3. Bandwidth is finite. The speed of transferring huge data can be limited by
   bandwidth.

4. The network is insecure. Communication between nodes may not be secure.

B)

The network security problem is solved technically. However, the security
problem caused by the user's unintentional leakage cannot be solved.

Although the network latency is getting lower and lower as technology advances,
it cannot be eliminated

According to CAP theory, it is i mpossible to satisfy all of the three
properties. For example, the CouchDB cluster guarantees availability but the
network partition problem would still cause consistency problems.

C)

Locations of data centres used to provide logical view of Cloud. The volume you
create in the NeCTAR must be in the same availability zone as the instance.

## Question 4

A) Explain Amdahl's law and discuss the challenges of its practical
implementation. [2] B) The actual performance as experienced by users of
shared-access HPC facilities such as the Edward cluster at the University of
Melbourne can vary – where here performance can be considered as the throughput
of jobs, i.e. from the time of first job submission to the time of last job
completion. Explain why this can happen. [2] C) Explain how the Edward cluster
has been set up to minimize this. [2] D) Explain what users can do to optimize
their throughput (use) of the Edward cluster. [2] E) Describe some of the
challenges with application benchmarking on HPC facilities. [2]

### Answer

A)

The theoretical maximum speed up is determined by the non-parallelizable part.
Challenge: It assumes a fixed problem size. Sometimes it is hard to predict the
length of time required for jobs.

Problem always bound by limitaton caused by sequential part; no matter how many
cores thrown at problem will be limited to the sequential part of program. Also
includes overheads required to deal with parallelism (loops, variables, comms
etc )

B)

Depending on different priorities and the load of the server, the queuing time
is different.

Stuck in queue; Overall usage of facility, e.g. I/O or node load; not all nodes
identical; the way code is written; the nature of the application itself.

C)

Multiple queues (cloud, physical) dedicated to certain types of jobs. Queueing
system to only schedule jobs when resources free; Modules set up with main
libraries installed, etc.

D)

Load right modules; wall time choices (minimal necessary); benchmark small data
then scale up to appropriately large value; avoid demanding large scale
resources

E)

Shared facility so not just for the user and can't guarantee runs same;
benchmarking apps hard anyway(results varied widely). Maybe mention
Linpack(Top 500) is a fixed set of algorithms that don't reflect real world app.

## Question 5

A) Applications can be deployed across Clouds either through creation and
deployment of virtual images (snapshots) or through scripting the installation
and configuration of software applications.

1. What are the benefits and drawbacks of these approaches? [3]
2. Discuss the mechanisms used to support these approaches. You may refer to
   specific tools used to support these processes on the NeCTAR Research Cloud.
   [3]
3. Container based solutions such as Docker have advantages and disadvantages
   compared to traditional Cloud-based virtualization solutions based upon
   hypervisors. Discuss. [4]

### Answer

1. Snapshot is easy. You can create it through dashboard. But the problem is
   that no history of how the instance is built. Scripting is harder, you have
   to know how to write the script. For example, if you use Ansible, you have to
   learn how to use it. But this gives you more control. But you get complete
   record of how to build and deploy the system.
2. openstack APIs(Nova/Glance/Swift etc) and services (Heat etc). Ansible
   scripting allows to automate software deployment includes tasks/roles.
3. Guest OS; Communication; Security; Performance; Isolation; Startup time;
   Storage

## Question 6

A) What are container orchestration technologies? What are the main benefits of
using container orchestration tools? Name two of the most popular Docker
orchestration tools? [3] B) A researcher wants to attach to an already running
Postgresql container and list all of the databases it contains. The command to
list all of the database is psql -U postgres -c “\l”. The name of the container
is postgres and it exposes the port 5432 to the host. Is the following command
correct? If not, please correct it:

`docker exec -p 5432 --name postgres sh -c psql -U postgres -c “\l”` [3]
C) The following Docker compose file starts two Docker containers that are used
to run a WordPress website. What are the equivalent Docker commands that could
be used to start these two containers individually? [4]

### Answer

Container orchestration technologies provides a framework for integrating and
managing containers at scale.

Benefits:

- Simplify container management processes
- Help to manage availability and scaling of container.

Docker SWARM, Kubernetes

`docker exec -t postgres sh psql -U postgres -c “\l”`

```dockerfile
version: '3.6'

services:

 wordpress:

   image: wordpress

   restart: always

   ports:

     - 8080:80

   environment:

     WORDPRESS_DB_HOST: database

     WORDPRESS_DB_USER: wordpress

     WORDPRESS_DB_PASSWORD: wordpress

     WORDPRESS_DB_NAME: wordpress

 database:

   image: mysql:5.7

   restart: always

   environment:

     MYSQL_DATABASE: wordpress

     MYSQL_USER: wordpress

     MYSQL_PASSWORD: wordpress

     MYSQL_ROOT_PASSWORD: P@ssw0rd

   volumes:

     - /data/mysql:/var/lib/mysql
```

## Question 7

A) In the context of Cloud, what is meant by serverless computing? [1] B) List
three reasons why it may be beneficial to choose a serverless solution. [3] C)
Discuss the role of functions in serverless computing. Your answer should
include key properties of functions that make them suitable for serverless
environments. [3] D) OpenFaaS is an open source framework that can be used to
deliver serverless computing solutions. Discuss the role of container
technologies such as Docker in OpenFaaS and their relationship with functions
and how they might be used to support auto-scaling. [3]

### Answer

A)

A way of developing application as collections of functions that are deployed on
a computing infrastructure without the need to manage it.

B)

Ease of deployment

Economics (computing time is billed only when functions are executed)

Reduced complexity due to the loosely-coupled infrastructure.

C)

Serverless applications are composed of functions

Functions in serverless computing are: free of side-effects, ephemeral,
stateless (making them ideal for parllel execution and scaling). Function can be
triggered by events; Functions can call each other

D)

In OpenFaaS every function is a Docker container, and when the load increases,
OpenFaaS fires up more containers executing the same function. (When the load
decreases, some containers are stopped).
