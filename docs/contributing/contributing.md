---
layout: default
title: Contributing
nav_order: 4
has_children: true
permalink: /contributing
---

# Contributing
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

# Open Containers Initiative Contributions

Before you are ready to contribute, make sure that you understand:

 1. What are the different OCI specifications, on an abstract level?
 2. What are applied usage examples of the specifications?
 3. How do I ask for help or clarification? 

You can have a gentle introduction to containers [here]({{ site.baseurl }}introduction/container-images/), and 
read about the OCI types [here]({{ site.baseurl }}introduction/oci-types/). 

## Kinds of contribution?

When you understand what a container is, and what the goals are behind each of the specifications 
provided by OCI, you are then in the right mindset to contribute. Generally, you might fit into one of the following scenarios:

 1. **Definition** You have a goal or need that is not addressed by a specification.
 2. **Documentation** An idea or concept is not explained enough for you to use it.
 3. **Feature Request** You have a new idea for an extension to a specification.

To serve these various contribution use cases, we have an [issue tracker](https://www.github.com/vsoch/oci-contribution/issues) with templates to guide you through the contribution process.
Each contribution request, whether it be asking a question or a feature, will happen via
discussion on the issue board. The final decision for a request might result in the opening of new
issues on other [opencontainers](https://www.github.com/opencontainers) boards, per the
collaborative discussion and decision of those involved. 

We have provided several templates to help guide you in your question, issue, or feature request. [Open an issue](https://www.github.com/vsoch/oci-contribution/issues) to get started with the process.
Now let's walk through what interactions and discussions on the issue tracker might look like.

## How do I Contribute?

### 1. Develop an Idea

You are on this page in first place, and reading about how to contribute, because you found a hole that isn't addressed by the specification, or have an idea for an extension to make it better. The first thing you should do is grab your computer, go to a comfortable working spot, and write. What is your use case or need? How did you try to use current software that implements OCI (and how did it fail?) Tell your problem like a story. It will be easier for experts and non-experts alike to follow your train of thought, and understand the issue you are trying to address. If you fail to capture their understanding off the bat you will have a very hard time getting support for change.

### 2. Discussion

Once you've written up your idea, post it to the [issue tracker](https://www.github.com/vsoch/oci-contribution/issues). You might also [post to the development list](https://groups.google.com/a/opencontainers.org/forum/#!forum/dev) to capture people's attention, and point them to your issue.  Why would you want to use the issue tracker in combination with the list? The issue tracker will allow you to keep a clean record of progress. You can easily link to code you are working on, and the discussion. It's a central place for *all the things*.
The mailing list is important for reach and perspective. You can challenge others
that have different use cases for interaction with containers to give feedback on your idea.

### 3. Support and Action

Once discussion starts to die down, it's important to try and synthesize the content discussed into a concrete action. The maintainers will likely be doing this without thinking about it. For example: 

 - *Documentation Action* if there is functionality you thought was missing and it actually existed? This calls for an improvement to the documentation. The maintainer can assign issues to developers to address your concern, and ask for your feedback.
 - *Show Me Action*: The most likely result of you wanting a new thing will be a request for a dummy implementation. It doesn't need to be perfect, but you must *show* that your idea has feet, and solves the problem that you stated. 
 - *Feature Request Action* It could be that your idea was succinct and strong, and a new feature is called for development. This likely will result in one or more developers (including you!) coming up with a plan of action. This is less likely an option, because changes to the specifications tend to be more conservative.

Generally, you will want to find support for your action, whether it be advice or actual help from others in the list. We do this step before detailed feedback in the case that your idea doesn't need furter investigation (already solved or being worked on, for example). What should never happen is anything that goes against the [code of conduct](https://github.com/opencontainers/org/blob/master/code-of-conduct.md). You should not be put down, ridiculed for your ideas, or otherwise have someone treat you poorly.

### 4. Detailed Feedback

After you've posted your idea to the list, I can almost guarantee you someone else will be interested or
excited to give you feedback. The list (or a Github issue) itself isn't really the place to hash out the details.
Your final post on the discussion might be to share a link to a more formal write up of your idea. You
probably already have it written into a document, and it makes sense
to share this writeup with others for feedback (Google Docs, GitHub markdown, etc.). How long should you 
get feedback? This is up to you. Make sure to give others credit and thanks for their contribution. If it's
on GitHub, use an AUTHORS.md file. If it's a Google Doc, allow collaborators to write their name in a section,
if desired. It's important to stress that the idea is a group effort. At this point, since you have others'
attention, you might want to consider creating a working group to continue progress on your idea.
What is a working group? It can be a small email list, a group of contributors subscribed to a common
repository, or a slack channel. It's basically a way to communicate, and that way should be your preferred method(s).

### 5. Implementation

Great! You now have created the idea, posted to the list, and you are tracking progress on the GitHub issue tracker. Here is the fun (and challenging) part. You need to *show* that your idea has feet. This comes
down to a dummy implementation that, paired with your writeup, can tag team to convince others of your idea.
This step will likely require several iterations. When you present your work to the OCI maintainers again, you need to stress the following points:

 1. Restate the problem, and what you couldn't previously do to lead to your idea
 2. Show them what is now improved, and possible, with your approach.
 3. Be transparent about limitations. Ask again for feedback and help to address them.

### 6. Contribution to OCI

Given a strong idea, a proof of concept, and support, the discussion might next move to
how the idea can be integrated with OCI, or it could serve as a tool to supplement it.
This final stage is the least established, and will vary depending on the proposal.
