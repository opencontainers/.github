---
layout: default
title: OCI Types
nav_order: 3
parent: Introduction
---

# Specification Types
{:.no_toc}

1. TOC
{:toc}

---

## Understanding How Specifications Meet Goals

The core of OCI are the specifications for container images, registries (called "distributions") 
and runtime. Let's step back and talk about what this actually means. If you are a developer, as 
we discuss these specifications, think about them in the context of answering these questions:

 - How would I want to use this to solve a particular problem?
 - Where might I have seen this in the wild, and not realized it's a part of OCI?

Specific examples will be given to help guide your thinking.

### The Image Specification

The [image specification](https://github.com/opencontainers/image-spec/blob/master/spec.md) generally is a grouping of things to describe a container image. While there is a definition for a [filesystem](https://github.com/opencontainers/image-spec/blob/master/layer.md) and [configuration](https://github.com/opencontainers/image-spec/blob/master/config.md), the most general entity to describe is the image manifest:

#### Manifest

The [manifest](https://github.com/opencontainers/image-spec/blob/master/manifest.md) comes down to a json blob of properties for the container such as contents (in Docker, we refer to image layers since the image is a bunch of .tar.gz assembled at runtime), annotations, and a unique identifier for a configuration object. For example, here is a json dump that describes a Docker container:

```
{
  "schemaVersion": 2,
  "config": {
    "mediaType": "application/vnd.oci.image.config.v1+json",
    "size": 7023,
    "digest": "sha256:b5b2b2c507a0944348e0303114d8d93aaaa081732b86451d9bce1f432a537bc7"
  },
  "layers": [
    {
      "mediaType": "application/vnd.oci.image.layer.v1.tar+gzip",
      "size": 32654,
      "digest": "sha256:9834876dcfb05cb167a5c24953eba58c4ac89b1adf57f28f2f9d09af107ee8f0"
    },
    {
      "mediaType": "application/vnd.oci.image.layer.v1.tar+gzip",
      "size": 16724,
      "digest": "sha256:3c3a4604a545cdc127456d94e421cd355bca5b528f4a9c1905b15da2eb4a4c6b"
    },
    {
      "mediaType": "application/vnd.oci.image.layer.v1.tar+gzip",
      "size": 73109,
      "digest": "sha256:ec4b8955958665577945c89419d1af06b5f7636b4ac3da7f12184802ad867736"
    }
  ],
  "annotations": {
    "com.example.key1": "value1",
    "com.example.key2": "value2"
  }
}
```

**Where would I find an image manifest?**

An image manifest would be served by a registry, and would help the user to obtain the content (in the example above, the .tar.gz layers assembled at runtime to create the image). 

**What would I do with the image manifest?**

The manifest helps you to download image layers. I might query the registry API to find the image manifest for an image I'm interested in, get back this json blob, and then use the client to pull the image layers (the digests). Depending on the design of the registry, there would be another endpoint that I know to query with the blob digests to actually download them.

**What are the annotations for?**

Annotations are key value pairs of metadata to describe the image of interest. They are fairly flexible to allow for the registry and user to use as they see fit.

**How would I want to use this to solve a particular problem?**

The image manifest definition should be able to describe some kind of content blobs for an
application like a registry.

**Where might I have seen this in the wild?**

An image manifest is what you see delivered by the [Docker registry]() to get metadata
for a particular [container tag](https://docs.docker.com/engine/reference/commandline/manifest/).


### The Distribution Specification

The [distribution specification](https://github.com/opencontainers/distribution-spec/blob/master/spec.md)
describes the API that might be used by a registry to distribute images. This means actions like pull, push, along with how images are named, and errors are presented. You can think of the distribution specification
as a collection of endpoints served by a registry to communicate with. Do you want a manifest? Use
the manifest endpoint:

```
GET /v2/<name>/manifests/<reference>
```

Do you want to upload a blob? There is an endpoint to POST to for that:

```
POST /v2/<name>/blobs/uploads/
```

**Where would I find a distribution specification?**

An implementation of this specification would be found with a container registry that
implements the OCI standard. For example, Docker Hub implements the specification. A
developer could also roll their own registry (such as [this one](https://github.com/atlaskerr/stori))
that implements it.

**What would I do with the distribution specification?**

The specification outlines a method of interaction. If you are writing a client, for example, these
are the endpoints that the client would use. If you are creating a new registry that you wanted
to conform to OCI, these are the API endpoints you would implement.

**How might I contribute to the distribution specification?**

Generally, since the goals are to move (push and pull) images, and provide endpoints for a client,
if you are designing a registry or a client and find that you are missing some key function of an
endpoint, or information provided by an endpoint, you might want to suggest a change to the specification.

### The Runtime Specification

The [runtime specification](https://github.com/opencontainers/runtime-spec/blob/master/spec.md) is another
description of an interaction, but this time it's with a container binary.  Specifically, this means
the execution environment, configuration, and lifecycle of a container.

**What do you mean by execution environment?**

What is the host operating system of your computer, Windows? Linux? These are different execution environments that come with different rules and standards for generating (what feels like) the same running container. If you look at the [runtime specification](https://github.com/opencontainers/runtime-spec/blob/master/spec.md) entry page, you'll actually find that there is a different specification file for each base operating system.

**Why do we need runtime specifications?**

As a user, you expect a container run on a Windows machine to generally feel like and act the same
as a container run on a Linux host. The runtime specifications are catered toward this goal, with different
configuration files (called config.json) to drive the creation, execution enviroinment, and actions 
for the container.

**How might I contribute?**

You might have an entirely different operating system or technology that you want to explore running containers on, in which case you would want to contribute a new specification. You might find that there is an ambiguity or bug for one runtime, and ask a question about how to work on it.

What are you waiting for? We want to hear from you!

[Contribute]({{ site.baseurl }}docs/contribute/){: .btn .btn-primary .fs-5 .mb-4 .mb-md-0 .mr-2 }
