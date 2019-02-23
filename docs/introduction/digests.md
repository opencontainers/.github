---
layout: default
title: Content Addressability
nav_order: 4
parent: Introduction
---

# Content Addressability

Content addressability is important so that you can ask for what you want. When you
are asking for (pulling) a container from a registry, the registry (if it's not
a crappy one) should provide [content addressable storage](https://en.wikipedia.org/wiki/Content-addressable_storage) to ensure that you get *exactly* what you are requesting. 

## Unique Resource Identifiers

How do we ask for containers? We ask for a unique resource identifier (uri) which
broadly comes in this form:

```
<registry>/<project>/<container>:<tag>@<digest>
```

The example above is given in a familiar format for many users - one where we have a server
(the registry) with some higher level project or organization (project), and under this
project some set of container names that have different versions (tags and digets). Some
might clump the entire first address into a general tag, the "namespace":

```
<namespace>:<tag>@<digest>
```

For our purposes, let's use language to describe a concrete example of a repository on Docker Hub (the registry):

```
<registry>/<organization>/<repository>:<tag>@<digest>
```

 - *registry*: is usually a server running software with an API to interact with to pull images. Docker Hub is our registry in this example.
 - *organization*: is part of the namespace, and is the (more humanly interpretable) portion of the address.
 - *repository* is the specific container. On Docker Hub this might come from a user pushing containers directly, or an automated build from a connected webhook.

Let's make this example more specific. Here [is the busybox](https://hub.docker.com/_/busybox)
container on Docker Hub. I want to pull it!  I might be tempted to do this:

```bash
$ Using default tag: latest
latest: Pulling from library/busybox
697743189b6d: Pull complete 
Digest: sha256:061ca9704a714ee3e8b80523ec720c64f6209ad3f97c0ff7cb9ec7d19f15149f
Status: Downloaded newer image for busybox:latest
```

That's great, and I ultimately get a specific tag (the default is "latest" and the
digest of my container is shown) but if I wanted to pull the container again, and I did
it in the same fashion? Well, take a look at the changes to "latest" (it was updated
recently) and [you'll see](https://hub.docker.com/_/busybox?tab=tags) that I'd likely get a different container.

A (slightly) better interaction might have been asking for a particular tag:

```bash
$ docker pull busybox:1.30.1
1.30.1: Pulling from library/busybox
Digest: sha256:061ca9704a714ee3e8b80523ec720c64f6209ad3f97c0ff7cb9ec7d19f15149f
Status: Downloaded newer image for busybox:1.30.1
```

But really, the best idea is to pull based on the exact address, or digest.

```bash
$ docker pull busybox@sha256:061ca9704a714ee3e8b80523ec720c64f6209ad3f97c0ff7cb9ec7d19f15149f
```
