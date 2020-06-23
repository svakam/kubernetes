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

Instead of just running a few docker containers on one host manually, Kubernetes will manage this and the containers in general. 

It's possible for Kubernetes clusters to have anywhere from one node up to thousands. 

Two prominent Docker orchestrator examples are Docker Swarm and Mesos. 

Some main advantages of using Kubernetes: 
- It can be run anywhere: privately (on-premise, in-house data center), in public (cloud, i.e. GCP, AWS), or a hybrid of both (in certain situations, it's ideal for some workloads to be stored privately on-premise and other workloads to be run on the public cloud. The same abstraction/system can be run on both platforms together for more potency. 
- Highly modular. 
- Open source. Fosters a more diverse community with more input. 
- Backed by Google. 

A computer, or host machine, can run a [server](#server), which is the physical hardware. The host [operating system](#operating-system) (OS) 

## Containers



## Glossary

#### cluster

#### container

#### Docker
Set of [PaaS](#paas-platform-as-a-service) products developed by Docker, Inc. that uses OS-level virtualization to deliver software in packages called containers. [First mention](#intro)

#### hypervisor
AKA virtual machine monitor, VMM. Computer software, firmware or hardware that creates and runs virtual machines or guest machines. Runs on top of the host machine and OS. 

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

#### server
Software or physical hardware that provides functionality for other programs or devices, called "clients". This architecture is called the client-server model. 

#### virtual machine
An emulation of a computer system. Based on computer architectures and provide functionality of a physical computer. Implementations may involve specialized hardware, software, or a combination.  a server (the physical machine), which has a host [operating system](#operating-system)