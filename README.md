# Kubernetes Reference

Cheat sheet for Kubernetes. 

## Acknowledgements

Edward Viaene: DevOps, Cloud, Big Data Specialist


## Table of Contents
1. [Intro](#intro)
1. [Containers](#containers)
1. [Glossary](#glossary)

## Intro

Kubernetes is an an open source [orchestration](#orchestration) system for [Docker](#docker) containers. 

Kubernetes lets a user schedule [containers](#containers) on a [cluster](#cluster) of machines. Multiple containers can be run on one machine. 

Long running services (i.e. Web applications) can be run on these containers. 

The states of these containers are managed by Kubernetes. It's possible to start the container on specific [nodes](#node). If a container is killed, it can be restarted. Containers have the ability to move from node to node. 

Instead of just running a few Docker containers on one host manually, Kubernetes will manage this and the containers in general. 

It's possible for Kubernetes clusters to have anywhere from one node up to thousands. 

Two prominent Docker orchestrator examples are Docker Swarm and Mesos. 

Some main advantages of using Kubernetes: 
- It can be run anywhere: privately (on-premise, in-house data center), in public (cloud, i.e. GCP, AWS), or a hybrid of both (in certain situations, it's ideal for some workloads to be stored privately on-premise and other workloads to be run on the public cloud. The same abstraction/system can be run on both platforms together for more potency. 
- Highly modular. 
- Open source. Fosters a more diverse community with more input. 
- Backed by Google. 

## Containers

### Virtual Machines vs. Containers

A computer, or host machine, can run a [server](#server), which is the physical hardware. The host [operating system](#operating-system) (OS) works on the [server](#server), and the [hypervisor](#hypervisor) works on the host OS to manage the guest OS's. Every guest OS is completely isolated and has its own binaries, libraries, and applications. 

A [virtual machine](#virtual-machine) (VM) is defined by these components bundled together: the guest OS, binaries/libraries, and applications. A VM takes up to minutes to load before it's fully live. 

A container is a considerably more lightweight version of the VM. Containers still contain the binaries/libraries and applications that a VM has, and the host OS still works on the server, but unique to the container configuration is a [Docker engine](#docker) (or other virtualization software) that manages the containers. Containers don't need to boot up the guest OS, which reduces wait time from minutes to almost instantaneously. Containers occupy a few megabytes of memory, but VMs occupy far more. 

Containers on cloud providers function a little differently than those on traditional host OS's. Cloud providers inherently use hypervisors to isolate customers, which means one or more guest OS's is mounted on the hypervisor, and the container/s on top of the guest OS. The benefits of containerization are still reaped in a cloud setting, with the extra layer of abstraction between the host OS and container. 

### Benefits of Docker

Docker allows the compartmentalization and isolation of an application and its binaries/dependencies. This prevents the common issue of an application built and running successfully on an individual machine, but not running in production; the binary and dependencies needed for the application come packaged with it. Consequently, there is a closer parity between development, QA, and production environments. Development teams are able to ship product faster. The same Docker image can be run unmodified on personal machines, data center VMs, and cloud providers. Docker uses Linux containers (a [kernel](#kernel) feature) for OS-level isolation, which means the container isn't visible to the host or guest OS. 

## Kubernetes Setup

Kubernetes should be able to run anywhere, but there are additional integrations needed for some cloud providers, like AWS and GCP; for example, [volumes](#volume) and external load balancers work only with supported cloud providers. 

[Minikube](#minikube) is a free tool that runs a single-node Kubernetes cluster inside a Linux VM. Minikube is best used for testing or development level work. It cannot spin up a production cluster, since it's a single-node machine with no high availability. DigitalOcean is a pay-to-use alternative tool that can also be used to run a single-node Kubernetes cluster on a local VM. 

Minikube automatically spins up a VM to run Kubernetes in, which means a hypervisor is needed. [VirtualBox](#virtualbox) is an example of a virtualization application that provides a hypervisor for Windows. 

kops is a tool that runs a cluster on AWS, and can be used to spin up a highly available production cluster. 

## Glossary

#### cluster

#### container

A considerably more lightweight version of the VM in terms of load time and storage. Consists of binaries, libraries, and applications seen in a virtual machine, but the guest operating system isn't required to boot. Dependent on virtualization software like Docker to be managed on top of the host OS and server. 

#### Docker
Set of [PaaS](#paas-platform-as-a-service) products developed by Docker, Inc. that uses OS-level virtualization to deliver software in packages called [containers](#container). [First mention](#intro)

Docker is the most popular container software. An alternative to Docker is 'rkt', which also works with Kubernetes. 

The Docker engine consists of the Docker [runtime](#runtime), software to run Docker images, and Docker Hub (an online service to store and fetch Docker images, and also build images online as opposed to on the host machine). 

#### kernel
Program at the core of an operating system; the part of an operating system that loads first and remains in main memory, providing basic services for all other parts of the OS. [First mention](#benefits-of-docker)

#### hypervisor
AKA virtual machine monitor, VMM. Computer software, firmware or hardware that creates and runs virtual machines or guest machines. Runs on top of the host machine and OS. [First mention](#intro)

#### minikube
Free tool that runs a single-node Kubernetes cluster inside a Linux VM. Best used for testing or development level work. Cannot spin up a production cluster, since it's a single-node machine with no high availability. Need virtualization software installed to run minikube (i.e. [VirtualBox](https://www.virtualbox.org/manual/UserManual.html#virt-why-useful)). 

#### node

#### operating system
Software that supports a computer's basic functions, such as scheduling tasks, executing applications, controlling peripherals, managing computer hardware, and software resources. [First mention](#virtual-machine)

#### orchestration
The automated configuration, coordination, and management of computer systems and software. A number of tools exist for automation of server configuration and management including Ansible, Puppet, Salt, Terraform, and AWS CloudFormation. [First mention](#intro)

#### PaaS: Platform as a Service
Category of cloud computing services that provides a platform allowing customers to develop, run and manage applications without the complexity of building and maintaining the infrastructure needed to do so. A complete development and deployment environment in the cloud, with resources that enable the ability to deliver cloud-based simple to enterprise applications. [First mention](#docker)

The platform's resources include: 
- Development tools, database management, business analytics
- Operating systems
- Servers and storage
- Networking firewalls/security
- Data center physical plant/building

#### runtime system/environment
Primarily implements portions of an execution model; in other words, the exeuction environment provided to an application or software by the operating system. 

#### server
Software or physical hardware that provides functionality for other programs or devices, called "clients". This architecture is called the client-server model. [First mention](#containers)

#### VirtualBox
Oracle VM VirtualBox is a cross-platform virtualization application. It extends the capabilities of a computer to run multiple OS's inside multiple virtual machines at the same time. As a example, Windows and Linux can run on a Mac, run Windows server 2016 on a Linux sevrer, run Linux on Windows, and so on alongside existing applications. The only practical limitations to installing as many VMs as possible are disk space, memory, and whether the computer's architecture is Intel/AMD-based or not. [First mention](#minikube)

#### virtual machine
An emulation of a computer system. Based on computer architectures and provide functionality of a physical computer. Implementations may involve specialized hardware, software, or a combination. A virtual machine (VM) or multiple VMs can be mounted on a [hypervisor](#hypervisor). Each VM consists of its own guest operating system, binaries/libraries, and applications, together which are isolated from other VMs that may be mounted on the host machine. [First mention](#containers)

#### volume
AKA logical drive. A single accessible storage area with a single file system, typically (though not necessarily) resident on a single partition of a hard disk. 