# OCI Weekly Dev Meeting Notes Archive - 2020

## December 9, 2020
**Recording:** https://www.youtube.com/watch?v=lgOpG0Cd9o4

### Attendees:
- Steve Lasker (Microsoft)
- Josh Dolitsky
- Nisha Kumar (VMware)
- Jimmy Zelinskie (petricorp)
- Bo Liu (Alibaba cloud)
- Tianon
- ASP
- Justin Cormack
- Brian Goff
- Derek McGowan
- Jon Johnson
- Peter Engelbert
- Tycho
- Tianon
- Ram Chinchani
- Mike Brown (IBM)
- Peng Tao (Ant Group)
- Serge Hallyn
- Samuel Karp
- Mark Peek
- _add yourself_

### Agenda Items:
- Distribution spec v1.0.0-rc2 (Josh)
    - Milestone: https://github.com/opencontainers/distribution-spec/milestone/5
- Distribution spec: use "main" as default branch? (Josh)
- Pushing a conformance image to GitHub registry? Access token to use? (Josh)
    - https://github.com/opencontainers/distribution-spec/pull/217
- Unusability of zstd (Justin Cormack) https://github.com/opencontainers/image-spec/issues/803
- Content negotiation (Jon, carried from last week)
    - https://github.com/opencontainers/distribution-spec/issues/212
    - https://github.com/docker/roadmap/issues/173
- Nydus container image service intro. Peng Tao and Liu Bo
    - https://github.com/dragonflyoss/image-service
    - https://github.com/dragonflyoss/image-service/blob/master/docs/nydus-design.md

For next meeting:
- Artifact Manifest - a 3rd manifest type for registries to support reference and collection types (Steve)

### Notes:
- Josh: Just opened #218 to try to solve the accept header content negotiation (Sebastian or Jon can take a pass at). Maybe have a session to resolve open items to move forward with rc2.
- Josh: Changing the name of the branch from master to main.
    - Steve: Maybe wait for Github to publish a seamless way to do this. Will reach out to find more.
- Josh: When creating an html report for a registry, it says "unknown" in the Github action. You cannot build a dockerfile with build args. Questions about how to use Github registry with a user token.
    - Brian: You need a personal token.
- Justin: Docker is donating docker distribution to CNCF (in January). In sandbox and incubation.
- Justin: Old clients cannot use an image using zstd. This is problematic with backwards compatibility with old containers and registries. If a client ignores a layer this would be an implementation problem. It would be better for the blob format to be part of a manifest list.
    - Steve: As long as it doesn't interfere with client operation, it should be fine.
    - Justin: The manifest list design is not very extensible, but it logically makes sense to include this information here.
    - Brian: The issue with that it will not make use of dedupe.
    - Justin: bandwidth is more important than the storage cost.
    - Steve: customers usually complain about resolving the exact artifact before download rather than storage costs.
    - Tycho: You can put whatever keys you want in the manifest.
    - Derek: The issue is that the client needs to understand the key.
    - Jimmy: A workaround is to translate the formats on the fly. That way you can serve legacy images in this way.
    - Steve: Maybe use versioning so clients can check for a version?
    - Brian: Maybe support different image formats in the manifest list.
    - Probably need a versioning schema
    - Tycho: Someday the image formats will not be interchangable, then what will the clients do.
    - Justin: Change to spec to say that images should have manifest lists in order to be backwards compatible (probably fix it before a release)
- Nydus:
    - Bo: The manifest for the nydus images have annotations that determine what kind of blobs the client should be looking for. 

## December 2, 2020
**Recording:** https://www.youtube.com/watch?v=Qzwa6R0uZXQ

### Attendees: 
- Tianon
- Mark Peek
- Phil Estes
- Justin Cormack
- Samuel Karp
- Tycho Andersen
- Jon Johnson
- Vincent Batts
- Steve Lasker
- Mauricio Vásquez
- Bo Liu
- ASP 
- Adam Wolfe Gordon
- Peng Tao
- Josh Dolitsky
- Peter Engelbert
- Cody Roseborough
- _add yourself_

### Agenda Items: 
- Registry APIs for untagged content, API standardization. Justin Cormack.
    - [Slides](https://docs.google.com/presentation/d/1ZfTfveXEqF0GtY3GDRDDGpEz-JmSw8B8uPP6HBQvqf0/edit#slide=id.ga34b7e2c3a_0_0)
    - Somewhat related: [distribution-spec#22](https://github.com/opencontainers/distribution-spec/issues/22#issuecomment-417143466)
- Proposed spec/conformance updates. Mark Peek and Peter Engelbert.
    - [PR#204](https://github.com/opencontainers/distribution-spec/pull/204)
    - [PR#208](https://github.com/opencontainers/distribution-spec/pull/208)
- Updates on Seccomp Notify in OCI runtime-spec and runc. Mauricio Vásquez Bernal. Alban Crequy.
  - [PR#1074](https://github.com/opencontainers/runtime-spec/pull/1074) (spec)
  - [runc PR#2682](https://github.com/opencontainers/runc/pull/2682) (implementation in runc)
- Nydus container image service intro. Peng Tao and Liu Bo
  - https://github.com/dragonflyoss/image-service
  - https://github.com/liubogithub/image-service/blob/doc/docs/nydus-design.md

### Notes

- Nisha plugged [tern lock](https://github.com/tern-tools/tern/commit/6de1f351b7cfe6ca5a25453f97fa6d9c0e481229)
- Jon's opinions on Justin's preso:
    - Listing untagged images is super important, let's try to standardize something ASAP. Tried to start something with [distribution-spec#22](https://github.com/opencontainers/distribution-spec/issues/22#issuecomment-417143466); we can continue discussion there?
    - Would love some standardization around deletion semantics, maybe we can add headers to indicate desired behavior for tag deletion etc.?
    - Tag history sounds awesome, would love that.
- Steve - Would like to get a working group together to see if we can agree on a common listing and deleting apis as each cloud/registry has implemented slightly different semantics with unique APIs, which is confuing to users, and limits generic tooling. 
- Group feedback on [PR#208](https://github.com/opencontainers/distribution-spec/pull/208)
  - GET and HEAD requests MUST return a Docker-Content-Digest header.
  - The inclusion of OCI-Content-Digest is not needed and should be removed from the PR.

## November 11, 2020

Cancelled due to US and EU Holidays
Week of 11/18 is KubeCon
Week of 11/25 is US Thanksgiving
Next meeting will be 12/2/2021

### Notes

- Docker-Content-Digest header
    - Its a MUST for OCI-, with exception that Docker- will be accepted
    - Backwards-compantibility
        - Clients should check for the header
        - Registries should supply the header
    - Let's just not change it? Is there actually any reason to change this?

- Remaining issues: https://github.com/opencontainers/distribution-spec/issues/211

## November 4, 2020 
Cancelled

## October 28, 2020
**Recording:** https://www.youtube.com/watch?v=Q2DYxlF6trM

### Attendees:
- Steve Lasker (Microsoft)
- Josh Dolitsky (The Hotdog)
- Phil Estes
- Omar Paul (AWS)
- Amye SP
- Brian Goff
- Peter Englebert
- Mark Peek
- Tianon
- Mike Brown
- Toddy M.
- _add yourself_

### Agenda Items:
- Distribution-spec v1.0.0-rc2 updates (Josh)
    - "Note regarding process section that is being removed from the specification text"
        - Link: https://github.com/opencontainers/distribution-spec/issues/191
    - "dist-spec 1.0.0-rc OPTIONAL marked items"
        - Link: https://github.com/opencontainers/distribution-spec/issues/194
    - "Friendly README"
        - Link: https://github.com/opencontainers/distribution-spec/issues/200
    - "fixed to use "bytes" unit for Content-Range to spec/test"
        - Link: https://github.com/opencontainers/distribution-spec/pull/203
    - "Add cross-repository mounting section to spec/test"
        - Link: https://github.com/opencontainers/distribution-spec/pull/204
    - "Resolve several open issues"
        - Link: https://github.com/opencontainers/distribution-spec/pull/206

### Notes:

## October 21, 2020

### Agenda Items:
- no meeting this week

## October 14, 2020
**Recording:** https://www.youtube.com/watch?v=i6HRPtrV5pA

### Attendees:
- Phil Estes
- Steve Lasker
- Derek McGowan
- Brian Goff
- Amye
- Jon Johnson
- Justin Cormack
- Josh Dolitsky
- yosifkit
- Mike Brown
- Michael Winser (Google)
- Kevin Parsons
- Andrew Sharon
- Juan Sebastian Oviedo
- Nisha Kumar
- Omar (AWS)
- Peter Engelbert
- Samuel Karp
- Toddy Mladenov
- Scott Zawalski
- Ram Chinchani
- Chad Metcalf
- Nick Yesin
- Chris A
- Bryan Clark
- Mark Peek
- 
- Adam Wolfe Gordon

### Agenda Items:
- Consuming Content From Public Registries: Steve with representatives from each cloud provider  
  Discussion for how OCI can help the community reliably depend on public content, utilizing public sources, with the benefits of local registries.
- Dist spec 1.0 brief update (Josh)
    - 1.0.0-vc2 github milestone https://github.com/opencontainers/distribution-spec/issues?q=is%3Aopen+is%3Aissue+milestone%3Av1.0.0-rc2

### Notes:

## October 7, 2020

### Attendees:
- Nisha Kumar
- Josh Dolitsky
- Tianon
- Amye SP
- Phil Estes
- Derek McGowan
- Peter Engelbert
- Samuel Karp
- Mark Peek
- Adam Wolfe Gordon
- Mike Brown

### Agenda Items:
- Brief discussion on dist-spec v1.0.0-rc1 and road to final (Josh)

### Notes:
Josh: Distribution spec v1.0.0-rc1 is out. rc1 has a ton of changes since the last year and half.
- Needs 3 RCs before v1.0.0 release, so expect rc-2 (v1.0.0-rc2 milestone created (left the projected date off for now))
- Look at the spec on the master branch (not the rc-1 branch)
- Links:
  - How to self-certify: https://github.com/opencontainers/oci-conformance/blob/master/instructions.md
  - Running conformance tests: https://github.com/opencontainers/distribution-spec/tree/master/conformance

## September 30, 2020
**Recording:** https://www.youtube.com/watch?v=PfhzClv0sgI

### Attendees:

- Tianon
- Phil Estes
- Brian Goff
- Steve Lasker
- Shubhra Deshpande
- Jimmy Zelinskie
- Adam Wolfe Gordon
- Samuel Karp
- Mike Brown
- Tycho Andersen
- Mark Peek
- Amye SP
- Derek McGowan
- Nisha Kumar
- Peter Engelbert
- Ram Chinchani
- Toddy Mladenov
- Josh Dolitsky
- Chris A
- (add yourself here)

### Agenda Items:

- Distribution spec 1.0.0-rc1 release (Josh)
    - https://github.com/opencontainers/distribution-spec/pull/190
- OCI Artifacts, supporting artifacts that reference other artifacts, like Notary v2 signatures - (Steve)
- Add other platform fields to image config spec https://github.com/opencontainers/image-spec/pull/777 https://github.com/opencontainers/image-spec/pull/809 (Brian)

### Notes:

- PR for dist-spec rc1: https://github.com/opencontainers/distribution-spec/pull/190
- OCI Artifacts, supporting artifacts that reference other artifacts, like Notary v2 signatures
  - [Artifact Collections Slides](https://github.com/SteveLasker/drafts/blob/main/media/oci-artifact-collections.pptx)
  - [Artifact metadata services initial thoughts](https://github.com/SteveLasker/drafts/blob/main/meta-data-services.md)

## September 23, 2020

Cancelled

### Agenda Items:
- ~~OCI Artifacts, supporting artifacts that reference other artifacts, like Notary v2 signatures~~ - Steve double booked, will cover next week
- _add your items_

## September 16, 2020
**Recording:** https://www.youtube.com/watch?v=t-lj9PoXE0Q

### Attendees:
- Nisha Kumar (VMware)
- Steve Lasker (Microsoft)
- Alban Crequy (Kinvolk)
- Amye SP
- Vincent Batts (Kinvolk)
- Mike Brown (IBM)
- Phil Estes (IBM)
- Samuel Karp (AWS)
- Sargun Dhillon
- Peter Engelbert
- Idit Levine
- Yuval Kohavi
- Tycho
- Serge Hallyn
- Erick Carty
- Derek McGowan
- Josh Dolitsky
- Kyle Anderson (Netflix)
- Sargun Dhillon (Netflix)
- Toddy Mladenov
- Sourabh Shirhatti
- Giuseppe Scrivano
- Ram Chinchani

### Agenda Items:
- [Seccomp Notify Proposal](https://docs.google.com/document/d/1xHw5GQjMj6ZKR-40aKmTWZRkvlPuzMGQRu-YpOFQc30/edit#heading=h.q8r2454bwe1t): support in OCI Runtime Spec and runc  - Alban Crequy
- [WASM & OCI](https://www.solo.io/blog/announcing-the-webassembly-wasm-oci-image-spec/?utm_campaign=Product%3A%20Web%20Assembly%20Hub&utm_content=139595890&utm_medium=social&utm_source=twitter&hss_channel=tw-846446677460504576) Idit
- _add your items_

### Notes:
#### Seccomp Notify Proposal
Touch on what was discussed last week.
- Alban: containers cannot invoke syscalls like mount() and/or bpf().
- Let the seccomp agent notify the container runtime instead.
- Use OCI hooks to declare the seccomp file descriptors.
- There is an existing PR that uses a "ListenerPath".
- Serge: who makes the decision on what syscalls are OK?
- Sargun: We use OPA to evaluate the syscalls.
- Vbatts: There may be a host policy vs container policy.
- Similar to the OCIv2 conversation about binding host with container.
- Next steps:
    - Address the existing PR #1038
    - Address the case where there is no seccomp notify declarations
    - Create a PR to the runtime spec
- Alban: general use case is to do syscall filtering via OPA. Kernel policy is slow moving, so rather than make changes in the kernel, we manage seccomp policy.
#### WASM and OCI
- Solo.io is using wasm to extend services at the control/data plane.
- The general idea is to add filters along the data path. Using wasm means one can write their own custom filters and compile it into wasm.
- There is an interface spec called WASI that extensions can use: webassemblyhub.io
- _meeting minutes_

## September 9, 2020
**Recording:** https://www.youtube.com/watch?v=4ILZVWTKZjs

### Attendees:
- Alban Crequy (Kinvolk)
- Adrian Mouat (Container Solutions)
- Steve Lasker (Microsoft)
- Vincent Batts
- Tianon
- Samuel Karp
- Andrew Sharon (AWS)
- Josh Dolitsy
- Amye SP
- Tycho Andersen (Cisco)

### Agenda Items:
- [Registry tooling for Multi-Arch Images (OCI Indexes) proposal](https://docs.google.com/document/d/1Dfwd6tUvRTTQKItD_AG-qmfJUbZQFk8_sut8P5RaOvY) - Adrian Mouat
- [Seccomp Notify](https://brauner.github.io/2020/07/23/seccomp-notify.html) support in OCI Runtime Spec and runc - Alban
  - [Proposal](https://docs.google.com/document/d/1xHw5GQjMj6ZKR-40aKmTWZRkvlPuzMGQRu-YpOFQc30/edit#heading=h.q8r2454bwe1t)
  - [Slide](https://docs.google.com/presentation/d/1n7fZSsWDNbLNuYbTGEJbxDi-s9hUttR3Fs0VtHj94l4/edit#slide=id.g2bea054e49_0_325)

### Notes:
- https://github.com/containerd/nri
 
## September 2, 2020

### Agenda Items:
- no topics this week

## August 26, 2020

**Recording:** https://www.youtube.com/watch?v=_v5-zKtvjz4

### Attendees:
- Tianon
- Steve Lasker (Microsoft)
- Samuel Karp
- Craig Peters
- Josh Dolitsky
- Mike Brown (IBM)
- _add yourself_

### Agenda Items:
- [Proposal for OCI Index to support config, enabling new artifact types](https://github.com/SteveLasker/drafts/blob/master/oci-index-add-config.md) - Steve
- Distribution spec updates - Josh
- [bundle.bar](https://bundle.bar) intro - Josh

### Notes:
- Agreement to add `index.config`
    - need to validate the various clients to assure they don't choke on the behavior
    - Felt adding a version `v3` was important to avoid clients having to guess what this additional property is, or having to know to avoid the propoerty
    - Derek/Mike were suggesting we should use this as an opporutnity to pull the schemas out of the image-spec and either put them in the artifacts spec or a new repo for schemas. Working thought is add them to artifacts as image-spec is a typeOf artifact. 
    - This also helps us avoid having to "braek the glass" on the image-spec.
    - **Next Steps**: Notary v2 forks of docker/distribution and ORAS will add index.config support so we'll have some reference implementations to test with the various clients.
    - With the Notary scenario working, we'll have enough feedback to give confidence to make the PRs on the appropriate specs
- https://github.com/bloodorangeio/distribution-spec/blob/new-spec/spec.md
- https://github.com/bloodorangeio/distribution-spec/blob/new-spec/spec.md
- _meeting minutes_

## August 19, 2020

Cancelled due to KubeCon *EU* week
 
## August 12, 2020
**Recording:** https://youtu.be/jfZIk6hYvFY

### Attendees:
- Steve Lasker (Microsoft)
- Justin Cormack (Docker)
- Phil Estes
- Till Wegmüller (OpenFlowLabs)
- Jacob Blain Christen (Rancher Labs)
- Tianon
- Darren Shepherd (Rancher Labs)
- Josh Dolitsky
- Samuel Karp (AWS)
- Adam Wolfe Gordon (DigitalOcean)
- Amye SP(OCI)
- Peter Engelbert
- Richard Nguyen
- Kevin Parsons (Microsoft)
- Mike Brown (IBM)

### Agenda Items:
- Multi-architecture images (OCI index) - Darren Shepherd
- [Proposal for OCI Index to support config, enabling new artifact types](https://github.com/SteveLasker/drafts/blob/master/oci-index-add-config.md) - Steve
- Distribution spec updates - Josh
- _add your topics_

### Notes:
- Index feedback from Darren
    - Multi-arch pain points
        - One immutable artifact that points to all archs
        - docker pull, tag, push odditites
        - What digest am I looking at?
            - Is it the index, manifest or the image?
        - Not sure if it's tooling or the upload apis
    - CI learnings
        - not feasable to build all architectures at once
        - cross compiling sucks
        - Easiest when you run parallel pipelines
        - one pipeline per architecture
        - Join at the end to create the multi-arch manifest
        - amdnind the manifest is racy and dirty (don't want to pull the wrong tag or have an incomplete build)
        - many CI systems can't handle all the different architectures, or join at the end.
        - Currently use drone to provide more flexibiliyt. Would like to move off, but this one parallel build feature is too helpful
    - push/pull semantics
        - Gets very confusing and they can accidently tag the manfiest, vs. the manifest list
        - Manifest list is like a pointer, with all it's normal pointer issues
        - containerd pulling has weird side effects
        - Lots of questions with naming standards, related to a tag, or a repo. Seems many repos are following different conventions.
- Additional to the Arch the OS runs also into the same problem. For example if you have a docker image based on linux or illumos, and the OS and arch are Orthagonal to each other.
- Hoping for some next steps for an owner to run with some ideas
    - Darren and Tianon, with some assistance from Till and Jacob
- _meeting minutes_

## August 5, 2020
*meeting canceled - no topics*

## July 29, 2020
**Recording:** https://www.youtube.com/watch?v=4KEUdBKkbF0

### Attendees:
- Josh Dolitsky
- Amye SP
- Adrian Mouat
- Samuel Karp
- Steve Lasker (Microsoft)
- Phil Estes
- Derek McGowan
- Mike Brown
- Peter Engelbert
- Ram Chinchani
- Rose Judge
- Tianon
- Sajay Antony

### Agenda Items:
- _add your topics_
- Distribution spec 1.0 updates (Josh)
    - Demo: https://oci.bloodorange.io/specs/distribution-spec/
    - List of PRs still under review: https://github.com/opencontainers/distribution-spec/issues/163
- [Notary v2 update](https://github.com/notaryproject/nv2/blob/33a6150829b2b947ea340c781d173e80a223535e/README.md) (Steve)

### Notes:
- For definitions of manifest and digest, should they reference image-spec? (Josh)
    - "Yes" (Mike and others)
    - Digest def: https://github.com/opencontainers/image-spec/blob/b6e51fa50549ee0bd5188494912a7f4c382cb0d4/descriptor.md#digests
    - Manifest def: https://github.com/opencontainers/image-spec/blob/069d186692cf734b8f5119a0cfdf4ff1ad741934/manifest.md


## July 15, 2020 - 6pm Pacific
**Recording:** https://www.youtube.com/watch?v=7V5aw7y3jJk

### Attendees:
- _add yourself_
- Tycho Andersen (Cisco)
- Vincent Batts (Kinvolk)
- Wei Fu (Alibaba Cloud)
- Tao Peng (Ant Group)
- Daniel Mangum (Upbound)
- Kohei Tokunaga (NTT)
- Akihiro Suda (NTT)
- Josh Dolitsky

### Agenda Items:
- OCI v2, Part III discussion
  - For those attending, please follow along with [the brainstorm document](https://hackmd.io/@cyphar/ociv2-brainstorm) (Aleksa/Tycho).
- Distribution spec 1.0 updates (Josh)

### Notes:
- Distribution spec 1.0 updates
    - Please help review "mini update" PRs for 1.0: https://github.com/opencontainers/distribution-spec/pulls?q=is%3Apr+is%3Aopen+mini+update
    - Example of OCI website with specs menu item: https://oci.bloodorange.io/specs/distribution-spec/


## July 8, 2020 - 6pm Pacific
Note time change to APAC friendly time, one time only
**Recording**: https://www.youtube.com/watch?v=JT3DJnfmWZ8

### Attendees:
- Steve Lasker (Microsoft)
- Tycho Andersen (Cisco)
- Phil Estes (IBM)
- Kir Kolyshkin (Red Hat)
- Wei Fu (Alibaba Cloud)
- Tao Peng (Ant Group)
- Bo Liu (Alibaba Cloud)
- Amye SP (OCI)
- Derek McGowan
- Vincent Batts
- Kohei Tokunaga (NTT)
- Akihiro Suda (NTT)
- Aleksa Sarai
- Jimmy Zelinskie
- _add yourself_

### Agenda Items:
- OCI v2, Part Duex discussion
  - For those attending, please follow along with [the brainstorm document](https://hackmd.io/@cyphar/ociv2-brainstorm) (Aleksa/Tycho).
- _add your topics_

### Notes:
 _meeting minutes_

## July 1, 2020

- Cancelled - note July 8th time change ^

## June 24, 2020
**Video recording:** https://www.youtube.com/watch?v=5n-WWfEsrWg

### Attendees:
- Aleksa Sarai (SUSE)
- Nisha Kumar (VMware)
- Bo Liu (AlibabaCloud)
- Till Wegmüller (OpenFlowLabs)
- Steve Lasker (Microsoft)
- Josh Dolitsky (Blood Orange)
- Peter Engelbert (Blood Orange)
- Phil Estes (IBM)
- Tianon
- Tao Peng (Ant Group)
- Samuel Karp (AWS)
- Tycho Andersen (Cisco)
- Adam Wolfe Gordon (DigitalOcean)
- Amye SP (OCI)
- Tue Tran (AWS)
- Serge Hallyn (Cisco)
- Mike Brown (IBM)

### Agenda Items:
- OCI v2 discussion
  - For those attending, please follow along with [the brainstorm document](https://hackmd.io/@cyphar/ociv2-brainstorm) (Aleksa/Tycho).


### Notes:
OCIv2 is a marketing term for updating the OCI spec to better address these use cases. Not a brand new spec.
#### Reduce Duplication
- tar does not provide good deduplication (look at Aleksa's blog)
- Purpose is to reduce duplication during transfer
- A benefit would be faster download speeds
- Original proposal is per chunck blobs during tranfer
- Restic way: many small blobs represent the files.
- Getting rid of tar archives, which will probably involve spec changes
- Possibly roll into extensions (vbatts?)
- How will clients detect the new images? What clients are not handling specific image indexes?

#### Canonical Representation
- Two different image builders will produce two different images even though the content is the same
- tar archives do not have a canonical representation (tar on one system is implemented differently than another system)
- Reproducibility across image builders is the goal
- See Aleksa's blog to find out why tar is not a good archival format

#### Minimal File Metadata
- Eg: timestamps, xattrs, device numbers
- Standardized metadata helps with reproducibility and correctness
- Considerations: do we keep device mountpoints? How do hardlinks work? Maybe look at OSTree?

#### Mountable filesystem format
- Step 1 is to download a blob and step 2 is to extract. Extracting destroys the signature.
- If you just use squashfs which combines all the layers. A builder could reason about the most optimal way of mounting the filesystem.
- The motivating use case is to preserve the signature and save disk space.
- If the image spec was designed in such a way that signatures need not have to be a supplemental metadata to query in order to verify the artifacts.

## June 17, 2020

- Cancelled

## June 10, 2020 

- Cancelled

## June 3, 2020

### Attendees:
- Tianon
- Mike Brown (IBM)
- Nisha Kumar (VMware)
- Till Wegmüller (OpenFlowLabs)
- Josh Dolitsky
- Samuel Karp (AWS)
- Bo Liu (AlibabaCloud)
- Adam Wolfe Gordon (DigitalOcean)
- Phil Estes (IBM)
- Derek McGowan
- Ram Chinchani
- Erick Carty
- Serge Hallyn
- Bowen Song
- Tycho
- Peter Engelbert
- Jon Johnson
- Shubhra Deshpande (AWS)
- _add yourself_

### Agenda Items:
- OCI v2 discussion (Aleksa?)
    - Requirements Brainstorm online at: https://hackmd.io/@cyphar/ociv2-brainstorm the idea is to try to figure out which features and requirements people have so prototypes can be made trying to fullfill all. Aleksa leads the Process on this.
- Conformance Testing scoping manifest, index, test driven (Josh/Steve)
- _add your topics_

### Notes:
- "test driven spec writing" - https://github.com/bloodorangeio/distribution-spec/blob/test-driven-spec/conformance/01_pull_test.go#L87
- https://github.com/bloodorangeio/distribution-spec/tree/test-driven-spec/sections
- https://github.com/bloodorangeio/distribution-spec/blob/test-driven-spec/Makefile#L99mk
- https://github.com/spdx/spdx-spec/blob/development/v2.2.1/mkdocs.yml
- https://www.mkdocs.org/


## May 27, 2020

### Attendees:
- Tianon
- Steve Lasker (Microsoft)
- Mike Brown (IBM)
- Samuel Karp (AWS)
- Josh Dolitsky
- _add yourself_

### Agenda Items:
- _add your topics_

### Notes:
- Conformance updates
    - Harbor, Quay Project, ACR are making commits
    - Some discussion 
- Clients discussion, how to fetch an artifact and its SBOM vs. pulling all layers + content-adressable store. (Nisha)
    - PURL Spec https://github.com/package-url/purl-spec

## May 20, 2020

### Attendees:
- Renaud Gaubert (NVIDIA)
- Tianon
- Samuel Karp (AWS)
- Steve Lasker (Microsoft)
- Tue Tran (AWS)
- Mike Brown (IBM)
- Phil Estes (IBM)
- Mrunal Patel
- Josh Dolitsky
- Ram Chinchani
- Sean McGinnis
- Derek McGowan

### Agenda Items:
- Runc Hooks PR (Renaud Gaubert): 
  - https://github.com/opencontainers/runc/pull/2229
  - https://github.com/opencontainers/runc/pull/2402
- Reoginaizing content in the distribution spec (Josh)
    - Josh asked for [eyes on PR 152](https://github.com/opencontainers/distribution-spec/issues/152)

### Notes:
- _meeting minutes_

## May 13, 2020

Recording: https://youtu.be/E9WNkklCmuc

### Attendees:
- Tycho Andersen
- Jimmy Zelinskie
- Till Wegmueller (OpenFlowLabs)
- Tianon
- Mike Brown (IBM)
- Phil Estes (IBM) 
- Shubhra Deshpande(AWS)
- Adam Wolfe Gordon (DigitalOcean)
- Steve Lasker (Microsoft)
- Samuel Karp (AWS)
- Bryan Clark (GitHub)
- Matthew Russo (AWS)
- Nisha Kumar
- Derek McGowan
- Serge Hallyn
- Ram Chinchani
- Amye Scavarda Perrin
- Josh Dolitsky
- Jeff Borek
- Peter Engelbert
- Richard Nguyen
- _add yourself_

### Agenda Items:
- [Artifacts - Distribtuion Spec Issue #148: Referencing artifacts](https://github.com/opencontainers/distribution-spec/issues/148) & [Releases Please #23](https://github.com/opencontainers/artifacts/issues/23) - Steve
- Forming an OCIv2 Working Group - Aleksa/Till
- [runc 1.0.0-rc10+ issue with SemVer](https://github.com/opencontainers/runc/issues/2399) - Aleksa
- [Review status codes for 1.0](https://github.com/opencontainers/distribution-spec/issues/68) on distribution-spec - Josh
    - Initial CSV: [Google Sheet link](https://docs.google.com/spreadsheets/d/1uwKBnUDoaoHICIN_NlIXJTyAsAFX9eqQGcD1oJqv72g/edit#gid=0)

### Notes:

- What does it take for artifacts to be stable for something like Helm?
    - Artifacts currently is a set of guidelines that need not be versioned until there are something like metadata schemas for particular artifacts
    - Existing registries already implement OCI regardless of a 1.0 for distribution-spec
    - Dist Spec needs a clarification about mediatypes and a reference to artifacts
        - Behavior related to unknown media types had to be done on the image spec, which is confusing
    - Epics: should we A) split index/manifest out of OCI Image Spec, possibly move it over to artifacts (Derek) or B) Merge OCI Image Spec, Distribution Spec, and Artifact spec (Aleksa). Should scope of OCI be expanded to include orchestration related features, for example, CNI was originally built for runtimes not orchestrators (Jimmy), should CRI be in OCI (Derek).


## May 6, 2020

### Attendees:
- Steve Lasker (Microsoft)
- Till Wegmüller (OpenFlowLabs GmbH)
- Tianon
- Erick Carty
- Phil Estes
- Derek McGowan
- Samuel Karp (AWS)
- Adam Wolfe Gordon (DigitalOcean)
- Shubhra Deshpande (AWS)
- Josh Dolitsky (Blood Orange)
- Peter Engelbert (Blood Orange)
- Jimmy Zelinskie
- _add yourself_

### Agenda Items:
- OCI Distribution Spec 1.0 plans
- [Congrats to Vincent](https://kinvolk.io/blog/2020/05/kinvolk-welcomes-vincent-batts-as-cto/)
- _add your topics_

### Notes:
- Josh - Cleanup of the spec
    - New breakdown - do we want this pre 1.0? https://github.com/opencontainers/distribution-spec/issues/126
        - Proposed readme layout https://github.com/bloodorangeio/distribution-spec/blob/e76ed2450a9dd3feb8072d34a005c7654dd6ab23/spec.md
    - "Rewrite-in-a-comment" PR: https://github.com/opencontainers/distribution-spec/pull/146
- Derek - Get the RC out, and vote if we want to hold for other elements like the extension model Vincent has been working on
    - Conformance has been great to close down the 1.0 spec.
- Reviewing milestone for dist-spec v1.0.0
    - "vendor-specific strings in HTTP headers"
        - Link: https://github.com/opencontainers/distribution-spec/issues/26
    - "Review status codes for 1.0"
        - Link: https://github.com/opencontainers/distribution-spec/issues/68
        - Josh/Derek - should be more forgiving, for example most registries return a 201 when 202 expected: https://oci-conformance.s3.amazonaws.com/distribution-spec/distribution/push/report.html
        - Jimmy - diff between 202 vs 201 is synchronicity
    - "" 



## April 29, 2020

### Attendees:
- Steve Lasker (Microsoft)
- Samuel Karp (AWS)
- Tianon
- _add yourself_

### Agenda Items:
- _add your topics_

### Notes:
- _meeting minutes_

## April 22, 2020

### Attendees:
- Josh Dolitsky
- Samuel Karp
- Andrew Sharon
- Sean McGinnis
- Derek McGowan
- Phil Estes
- Bowen Song
- Peter Engelbert
- Ram Chinchani
- Bryan Clark
- Tianon
- Mike Brown
- Sean McGinnis
- Amye Scavarda Perrin
- Chris Aniszczyk
- Steve Lasker

### Agenda Items:
- Conformance updates (Josh)
    - Isolated workflows
    - Should we add test support for artifacts?
    - Need cloud account credentials
    - https://conformance.opencontainers.org/distribution-spec/
    - Preview: https://bloodorangeio.github.io/oci-conformance/distribution-spec/
    - PR: https://github.com/opencontainers/oci-conformance/pull/47
    - Readme: https://github.com/opencontainers/distribution-spec/blob/master/conformance/README.md
- Artifacts (Steve)
    - IANA registration for [vnd.oci.image.manifest.v1+json](https://www.iana.org/assignments/media-types/application/vnd.oci.image.manifest.v1+json) completed. This clears the way to adding registering `mediaTypes` to the publishing step.
    - As I was finishing up publishing steps, I tripped up over defining localized strings as there are many "standards" that I need to review, similar to the IANA process.
    - Will likly split out publishing of well-known types to get the spec out for approval.
    - Will focus on getting the core spec out as we need it for Notary v2 and other registries and artifact types that want to wrap up their efforts.

## April 8, 2020

### Attendees:
- Steve Lasker
- Tianon
- Phil Estes
- Samuel Karp
- Joe Exotic (aka Josh Dolitsky)
- Mike Brown
- Till Wegmueller
- Chris Aniszczyk
- Nisha Kumar
- Jimmy Zelinskie
- Shubh
- Vincent Batts
- Matthew Russo

### Agenda Items:
- _add your topics_
- Open Discussion - Expand your socially distanced circle with random topics.
    - If folks are interested in just having a community discussion of open ended items, it would be nice to chat with people outside our immediate quarantined personal and working pod.
- OCI on illumos Zones (Till)
- Carole Baskin - did she kill her husband or not?

### Notes:
- _meeting minutes_

## April 1, 2020

_video recording_: https://youtu.be/z-ujSHejhJk

### Attendees:
- Steve Lasker (Microsoft)
- Phil Estes (IBM)
- Josh Dolitsky
- Vincent Batts
- Ram Chinchani
- Jim Perrin
- Ken Brooks
- Derek McGowan
- Jimmy Z
- Mike Brown
- Peter Engelbert
- Samuel Karp (AWS)
- Tianon
- Shubh
- Amye Scavarda Perrin (CNCF)
- Andrew Sharon (AWS)
- Serge Hallyn

### Agenda Items:
- [PR# 125: WIP: spec rewrite](https://github.com/opencontainers/distribution-spec/pull/125) w/ [Readable format:](https://github.com/opencontainers/distribution-spec/blob/e76ed2450a9dd3feb8072d34a005c7654dd6ab23/spec.md)
- "Enumerate the ways in which spec.md language/layout is unclear" [issue](https://github.com/opencontainers/distribution-spec/issues/117)
- walked through the mirroring PR
- 

### Notes:
- User stories example (helm): https://github.com/helm/community/blob/master/helm-v3/011-user_stories.md

## March 25, 2020

_video recording_: https://youtu.be/KbjikGnIe5E

### Attendees:
- Vincent Batts
- Mike Brown (IBM)
- Samuel Karp (AWS)
- Josh Dolitsky
- Steve Lasker (Microsoft)
- Brandon Lum (IBM)
- Phil Estes (IBM)
- Peter Engelbert
- Ram Chinchani
- Archana Shinde
- Bowen Song
- Shubhra Deshpande (AWS)
- Maitri
- Derek McGowan
- Serge H
- Richard Nguyen (AWS)

### Agenda Items:
- (josh) Demo of new conformance tests PoC, breakdown tests into categories
    - For context: https://github.com/opencontainers/distribution-spec/issues/108
    - New wall of shame: https://github.com/bloodorangeio/oci-distribution-conformance-results/blob/split-tests/README.md
    - Updated test source (in progress): https://github.com/bloodorangeio/distribution-spec/tree/split-tests/conformance
- (derek) Extension protocol for distribution spec
    - https://github.com/opencontainers/distribution-spec/pull/111
- [Generic OCI graphics](https://github.com/opencontainers/tob/issues/65#issuecomment-604040525) feedback
- (vb) runtime-spec v1.0.2
- (vb) distribution-spec Release Candidate?
- _add your topics_

### Notes:
- (vb) open invite for folks that just want to chat. Just reach out.
- (Josh) Conformance tests
    - reviewing the "[wall of shame](https://github.com/bloodorangeio/oci-distribution-conformance-results/blob/split-tests/README.md)" and it's goals
    - 4 catagories (pull, push, discovery, management)
    - Josh to capture the list of discrepencies with the spec as issues
        - Issue to track: [#117](https://github.com/opencontainers/distribution-spec/issues/117)
    - Then, we may choose to reformat the spec [#62](https://github.com/opencontainers/distribution-spec/issues/62)
- (Vbatts) Extensions
- (steve) Graphics - people will add a bit more review, but looking great. Feedback in the [PR](https://github.com/opencontainers/tob/issues/65#issuecomment-604040525)
- (vb) Runtime spec
    - Cleanup the maintainers, from 8 down to 6
    - 
  
## March 11, 2020

_video recording_: https://youtu.be/4ifI8905VEc

### Attendees:
- Vincent Batts
- Joseph Schorr
- Nisha Kumar
- Brandon Lum (IBM)
- Tue Tran (AWS)
- Tianon
- Steve Lasker (Microsoft)
- Adrian Mouat (Container Solutions)
- Griffin Dunn (Datadog)
- Ram Chinchani (Cisco)
- Amye SP (Staff)
- Jon Johnson (Google)
- Serge Hallyn (Cisco)
- Josh Dolitsky (Blood Orange)
- Peter Engelbert (Blood Orange)
- Rose Judge
- Alec Merdler (Quay)
- Bowen Song
- _add yourself_

### Agenda Items:
- (josh) Distribution spec conformance, next steps
    - Test suite in place, but most registries failing..
        - Should we ease up the tests to be more reflective of reality?
        - Potentially break these tests down into categories, where only the baseline category required for certification. See https://github.com/opencontainers/distribution-spec/issues/108
    - Container image for release? Where to upload / multiple locations?
    - Blood Orange OCI conformance results - to be hosted by OCI?
        - View results here: https://oci.bloodorange.io/
        - Simple GitHub pages site, w/ tests running hourly via GitHub Actions cron
        - Requires auth credentials to the various registries to be stored as GitHub secrets (or otherwise)
- (joey) Pub/Sub Early Proposal introduction and overview: https://docs.google.com/document/d/1V4vaF9mSTBFbIbUUDH0mk-4KizCSFlv7oqA_4ZkD9a8
- (lumjjb) Added Encrypted mediatype PR: https://github.com/opencontainers/artifacts/pull/15
- (vbatts) extensions proposal https://github.com/opencontainers/distribution-spec/pull/111

### Notes:
- distribution-spec conformance
    - bare minimum will be tested by default
    - findings are that almost all registries have endpoints that they don't/won't implement
    - category grouping of functionality
    - tests run hourly to all publicly available registries
    - we can get this moved over to OCI org, and point something like conformance.opencontainers.org at it
- pub/sub proposal
    - this is an alternative to `_catalog` endpoint
    - the old API is expensive and only gets worse (for client and server) as the number of images/tag increases
    - this proposal is lighter, and is actually optimized to seeing most recent changes, which is the largest use-case
    - webhooks (which means the client callback need to be publically exposed)
        - There is an alternate websocket approach that is slightly more complex, but allow the client to be behind a firewall/NAT
    - catching up from a registry
    - question from lasker: can we just catch up from the last N-months? time-based hash?
    - question from vbatts: "what about the `curl` use-case?" as far as fetching this info? curl doesn't support websockets, this would have to be a client library.
    - question from dolitsky: JWK auth spec model?
- encrypted layer
    - this is a guinnea pig for artifact repo getting a new mimetype
    - lasker: is this _only_ for runnable layers, or generic?
    - this is largely generic, but since this is pre-artifacts it was only considering the runnable layer case. This should not be much of a change.
    - please to review
    - Encryption library implementation: https://github.com/containers/ocicrypt
    - Example implementations:
      - contianerd: https://github.com/containerd/cri/blob/master/docs/decryption.md
      - cri-o: https://github.com/cri-o/cri-o/blob/master/tutorials/decryption.md
      - skopeo (--decryption/encryption-key flag): https://github.com/containers/skopeo/blob/master/docs/skopeo-copy.1.md
- extensions proposal:
    - please to review and comment


## March 4, 2020

_video recording_: https://youtu.be/NUvP-J925ik

### Attendees:
- Steve Lasker (Azure)
- Matthew Russo (AWS)
- Phil Estes (IBM)
- Vincent Batts
- Nisha Kumar (VMware)
- Samuel Karp (AWS)
- Rose Judge
- Ram Chinchani
- Mike Brown
- Peter Engelbert
- Serge Hallyn
- Josh Dolitsky
- Tianon
- Amye Scavarda Perrin (CNCF)
- Andrew Sharon (AWS)

### Agenda Items:
- (phil) Quick update on TOB call/projects proposals from Monday {[notes here](https://hackmd.io/kKl1ECKnSLWhgk7dZ2WUFQ)}
- (vb) if topics are minimal, would be great to cleanup the backlog
- (josh) Misc. conformance topics
    - 1.) Breakdown of conformance into categories?
        - See https://github.com/opencontainers/distribution-spec/issues/108
    - 2.) Hosting a container image for conformance suite
        - Quay? Docker Hub?
        - Do credentials exists already?
    - 3.) "DELETE request to manifest URL (tag) MUST fail"
        - Issue: https://github.com/opencontainers/distribution-spec/issues/102
        - Proposed PR: https://github.com/opencontainers/distribution-spec/pull/105

### Notes:
- TODO(vb) quay.io/oci org things, particularly for josh and conformance
- Clean house
  - https://github.com/opencontainers/distribution-spec/issues
        - Dup of 27? https://github.com/opencontainers/distribution-spec/issues/85
        - Covered by #68 https://github.com/opencontainers/distribution-spec/issues/86
        - v1.0.0 milestone https://github.com/opencontainers/distribution-spec/milestone/3
  - https://github.com/opencontainers/runtime-spec/issues
        - https://github.com/opencontainers/runtime-spec/issues/1010#issuecomment-
        - merged https://github.com/opencontainers/runtime-spec/pull/1033
  - https://github.com/opencontainers/image-spec/issues
        - https://github.com/opencontainers/image-spec/pull/775
        - closed https://github.com/opencontainers/image-spec/pull/742
        - https://github.com/opencontainers/image-spec/pull/770
spec/issues/18
  - https://github.com/opencontainers/artifacts/pulls
  - Suggest closing: https://github.com/opencontainers/distribution-spec/issues/18
  - Suggest closing: https://github.com/opencontainers/distribution-spec/issues/22 
  - label for `vNext`https://github.com/opencontainers/distribution-spec/issues/71

## February 26, 2020

### Notes:

- Cancelled with no active agenda items


## February 19, 2020

_no video recording_

### Attendees:
- Steve Lasker
- Nisha Kumar (VMware)
- Josh Dolitsky (Blood Orange)
- Richard Nguyen (AWS)
- Samuel Karp (AWS)
- Andrew Sharon (AWS)
- Phil Estes (IBM)
- Vincent Batts
- Jon Johnson
- Ram Chinchani
- Rose Judge
- Serge Hallyn
- Ken Brooks
- Peter Engelbert
- Amye SP (OCI)
- Mike Brown (IBM)

### Agenda Items:
- Artifacts Progress - IANA registrations (Steve)
- Follow-up: image sources and SBoMs (Nisha)
- Intro to [opencontainers/oci-conformance](https://github.com/opencontainers/oci-conformance) (Josh)
- Initial thoughts on [ORAS proposal](https://github.com/opencontainers/tob/issues/66)? (Josh)

### Notes:
- Artifacts Progress -
    - registering unique mediaTypes/mime-types
    - Once the Iana media types are complete, we'll have a v1 draft of the Artifacts spec
- SBoMs and sources
    - BuildSourceImage: https://github.com/containers/BuildSourceImage
    - (WIP doc on the source image layout https://github.com/containers/BuildSourceImage/blob/018600472a893dd17681e32c2d3f74a6b696e016/layout.md)
    - mediatypes
    - cross section of source audit vs reproducibility
    - strawman: (vb) https://hackmd.io/ilHo7-SPTniX0SzF2seJ9w (Nisha) https://hackmd.io/dbRUEQRSQ268e9YWm1u2Pg
- OCI Conformance
    - repo: https://github.com/opencontainers/oci-conformance
    - example runs: https://oci.bloodorange.io/

## February 05, 2020

**video recording**:  https://youtu.be/MxPgHWM9vYM 

### Attendees:
- Steve Lasker
- Vincent Batts
- Samuel Karp (AWS)
- Rose Judge
- Jon Johnson
- Josh Dolitsky
- Peter Engelbert
- Nisha Kumar (VMware)
- Sriram Narayanan (Belenix)
- Aleksa Sarai
- Tianon
- Mike Brown (IBM)
- _add yourself_

### Agenda Items:

- Call for action to update runc's hook implementation.
- Any concerns with adopting umoci into the OCI?
- Artifacts Update (Steve)

### Notes:
- Maintainer trimming:
    - Vincent: Governance still works (still has diversity in company representation). Trouble is some maintainers are missing from the voting. 4 people in the last 2 years are not active anymore.
    - Vincent: Started a private email to current maintainers in the maintainers file. Couple of folks said they couldn't do it anymore. Vishnu for Google and (?). Maintainers file is updated. Still leaves 6 maintainers.
-  hooks_
    - https://github.com/opencontainers/runc/pull/1811
    - Call to action: if you use esoteric hooks, make sure the PR works for you.
        - *Especially* if you have to migrate to the new hooks.
    - https://github.com/opencontainers/runtime-spec/pull/1008
    - https://github.com/opencontainers/runtime-spec/issues/1010#issuecomment-581553814
- maintainers
    - https://github.com/opencontainers/runc/blob/master/MAINTAINERS_GUIDE.md#how-are-decisions-made
    - possibly time to revisit aspects of the charter, regarding the 2/3 quorum everywhere. It's a rough bar for some of the projects (non spec).
    - possibly also revisit self-LGTMs as well(?)
- umoci
    - https://github.com/opensuse/umoci
    - and merge aspects of image-tools for validation
    - Tych0 interested in being a maintainer
- Artifacts
    - Steve - reviewing iana.org for mediaType unqiueness. Looks very promising as it supports multiple scopes for vendors (vnd.), personal (prs.) and unregistered (x.) for cloud or customer specific referneces 
    - 3T SBOM, Notary and OPA conversations evolving for e2e policy enforcement of signed artifacts
    - Closing the loop with gpl license compliance, using artifacts to store SBOMs which reference packages, that require the source to be stored alongside the binaries (images) in the registry. The gpl source would have it's own mediaType - see iana.org.
    - (vb) source containers, and "equivalent access"
    - (aleksa) redirect to origination like SUSE open build service
    - (nisha) but why new mediatype than 'text' or 'application/json'
    - (aleksa) It's not that we're not using JSON, but that client tools can actually support looking for a particular type of document, rather than guessing
    - (aleksa) we should choose a approach, and not block folks from extending and using their own, because they will.
    - (nisha) this is being approached from a distro perspective, but what about pypi, golang, etc. This needs a specific conversation.
        - (aleksa) also things like configuration files are a real headache
    - (vb) let's have a discussion
    - (Steve) Notary v2 [Separation of Concerns](https://docs.google.com/document/d/1u3NSJP5j65cdZHSMFALtvHno4YhbGVK6opYaO-vBOzc/) doc discussing how we can work independtly on these various effors, but leverage them together, end to end 
    - (aleksa) One more thing -- we need to consider whether individual SBOM entries (per-package) should also be signed (or be verifiable in some fashion) so if a user installs a package in their own """layer""" then it should be clear that the package is from a distro.
    - (Steve) the 3T SBOM format can refernece other SBOMs. This way the SBOM associated with a container image can reference all the SBOMs of all the packages added for the app, and all the SBOMs for the base layers. Each, signed with Notary v2 and pushed to a registry, likely referened through an OCI Index, or a property in the OCI manifest (later detail TBD).

## January 29, 2020

**video recording**:  https://youtu.be/LZwvzpFxtFU

### Attendees:
- Tianon
- Samuel Karp (AWS)
- Amye Scavarda Perrin (OCI)
- Josh Dolitsky (Blood Orange)
- Peter Engelbert (Blood Orange)
- Vincent Batts
- Steve Lasker

### Agenda Items:
- (jdolitsky) Conformance updates
- Registry Import API (Steve Lasker)
The ability to move content between registries, including the ability to persist content genericlaly as an offline blob is a common request we get on ACR. As we support air-gapped environemnts, we're curious if other registry operators are interested in collaborating on an export/import api.
- (vbatts) trim some maintainers

### Notes:
- (jdolitsky) Conformance updates
    - [distribution-spec#82](https://github.com/opencontainers/distribution-spec/pull/82) has been merged!
    - Test suite available [here](https://github.com/opencontainers/distribution-spec/tree/master/conformance)
    - Non-official GitHub action available [here](https://github.com/bloodorangeio/oci-test-action)
        - Example workflows using the action [here](https://github.com/bloodorangeio/oci-distribution-conformance-results/tree/master/.github/workflows)
        - PR submitted to make this part of spec itself: [distribution-spec#89](https://github.com/opencontainers/distribution-spec/pull/89)
    - Non-official, preliminary table of results: https://oci.bloodorange.io/
    - PR to add tests for error codes: (in progress rn...)
    - Began setting up OCI conformance program
        - Fork: https://github.com/bloodorangeio/oci-conformance
        - Based heavily on https://github.com/cncf/k8s-conformance 
- Import API
    - Could it be an extension of the existing get APIs
    - Would this be a synching API?
        - while it might be extended to support, it's not the immediate intent. But,it should support a collection, or scope. Such as a multi-arch manifest that copies the index and manifest contents. It should also copy the eventual signatures and other relevant content.
    - Some interest from others. Steve to start some proposals for others to contribute to
- Trim maintainers
    - https://github.com/opencontainers/runtime-spec/blob/master/MAINTAINERS
    - https://www.opencontainers.org/about/governance
- house keeping of issues and PRs is welcome
- options for kubecon
    - Amye has these threads open, and we'll know once she's heard anything

## January 22, 2020

### Attendees:
- Tianon
- Josh Dolitsky (Blood Orange)
- Peter Engelbert (Blood Orange)
- Steve Lasker (Microsoft)

### Agenda Items:
- (jdolitsky) [distribution-spec#82](https://github.com/opencontainers/distribution-spec/pull/82) ready to merge?

### Notes:
- Didn't hvae much of an agenda prior, so it appears many didn't attend. 
- Just a reminder to get an agenda in by the Friday before to give folks time to plan. This was a 3 day weekend as well.
- Quick convo about the PR from Josh and Peter. More eyes to review and possibly approve the PR.

## January 15, 2020 

*recording available*: https://youtu.be/xlHLZhgpn4E 

### Attendees:
- Josh Dolitsky (Blood Orange)
- Peter Engelbert (Blood Orange)
- Phil Estes (IBM)
- Vincent Batts
- Mike Brown (IBM)
- Sean McGinnis (Dell)
- Samuel Karp (AWS)
- Steve Lasker (Azure)
- Amye Scavarda Perrin 
- Jon Johnson
- Nisha Kumar
- Serge
- Tianon
- Ram Chinchani (Cisco)
- Derek McGowan

### Agenda Items:
- (vb) runtime-spec v1.0.2 vote
    - https://github.com/opencontainers/runtime-spec/pull/1026
- (vb) go-digest v1.0.0?
- (jdolitsky) distribution-spec conformance updates
- KubeCon EU Meeting? (Steve)
- Notary v2 quick update (Steve) - if time permits


### Notes:
- Need active maintainers to even get a 2/3 quorom on release vote
- distribution conformance met on monday
    - https://www.youtube.com/watch?v=rb977-K90Vk
    - Preliminary test results: https://oci.bloodorange.io/
    - Conformance test source: https://github.com/bloodorangeio/distribution-spec/tree/master/conformance
        - Planning to PR this to master soon
    - kubernetes conformance example: https://github.com/cncf/k8s-conformance/tree/master/v1.15
    - Potential GCR auth issue
        - https://github.com/containerd/containerd/issues/1318#issuecomment-327277368
        - See also https://github.com/genuinetools/reg/blob/d959057b30da67d5f162790f9d5b5160686901fd/registry/tokentransport.go#L170
- kubecon EU
    - Opportunity for a Pre-Con event on Monday. Steve to work with Amyee on logistic possibilities.
    - stevelasker to have a proposal on time and place by next week
- notary v2
    - while that effort touches heavily to OCI stuffs, notary is it's own (CNCF) project, so it now is coordinating on the CNCF calendar and has its own call on Mondays
    - https://www.cncf.io/community/calendar/
- How do we get to a 1.0 for distribution
    - Vincent considering the feature flag discussion if it will impact the 1.0 spec, or it will be additive
    - error codes, conformance, pubsub discussion from jschorr?
    - 

## January 8, 2020

**recording available**: https://youtu.be/YLHcOGuawr8 

### Attendees:
- Josh Dolitsky (Blood Orange)
- Peter Engelbert (Blood Orange)
- Steve Lasker (Azure)
- Vincent Batts
- Tianon
- Phil Estes
- Jeff Borek
- Serge Hallyn
- Amye Scavarda Perrin
- Derek McGowan
- Ram Chinchani
- Tue Tran (AWS)
- Andrew Sharon (AWS)
- Sam Bernings (AWS)
- Lahiru (AWS)
- Justin Cormack
- Samuel Karp (AWS)
- Trishank Kuppusamy
- Sean McGinnis
- Nisha Kumar
- Samuel McGraw
- Chris Aniszczyk
- Mike Brown

### Agenda Items:
- Distribution conformance update (jdolitsky)
- runtime-spec release (and then runc release? ;-) (vbatts)
- Also the hooks PR for runtime-spec has been merged. This was the last item holding back runc from settling on a 1.0.0
- the Notary v2 discussion may have some items as well 

### Notes:
- (josh) conformance stuffs
    - https://github.com/bloodorangeio/distribution-spec/tree/master/compliance
    - Model after k8s-conformance: https://github.com/cncf/k8s-conformance
    - at first investigated using quay tests, but too wide of scope, python, and too many quay specifics
    - then looking at zot tooling. The test suite they chose was not flexible enough for gerenal conformance comparison
    - gingko + resty
    - "reggie" (vbatts lols)
        - simple client library that provides visual parity with the spec and auth support
        - https://github.com/bloodorangeio/reggie
    - (vb) is this built as a binary? or run as test?
        - it is `go test`
    - (vb) is the output machine parsible for comparison or putting into a table?
        - output is `junit.xml` and `report.html`
    - (vb) is there a possible scale/grade so we can evaluate SHOULD, SHOULD NOT, MAY, and MAY NOT
    - https://github.com/cncf/k8s-conformance/pull/726
    - https://github.com/cncf/k8s-conformance/pull/726/files#diff-24a94212f270a1fce398bc07e08e68b3
- (vb) expect some house cleaning and release votes for a couple of the projects
    - of note: Hooks issue in runc - https://github.com/opencontainers/runtime-spec/pull/1008 is closed 
- (justin) notary v2
    - likely to have a seperate standing call, and only check-ins during this OCI call
    - hopefully morning pacific coast
    - Steve to get a draft of scenarios done by EOW for discussion, review and editing
    - https://docs.google.com/document/d/1RVNhuQIZWv6NqQkV3sOKphMZbl_6PXQtf9ZPv7wiEms/edit 
    - Steve: will include tag signing as part of the use cases/scenarios
    - (vb) thinking through feature flags and something like OEP for handling proposals that span specs/projects
    - (justin) there was thoughts and concerns on storing the signature. Derek and I had conversations and he has strong opinions about this. 
    - signed tags?
    - (nisha but tags are mutable
    - right
- (borek) it's good to see OCI being an ongoing place of open collaboration
- (trishank) where will the doodle be shared for finding a good time for notary calls?
    - (vb) dev@opencontainers.org and #notary-v2 on the cncf slack
