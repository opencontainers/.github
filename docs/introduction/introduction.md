---
layout: default
title: Introduction
nav_order: 3
has_children: true
permalink: /introduction
---

# Introduction
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

If you are looking for a gentle introduction to containers and the Open Containers
Initiative, you've come to the right place!

## Containers

A container is generally an encapsulated environment that is created from one or more binaries (images) to provide some form of isolation. Read more about [containers here]({{ site.baseurl }}docs/introduction/container-images/)

## What is OCI?

OCI stands for the "Open Containers Initiative" and encompasses a group of people and a set of 
specifications for describing container formats and interactions. For more information about
OCI, see [About Open Containers]({{ site.baseurl }}about/).

## OCI Specification Types

What is a runtime? A container image? A distribution? These are different *types* that each
come with specifications for how a container is built, or interacted with. To give you a
good understanding of OCI Types, let's talk about the goals of [OCI types]({{ site.baseurl }}docs/introduction/oci-types/). When you understand
the goals of each one, this puts you in a position to understand how they are used, why they are used,
and how you can contribute.

## Content Addressability

How does somebody find your house to mail a letter? They have an address, or a unique
identifier for the location of your house. Containers are no different - we can calculate
hashes of their content called _digests_ and then use these addresses as unique identifiers 
to reference the containers. Read more about [Content Addressability]({{ site.baseurl }}docs/introduction/digests/) here.

## Distributing Container Images

Let's say I have a container on my host. How do I get it to you? How can you be sure
that your containers are safe if your laptop crashes? The task of distributing containers
offers an entire new space of challenges. Read about 
[distributing container images here]({{ site.baseurl }}docs/introduction/distribution/)


You made it to the bottom! Now that have an understanding of containers and the specifications, you should
next read about how to contribute.

[Contributing]({{ site.baseurl }}contributing){: .btn .btn-primary .fs-5 .mb-4 .mb-md-0 .mr-2 }
