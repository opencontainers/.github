---
layout: default
title: Container Images
nav_order: 2
parent: Introduction
---

# Introduction to Containers

A container is a portable encapsulation of an environment [1]. 
It's a way for you to package an entire operating system, libraries, and software into a package that you can move and run anywhere.
That is the quick and dirty definition, but today we are going to delive a little more into what this actually means.

{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## Container Basics

### What problems do containers solve?


#### Reproducibility
{: .no_toc }

We have differences in environments, hardware, and even security, and this makes sharing of applications challenging. 
A *reproducible* workflow that uses containers helps us get around this problem, and (hopefully) reduce the frequency of uttering the phrase _But it ran on my computer!_

#### Portability
{: .no_toc }

The ability to easily move a container from one machine to another is easily afforded by the fact that many container formats are variations on a compressed filesystem. 
If you wanted to share your entire computer, right now, you would have a hard time doing that.

#### Development Environments
{: .no_toc }

It used to be the case that to develop a simple model - view - control (MVC) application with some application, database, and web server, you would need to install and run the components on your host. 
It would be very challenging to work on multiple projects at once, because different projects might have different dependencies.
Containers are essential for developers because they allow us to spin up an entire set of components for a specific development environment, and then bring it down just as easily.

#### Continuous Integration
{: .no_toc }

The same is true for testing, using containers one can easily test across operating systems from a single host.

#### Flexible
{: .no_toc }

The technologies that we use must be flexible to change. 
The resources that we invest in are ephemeral, and change is unavoidable. 
For a concrete example. let's say you are running a complex (containerized) application on a cloud provider. 
The costs of the provider changes, and you need to do a quick switch! 
Since your application is containerized, you can easily change providers.
You aren't forced becoming locked into a cloud vendor. You are a free container whale!

#### Isolation
{: .no_toc }

While the level of isolation can vary based on the container technology, containers generally allow you to isolate an application or component from your host. 
This is incredibly useful if you have packages with conflicting dependencies that need to run on the same host. 

## Virtualization
{: .no_toc }

You might be familiar with the idea of a [virtual machine](https://en.wikipedia.org/wiki/Virtual_machine) (VM), which was, for some of us, our first foray into virtualization. In a bucket:

 - A hypervisor is based on emulating hardware. 
 - When we emulate hardware, this is called virtualization.

While the term "virtual machine" is used in different contexts and can spawn much disagreement about its definition, for the time being let's abstractly talk about the differences between *containers* and *hypervisors*. 
The biggest difference was already stated - **hypervisor emulation is based on emulating hardware**. 
With this kind of technology, we take a machine and it emulates virtual hardware, and then bring up another operating system on top of that hardware. 
There is a nice slide to show [hypervisor based virutualization here](https://www.slideshare.net/Docker/introduction-to-docker-2017/18).

Containers are about virtualizing the subsystems of the operating system itself. 
We take services that the operating system provides (networking, filesystem, etc.) and provide them in a way that is virtuaizable. 
This means that I can bring up different copies of an operating system on the same kernel. 
We are using features of the kernel. 
So you can think of containers as running at the level of the kernel, and this is different from hypervisors that run one level down, and try to emulate the hardware.

 - Containers: have a **single** kernels running underneath them
 - Hypervisors: have **multiple** kernels

A cool result of this, given that you have a single kernel, is that if you fix or update that kernel, all the "guests" running off it also get patched.

For memory, a hypervisor can only see pages. 
It doesn't know what each guest is doing. 
With a container, under a single kernel the single kernel can see all objects and usage inside each container to make resource decisions. 
For this reason the resource decisions are made much more efficient.

### What is a virtual machine?

Now we can tell you that a virtual machine runs on a hypervisor, and we have a hardware layer, an entire entire operating system, and then libraries and applications on top of it. A VM is a very needy fellow:

 - Each VM requires CPU, storage, memory, and an entire operating system
 - More VMs == more resources!
 - Portability is not guaranteed

The need to allocate more system resources makes them a lot fatter and less portable than containers.
For a ballpark comparison, a hypervisor image is typically gigabytes, and a container can be in the order of megabytes. 
You've probably heard people talk about containers and use terms like "lightweight" and "efficient." 
I found a nice slide to show the differences [here](https://www.slideshare.net/Docker/introduction-to-docker-2017/22).

### Linux Container API

So if containers are so great, why did they only "become a thing" around 2014? 
The short answer is that Docker came along and gave us "mere mortals" an ecosystem for building, pushing, pulling and running containers. 
This was a product that simplified the complexity of underlying linux' isolation APIs: cgroups and namespaces.

 - *cgroups*: controls resources within the kernel (io, cpu, devices, memory, network). There is something called a "freezer" that you put a bunch of processes into and put them to sleep without worrying about resources between them.
 - *namespaces*: provide a pure isolation layer inside the kernel. Most of the time, resources only belong to a single one, for example:
   - networking devices go in networking namespaces
   - ipc namespace for messages between containers 
   - mount namespace for filesystem tree
   - pid namespace - init in linux needs to be running as pid 1 it isolates the process tree between containers     
   - UTS namespace because each container needs a separate hostname, 
   - User namespace is important for "pretending to be root" without being root.)

For those interested, there is a good talk about the history of the Linux Containers API development [here](https://www.youtube.com/watch?v=YsYzMPptB-k#t=18m10s).
In early containers, you could break from a container and become root on the host. 
While running as root is a desired or necessary feature for many applications, unexpected container breakouts are a bad security risk that container runtimes have worked hard to prohibit.
These core isolation APIs are for the most part the same for all linux distros.

A fun history fact (and maybe you already figured this about because you watched the video links above!). 
These two things (cgroups and namespaces) were developed by different open source groups. 
This came from an agreement at a conference in 2011 called the [Kernel Summit](https://lwn.net/Articles/KernelSummit2011/), literally a bunch of people sitting in a room that had both developed technologies they wanted added to the linux kernel, and had to go through the feature process and argue their case independently. 
At the end we did get a single container isolation API, but it had these two different components.  
If you are interested in learning about platform specific runtime differences, see the [runtime-spec](https://github.com/opencontainers/runtime-spec/blob/master/implementations.md) repository.

## Containers

Everything that claims to be a container technology is basically orchestrating these components. 
You can draw boxes on your powerpoint, call the boxes containers "packages" or "encapsulated environments" or what not - but low level container runtimes must include system isolation.

Containers:

 - are encapsulations of an environment
 - have their own process namespace
 - the root process of the container container on the host is still associated with one parent process, and when you start the root process the set of child processes within the container might kick off, and when you kill the root process the container's child processes are also killed.

### Container Namespaces

Akin to the namespaces on your host, a container also has its own namespace, or may be associated with a namespace shared by a group of containers.
Here it is helpful to think of a container like a little packaged environment, one that you can actually shell into like you would a server. 
When I shell inside the container I find that it has its own little process namespace.

### Container Cgroups

A cgroup is a "control group" and it's exactly that - a feature of the kernel that lets you allocate permissions for resources. 
So, for example, I might allocate a particular amount of memory, or CPU time, or network bandwidth to a set of tasks (processes that are running on my computer.) 
What else can we do? 
We can monitor them, reconfigure them, and even deny them access to resources.
Containers also have their own set of cgroups.

## What about a container image?

The words "container" and "image" are sometimes used synonymously, but are subtly two different things. 
You can think of a container image as a template, and a container is one or more running instances of that template. 
In more concrete terms, the image is one or more binary blobs sitting on your filesystem, ready to instantiate to create an isolated, encapsulated environment.

## Example Interactions

Let's give a concrete example of how you might use a container. 
Let's say you are a scientist, and a life changing paper just came out that describes how to estimate an optimal cheese eating time based on measured properties of the cheese. 
You've been collecting cheeses for decades, you can easily collect the metrics needed, and you just need the software. 

### 1. You find container images in a registry
{: .no-toc }

Thankfully, the scientist created the container you need and pushed it to [Docker Hub](https://hub.docker.com/) so all you need to do is:

 1. Install a container runtime, such as Docker, to manage OCI containers
 2. Run the container with your input parameters (if the container isn't in your cache, it will be pulled)

That is it, and truly it is that easy!

### 2. You want to change the cheese algorithm
{: .no-toc }

Uhoh, the scientist calculated the relationship between the moisture content of cheese completely wrong, and you need to modify his code and then write your own paper to refute his claims. 
Dry cheese, like cheddar, deserves just as high of a rating! 
In this case, you would:

 1. Find the container recipe, which is an Docker build specification file in this case
 2. Build and run your new container
 3. Modify it as desired, and continue testing and modifying until you get the desired result

And you could equally publish your container and findings. 
This is a good example of how containers support reproducible science. 

Resources:

 - [VMWare: Ben Corrie Sr. Staff Engineer](https://www.vmware.com/solutions/cloud-native-apps.html)
 - [RedHat: Control Groups](https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/6/html/resource_management_guide/ch01)
 - [Beginners Guide to Containers Technology](https://www.youtube.com/watch?v=YsYzMPptB-k)

[1]: https://en.wikipedia.org/wiki/Container_(virtualization)
