---
layout: default
title: Container Images
nav_order: 2
parent: Introduction
---

# Introduction to Containers

A container is a portable encapsulation of an environment. It's a
way for you to package an entire operating system, libraries, and
dependencies in a package that you can move and run anywhere.
That is the quick and dirty definition, but today we are going
to delive a little more into what this actually means.

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

We have differences in environments, hardware, and even security, and this makes sharing of applications challenging, leading to the commonality of the phrase above. A *reproducible* workflow that uses containers helps us get around this problem, and (hopefully) reduce the frequency of uttering this phrase _But it ran on my computer!_

#### Portability
{: .no_toc }

The ability to easily move a container from one machine to another is easily afforded by the fact that many container formats are variations on a compressed filesystem. If you wanted to share your entire computer, right now, you would have a hard time doing that.

#### Development Environments
{: .no_toc }

It used to be the case that to develop a simple model - view - control application with some application, database, and web server, you would need to install and run the components on your host. It would be very challenging to work on multiple projects at once. Containers are essential for developers because 
they allow us to spin up an entire set of components for a specific development environment, and then bring it
down just as easily.

#### Continuous Integration
{: .no_toc }

The same is true for testing, You can easily test across operating systems without leaving a single host.

#### Flexible
{: .no_toc }

The technologies that we use must be flexible to change. The resources
that we invest in are ephemeral, and change is unavoidable. For a concrete example. let's say you are running
a complex (containerized) application on a cloud provider. The costs of the provider changes, and you need to do a quick switch! Since your application is containerized, you can easily change providers. You can
swap out a component and not run things when you don't need to. You aren't forced becoming locked into a cloud vendor. You are a free container whale!

#### Isolation
{: .no_toc }

While the level of isolation can vary based on the container technology, containers generally allow you
to isolate an application or component from your host. This is incredibly useful if you have packages
with conflicting dependencies that need to run on the same host. 

## Virtualization
{: .no_toc }

You might be familiar with the idea of a [virtual machine](https://en.wikipedia.org/wiki/Virtual_machine) (VM), which was, for some of us, our first foray into virtualization. In a bucket:

 - A hypervisor is based on emulating hardware. 
 - When we emulate hardware, this is called virtualization.

While the term "virtual machine" is used in different contexts and can spawn much disagreement about
its definition, for the time being let's abstractly talk about the differences between *containers* and
*hypervisors*. The biggest difference was already stated - **hypervisor emulation is based on emulating hardware**. With this kind of technology, we take a machine and it emulates virtual hardware, and then bring up 
another operating system on top of that hardware. There is a nice slide to show [hypervisor based virutualization here](https://www.slideshare.net/Docker/introduction-to-docker-2017/18).

Containers are about virtualizing the subsystems of the operating system itself. We take services that the operating system provides (networking, filesystem, etc.) and provide them in a way that is virtuaizable. This means that I can bring up different copies of an operating system on the same kernel. We are using features of the kernel. So you can think containers as  building on the level of the kernel, and this is different from hypervisors that build one level down, and try to emulate the hardware.

 - Containers: have a **single** kernels running underneath them
 - Hypervisors: have **multiple** kernels

A cool result of this, given that you have a single kernel, is that if you fix or update that kernel, all the "guests" running off it also get patched.

For memory, a hypervisor can only see pages. It doesn't know what each guest is doing. With a container, under a single kernel the single kernel can see all objects and usage inside each container to make resource decisions. For this reason the resource decisions are made much more efficient.

### What is a virtual machine?

Now we can tell you that a virtual machine runs on a hypervisor, and we have a hardware layer, an entire  
entire operating system, and then libraries and applications on top of it. A VM is a very needy fellow:

 - Each VM requires CPU, storage, memory, and an entire operating system
 - More VMs == more resources!
 - Portability is not guaranteed

The need to allocate more system resources makes them a lot fatter and less portable than containers.
For a ballpark comparison, a hypervisor image is typically gigabytes, and a container can be in the order of megabytes. You've probably heard people talk about containers and use terms like "lightweight" and "efficient." 
I found a nice slide to show the differences [here](https://www.slideshare.net/Docker/introduction-to-docker-2017/22).

### Linux Container API

So if containers are so great, why did they only "become a thing" around 2014? 
It's because the linux containers API is pretty compiicated. Containers in linux are controlled by
a Kernel API, and I found a good summary and diagram in the talk [here](https://www.youtube.com/watch?v=YsYzMPptB-k#t=18m10s) picture at 18 minutes, 10 seconds. There is quite some (people-based) history behind 
the underlying API. Watch the same [talk a bit later](https://www.youtube.com/watch?v=YsYzMPptB-k#t=24m45s) for another useful picture. Generally, there are two components under discussion:

 - *cgroups*: controls resources within the kernel (io, cpu, devices, memory, network). There is something called a "freezer" that you put a bunch of processes into and put them to sleep without worrying about resources between them.
 - *namespaces*: provide a pure isolation layer inside the kernel. Most of the time, resources only belong to a single one, for example:
  - networking devices go in networking namespaces
  - ipc namespace for messages between containers 
  - mount namespace for filesystem tree
  - pid namespace - init in linux needs to be running as pid 1 it isolates the process tree between containers     
  - UTS namespace because each container needs a separate hostname, 
  - User namespace is important for "pretending to be root" without being root.)

In early containers, you could break from a container and become root on the host. This is bad, very bad.
These core components are the same for all systems! They are unfortuntately very complex.

A fun history fact (and maybe you already figured this about because you watched the video links above!). These two things (cgroups and namespaces) were developed by different open source groups. This came from an agreement at a conference in 2011 called the [Kernel Summit](https://lwn.net/Articles/KernelSummit2011/), literally a bunch of people sitting in a room that had both developed technologies they wanted added to the linux kernel, and had to go through component by component and argue their case for their thing. At the end we did get a single cohesive thing, but it had these very two different cgroups and namespaces. 

For the applied amount us, the definitions of "namespaces" and "cgroups" is not satisfactory.
I don't get it, show me! For a typical Linux OS (the example shown below is Ubuntu 16.04), 
these ideas map to folders on your computer, and 
the APIs generally work to create and modify content here, and dictate rules (permissions)
for interactions.

**Where are the namespaces?**

Here are the namespaces:

```
$ ls -l /proc/self/ns/
total 0
lrwxrwxrwx 1 vanessa vanessa 0 Sep 11 12:42 cgroup -> cgroup:[4026531835]
lrwxrwxrwx 1 vanessa vanessa 0 Sep 11 12:42 ipc -> ipc:[4026531839]
lrwxrwxrwx 1 vanessa vanessa 0 Sep 11 12:42 mnt -> mnt:[4026531840]
lrwxrwxrwx 1 vanessa vanessa 0 Sep 11 12:42 net -> net:[4026532009]
lrwxrwxrwx 1 vanessa vanessa 0 Sep 11 12:42 pid -> pid:[4026531836]
lrwxrwxrwx 1 vanessa vanessa 0 Sep 11 12:42 pid_for_children -> pid:[4026531836]
lrwxrwxrwx 1 vanessa vanessa 0 Sep 11 12:42 user -> user:[4026531837]
lrwxrwxrwx 1 vanessa vanessa 0 Sep 11 12:42 uts -> uts:[4026531838]
```

**Where are the cgroups?**

Here! Each cgroup is separately mountable. 

```bash
ls -l /sys/fs/cgroup
total 0
dr-xr-xr-x 6 root root  0 Aug 29 15:00 blkio
lrwxrwxrwx 1 root root 11 Aug 29 15:00 cpu -> cpu,cpuacct
lrwxrwxrwx 1 root root 11 Aug 29 15:00 cpuacct -> cpu,cpuacct
dr-xr-xr-x 6 root root  0 Aug 29 15:00 cpu,cpuacct
dr-xr-xr-x 3 root root  0 Aug 29 15:00 cpuset
dr-xr-xr-x 6 root root  0 Aug 29 15:00 devices
dr-xr-xr-x 3 root root  0 Aug 29 15:00 freezer
dr-xr-xr-x 3 root root  0 Aug 29 15:00 hugetlb
dr-xr-xr-x 6 root root  0 Aug 29 15:00 memory
lrwxrwxrwx 1 root root 16 Aug 29 15:00 net_cls -> net_cls,net_prio
dr-xr-xr-x 3 root root  0 Aug 29 15:00 net_cls,net_prio
lrwxrwxrwx 1 root root 16 Aug 29 15:00 net_prio -> net_cls,net_prio
dr-xr-xr-x 3 root root  0 Aug 29 15:00 perf_event
dr-xr-xr-x 6 root root  0 Aug 29 15:00 pids
dr-xr-xr-x 2 root root  0 Aug 29 15:00 rdma
dr-xr-xr-x 6 root root  0 Aug 29 15:00 systemd
```

Each of these is a folder, and the simplest one is "freezer." The way we control cgroups is via file system calls.
So, to make a cgroup called "test" I create a directory called test.
To move a process as a task into a cgroup, I can echo it there.

## Containers

Everything that claims to be a container technology is basically orchestrating 
this cgroup and namespace system. You can draw boxes on your powerpoint, call containers
"packages" or "encapsulated environments" or what not - a container technology is just
some software to stick it's boogery fingers into these system APIs. Containers: 

 - are encapsulations of an environment
 - have their own process namespace
 - the main container on the host is still associated with one process, and when you start that process the set within the container might kick off, and when you kill it the container's processes are also killed.


### Container Namespaces

Akin to the namespaces on your host, a container also has its own namespace? 
Here it is helpful to think of a container like a little packaged
environment, one that you can actually shell into like you would a server. When I shell
inside the container I find that it has its own little process namespace.

### Container Cgroups

A cgroup is a "control group" and it's exactly that - a feature of the kernel
that lets you allocate permissions for resources. So, for example, I might allocate
a particular amount of memory, or CPU time, or network bandwidth to a set of tasks,
these processes (point to processes) that are running on my computer. What else can we
do? We can monitor them, reconfigure them, and even deny them access to resources.
So these containers also have their own set of cgroups.

## What about a container image?

The words "container" and "image" are sometimes used synonymously, but are subtly two
different things. The image is a binary sitting on your filesystem of actual stuff in
some frozen state. In docker you start from a bunch of compressed archives put together,
and some other container formats have specialized compressed filesystems as images.
A really good metaphor I like to use is that the image is the filesystem / binary that
you might have sitting somewhere, and the container is the instance of that binary. Just
like a class has instances of it, an image has instances, and we call them containers.


## Example Interactions

Let's give a concrete example of how you might use a container. Let's say you are a
scientist, and a life changing paper just came out that describes how to estimate
an optimal cheese eating time based on measured properties of the cheese. You've been
collecting cheeses for decades, you can easily collect the metrics needed, and you just
need the software. 

### 1. You find container images in a registry
{: .no-toc }

Thankfully, the publishes also released a container in a registry (such as [Docker Hub](https://hub.docker.com/))
and you can:

 1. Install the Docker daemon to interact with Docker containers
 2. Pull the container to your local machine
 3. Run the container with your input parameters

That would it, and truly that easy!

### 2. You want to change the cheese algorithm
{: .no-toc }

Uhoh, the scientist calculated the relationship between the moisture content of cheese
completely wrong, and you need to modify his code and then write your own paper to refute his
claims. Dry cheese like cheddar deserves just as high of a rating! In this case, you would:

 1. Install the Docker daemon to interact with Docker containers
 2. Find the container recipe (build specification), a Dockerfile, and modify his code
 3. Build and run your new container

And you could equally publish your container and findings. This is a good example
of how containers support reproducible science. 

Resources:

 - [VMWare: Ben Corrie Sr. Staff Engineer](https://www.vmware.com/solutions/cloud-native-apps.html)
 - [RedHat: Control Groups](https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/6/html/resource_management_guide/ch01)
 - [Beginners Guide to Containers Technology](https://www.youtube.com/watch?v=YsYzMPptB-k)
