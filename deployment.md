# Deployment

## Container and Deployment Overview

A **container** is a running piece of software that bundles code along with all of its dependencies, including system tools, libraries, or configuration files. Building your application in a container allows the application to run consistently in any environment, whether that environment is another computer's operating system or cloud deployment.

**Deployment** is the process of making an application run in the production environment. Deployment can be done manually or can be automated. Kubernetes is a container orchestration system that automates container deployment, scaling, and management and will be used in this course.

Two ways of bundling an application with its environment and dependencies are:

Containers and
Virtual machines (VMs).

### What is a Container?

OS level virtualization allows us to run multiple isolated processes in parallel. A container is an isolated process that consists of the following items, all bundled into one package:

- the application code,
- the required dependencies (e.g. libraries, utilities, configuration files), and
- the necessary runtime environment to run the application.
  Each container is an independent component that can run on its own and be moved from environment to environment.

### Benefit of Containers

- Containers make it easier for developers to create, deploy, and run applications on different hardware and platforms, quickly and easily.
- Containers share a single kernel and share application libraries.
- Containers cause a lower system overhead as compared to Virtual Machines.
  How to create containers?
  Several platforms (called Container runtime/engines) allow us to create containers. Some common Container runtime/engines are:

- Docker - A standardized packaging format for diverse applications
- CRI-O - Lightweight container runtime for Kubernetes
- OpenVZ - Open source container-based virtualization for Linux
- Containerd - Container runtime with an emphasis on simplicity, robustness, and portability
- Rkt - An application container engine developed for modern production cloud-native environments
- LXC and LXD - A distro and vendor-neutral environment for the development of Linux container technologies
  Docker is the most popular one and hence, in this course, you will learn to create containers using the Docker engine.

### Containers vs VMs

#### What is a VM?

A VM is like a complete computer, with its own copy of an operating system and virtual hardware. Just as with containers, a single physical machine (the host machine) can run many virtual machines to scale the number of isolated applications. While virtual machines work well for scaling applications, since they virtualize an entire machine, they can be resource-intensive. This is where containers can be an improvement.

- **How multiple VMs are managed on a host machine?**
  Each VM has a complete OS, and multiple VMs can run on the same host. The host operating system runs the VMs using a hypervisor, which is special software that creates and manages the VMs. The hypervisor maintains the isolation of the VMs with each other.
- **How multiple containers are managed on a host machine?**
  Containers bundle together an application with its dependencies. Unlike VMs, containers do not have a separate OS or virtualized hardware. They share a single operating system kernel. In practice, the containers are managed by a container manager, which serves a role analogous to the hypervisor in a VM scenario.

#### How to create VMs?

If you want to create a VM (a complete computer) locally, you can use either of the following software (called Hypervisors):

- Microsoft Hyper-V
- Oracle VM VirtualBox
- VMWare
- Parallels Desktop
  We will not get into the details and types of hypervisors because it is beyond this course's scope. Also, most of the cloud service providers offer you to create VM on their infrastructure, such as:

- AWS EC2
- GCP Compute Engines
- Azure Virtual Machines
  Creating VMs is also beyond the current course's scope, but it is important to understand the relative difference between a container and a VM.

Just as with containers, a single physical machine (the host machine) can run many virtual machines to scale the number of isolated applications.
