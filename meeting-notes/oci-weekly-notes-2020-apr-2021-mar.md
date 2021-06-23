# OCI Weekly Dev Meeting Notes Archive - April 2020 to March 2021

## March 31, 2021
**Recording:** https://www.youtube.com/watch?v=09NkIzIZhpM

### Attendees:
- Steve Lasker (Microsoft)
- Phil Estes (AWS)
- Nisha Kumar (VMware)
- Justin Cormack (Docker)
- Chris Aniszczyk (LF)
- Brandon Klein (Sandia National Labs)
- Mike Brown (IBM)
- Josh Dolitsky
- Sarah Novotny (Microsoft)
- Aidan Delaney
- Derek McGowan
- Samuel Karp (AWS)
- Mark Peek (VMware)
- Amye SP (LF)
- Bo Liu (Alibaba Cloud)
- Hank Donnay (Quay)
- Jon Johnson (Google)
- Jason Hall (Red Hat)
- _add yourself_

### Agenda

Reserving the majority of time to discuss how registries can support additional concepts. Including properties, linked references and signing.

**Can we instead go over the topics that were preempted on the 24th first? Specifically:
    ""- We have a few design choices that are based on whether we can or can't make changes to the existing manifests. Let's discuss what and how we'd make changes as this will focus our proposals going forward.
"

We'll start with [Justins proposal](https://gist.github.com/justincormack/523dc229f0dd7b882edf19c60aed1581) as it's the most holistic. If we beleive it's the general north star, the [references PR](https://github.com/opencontainers/image-spec/pull/828) and [oci.artifact.manifest spec](https://github.com/opencontainers/artifacts/pull/29) become moot.

The [Descriptors as first-class manifests](https://github.com/opencontainers/distribution-spec/issues/252) is an additional concept. I suspect the above will take the majority of the hour. If something changes, we can bring this in.

### Actionable Agenda Items:
- Audit OCI Inactive Maintainers + Call For New Maintainers: https://github.com/opencontainers/tob/issues/95

### Presentation/Discussion Agenda Items

- [Justin's draft doc](https://gist.github.com/justincormack/523dc229f0dd7b882edf19c60aed1581) (Justin)
- How to add schema, and change rules to `image.manifest` and `image.index` (Steve)
  - We have a few design choices that are based on whether we can or can't make changes to the existing manifests. Let's discuss what and how we'd make changes as this will focus our proposals going forward.
- [Follow-up discussions about references](https://github.com/opencontainers/image-spec/pull/828) (Dan)
- [Linked Artifacts, enabling Notary v2, SBoMs, Nydus and other types](https://github.com/opencontainers/artifacts/pull/29) (Steve)
- [Descriptors as first-class manifests](https://github.com/opencontainers/distribution-spec/issues/252) (Jon)
- [Deduplicate uploads](https://github.com/opencontainers/distribution-spec/issues/236) (Sargun)
- **Announcement**: Distribution Spec v1.0.0-rc2 [released ](https://groups.google.com/a/opencontainers.org/g/dev/c/Ga-ZYyAab8w/m/wbWL2iQ8BgAJ) (Josh)
    - v1.0.0-rc3 will be the last release before v1.0.0
    - See [v1.0.0-rc3 milestone](https://github.com/opencontainers/distribution-spec/milestone/7) for last minute items
- _add your items_

### Notes:
 - **Important note** for anyone who sees the agenda above and wants to watch the recording to learn about those items: **please note** that we set the agenda aside today to talk through ways to reorganize current efforts within the OCI and help navigate some of the "stuck-ness" being experienced due to lack of active maintainer participation in some OCI projects. Please *do* watch the recording and provide us feedback on how to structure the working groups in a way that will meet the needs of the OCI constituent groups. - *Phil on behalf of the TOB.*

## March 24, 2021
**Recording:** https://www.youtube.com/watch?v=X6jeM4gAQAs

### Attendees:
- Steve Lasker (Microsoft)
- Jason Hall (Red Hat)
- Phil Estes (AWS)
- Justin Cormack (Docker)
- Nisha Kumar (VMware)
- Aidan Delaney
- Dan Lorenc (Google)
- Marina Moore (NYU)
- Josh Dolitsky
- Bo Liu (Alibaba Cloud)
- Brian Goff (Microsoft)
- Derek McGowan
- Samuel Karp (AWS)
- Michael Brown (AWS)
- Brandon Klein (Sandia National Labs)
- Mike Brown (IBM)
- _add yourself_

### Actionable Agenda Items:
- [Base image annotations](https://github.com/opencontainers/image-spec/pull/822) (Jason)
- [Fix CI?](https://github.com/opencontainers/image-spec/pull/814) (jon/vbatts)
    - TODO: Move image to OCI org on Docker Hub
    - TODO: Move to GitHub Actions
    - TODO: Get more image-spec maintainers
- [Merge `data` field?](https://github.com/opencontainers/image-spec/pull/826) (Jon)
    - TODO: Define a minimum size that implementations SHOULD support?

### Presentation/Discussion Agenda Items:
- How to add schema, and change rules to `image.manifest` and `image.index` (Steve)
    - We have a few design choices that are based on whether we can or can't make changes to the existing manifests. Let's discuss what and how we'd make changes as this will focus our proposals going forward.
- [Descriptors as first-class manifests](https://github.com/opencontainers/distribution-spec/issues/252) (Jon)
- [Follow-up discussions about references](https://github.com/opencontainers/image-spec/pull/828) (Dan)
- [Linked Artifacts, enabling Notary v2, SBoMs, Nydus and other types](https://github.com/opencontainers/artifacts/pull/29) (Steve)
- [Justin's draft doc](https://gist.github.com/justincormack/523dc229f0dd7b882edf19c60aed1581) (Justin)

### Notes:
- 

## March 17, 2021
**Recording:** https://www.youtube.com/watch?v=gFZQplmiSDc

### Attendees:
- Vincent Batts (kinvolk)
- Steve Lasker (Microsoft)
- Tianon
- Jon Johnson
- Samuel Karp (AWS)
- Dan Lorenc (Google)
- Mike Brown (IBM)
- Phil Estes (AWS)
- Bo Liu (Alibaba))
- Aidan Delaney
- Brandon Klein (Sandia National Labs)
- Mark Peek (VMware)
- _add yourself_

### Actionable Agenda Items:
- https://github.com/opencontainers/image-spec/pull/822
    - Standard Base Image Annotations
    - Please review or give actionable feedback.
- https://github.com/opencontainers/image-spec/pull/826
    - Please review or give actionable feedback.
- 

### Presentation/Discussion Agenda Items:
- https://github.com/opencontainers/distribution-spec/pull/251
- Linking Proposal (Dan): https://github.com/opencontainers/image-spec/pull/828 and https://github.com/opencontainers/image-spec/issues/827

### Notes:

## March 10, 2021
**Recording:** https://www.youtube.com/watch?v=GBrUEctHkYg

### Attendees:
- Phil Estes (AWS)
- Steve Lasker (Microsoft)
- Mike Brown (IBM)
- Tianon
- Josh Dolitsky
- Aidan Delaney
- Brian Goff (Microsoft)
- Brandon Klein (Sandia National Labs)
- Samuel Karp (AWS)
- _add yourself_
### Actionable Agenda Items:
- _add your items_

### Presentation/Discussion Agenda Items:
- [`Content-Encoding`](https://github.com/opencontainers/distribution-spec/issues/235) (Jon)
- [`Upload deduplication`](https://github.com/opencontainers/distribution-spec/issues/236) (Sargun)
- [Base image annotations proposal](https://github.com/opencontainers/image-spec/pull/822) going back to describing a single base image (Jason; can't attend)

### Notes:


## March 3rd, 2021
**Recording:** https://www.youtube.com/watch?v=WwZplxfZ0fk

### Attendees:
- Mike Brown (IBM)
- Phil Estes (AWS)
- Bo Liu (Alibaba Cloud)
- Steve Lasker (Microsoft)
- Samuel Karp (AWS)
- Aidan Delaney
- Mark Peek (VMware)
- Jon Johnson
- _add yourself_

### Actionable Agenda Items:

- Base image annotation PR [image-spec#822](https://github.com/opencontainers/image-spec/pull/822)
- _add your items_

### Presentation/Discussion Agenda Items:
- [`Content-Encoding`](https://github.com/opencontainers/distribution-spec/issues/235) (Jon)
- Descriptor [`data` field](https://github.com/opencontainers/image-spec/blob/master/descriptor.md#reserved) (Jon)
- Monolithic uploads + deprecation | Pt. 2 (Josh)
    - [Original issue](https://github.com/opencontainers/distribution-spec/issues/234)
    - PR: (https://github.com/opencontainers/distribution-spec/pull/239)
        - Is this good now? https://github.com/opencontainers/distribution-spec/pull/230
    - After merged,  will proceed with distribution-spec v1.0.0-rc2 release
    - RC2 milestone (FYI) https://github.com/opencontainers/distribution-spec/milestone/5
    - New readme: https://github.com/opencontainers/distribution-spec/blob/master/README.md
- What’s the story with ORAS? | Pt. 2 (Josh)
    - Will not be a supported OCI project
    - Maybe to be submitted into CNCF sandbox (adoption from Helm/OPA/etc, and uses Containerd Go libraries)
    - Build a pure OCI distribution client as a [Umoci CAS Engine](https://github.com/opencontainers/umoci/blob/master/oci/cas/cas.go#L65) implementation and see where that goes (do what `skopeo copy` does)
    - Maybe later ORAS drops Containerd under the hood and uses the Umoci library once it matures


### Notes:

## February 24, 2021

### Agenda Items:
- Cancelled

## February 17, 2021
**Recording:** https://www.youtube.com/watch?v=x4TTgLRVumE

### Attendees:

- Jason Hall (Red Hat)
- Phil Estes
- Steve Lasker (Microsoft)
- Josh Dolitsky
- Wayne Warren (Digitalocean)
- Mark Peek (VMware)
- Samuel Karp
- William Fielder (Red Hat)
- Tianon
- Mike Brown (IBM)

### Actionable Agenda Items:
- _add your items_

### Presentation/Discussion Agenda Items:
- [Proposal: Standard Base Image Annotations](https://github.com/opencontainers/image-spec/issues/821) ([@ImJasonH](https://github.com/imjasonh))
    - https://hackmd.io/EKf0U1b7Reu5FneC1dQgXw?view
    - There was general agreement that these additional image annotations for the base manifest and reference are useful extensions. A PR will be opened against opencontainers/image-spec.
- [Is it time to adopt extensions? Discussion #238](https://github.com/opencontainers/distribution-spec/discussions/238)? (Steve)
    - General concensus to move forward with `_ext/` model. A discussion for numbered or named extensions. Steve to reachout to Vincnent, Derek and Cormack as they all expressed interest as well.
- _add your items_

### Notes:

## February 10, 2021
**Recording:** https://www.youtube.com/watch?v=2xRfoKhdAcM

### Attendees:
- Tianon
- Steve Lasker (Microsoft)
- Jon Johnson
- Mark Peek
- Nisha Kumar
- Bo Liu (Alibaba Cloud)
- Brian Goff (Microsoft)
- Samuel Karp
- Brandon Lum (IBM)
- Josh Dolitsky
- Amye SP (OCI)
- Fu, Wei (Alibaba Cloud)
- _add yourself_
- 

### Actionable Agenda Items:
- _add your items_

### Presentation/Discussion Agenda Items:
- Monolithic uploads + deprecation (Jon)
    - https://github.com/opencontainers/distribution-spec/issues/234
- [OCI Artifact Manifest](https://github.com/opencontainers/artifacts/blob/3e34f029537052639eed59b469cb6c43706ac3d0/artifact-manifest.md) Update [PR #29](https://github.com/opencontainers/artifacts/pull/29)- I've reduced this down to the reverse lookup capabilities of a `manifests` collection.  
  Weak `references` to other artifacts are deferred until we can work through the [registry/repo mapping discussions](https://github.com/notaryproject/nv2/discussions/31) (Steve)

### Notes:

 
## February 3, 2021
**Recording:** https://www.youtube.com/watch?v=0RZXhmqS_OE

### Attendees:
- Tianon
- Mike Brown (IBM)
- Phil Estes
- Jon Johnson
- Samuel Karp
- Mark Peek
- William Fielder
- Ram Chinchani
- Adam Wolfe Gordon
- Erwin van Eyk
- Jimmy Z
- Neelendra Bhandari
- Petar Galic
- Serge Hallyn
- Shivam Mishra
- Toddy Mladenov
- William Lambert
- Nisha Kumar
- Josh Dolitsky

### Actionable Agenda Items:
- _add your items_

### Presentation/Discussion Agenda Items:
- CReB -- a Container Registry Benchmark
    - Petar Galic (Vrije Universiteit Amsterdam) presentation & ideas for further collaboration
    - https://github.com/pgalic96/registry_benchmark
- Listing stuff (Jon)
    - [Proposal: Add a manifest list API #222](https://github.com/opencontainers/distribution-spec/issues/222)
    - [Listing API Requirements #229](https://github.com/opencontainers/distribution-spec/pull/229)
    - [Show/Get-Info API Requirements #232](https://github.com/opencontainers/distribution-spec/pull/232)
- ETags + 412 thoughts (Jon)
    - https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/ETag
    - https://tools.ietf.org/html/rfc7232#section-2.3
- _add your items_

### Notes:

- Viewable link of the CReB presentation: https://docs.google.com/presentation/d/1vL4a8Wfr4pHmOUxgBF6JA1mOfcfoolVRbHwPsmXbxQo/edit?usp=sharing
- KEP-like proposal format would be useful (vbatts extensions were similar?)
- "We got off a little bit in the weeds." -Steve  (QOTD)

## January 27, 2021
**Recording:** https://www.youtube.com/watch?v=VQ60WB1IvI8

### Attendees:
- Mike Brown (IBM)
- Tianon
- Hank Donnay (quay)
- Neil Johnson
- Jon Johnson
- Adam Wolfe Gordon
- Brian Goff
- Derek McGowan
- Josh Dolitsky
- Kershaw Mehta
- Neelendra
- Nisha Kumar
- Peter Engelbert
- Phil Estes
- Ram Chinchani
- Samuel Karp
- Shivam Mishra
- Steve Lasker (Microsoft)
- Bo Liu (Alibaba Cloud)
- William Fielder (Red Hat)
- Tao Peng (Ant Group)
- Vincent Batts
- Amye Scavarda Perrin
- Serge Hallyn (Cisco)

### Agenda Items:
- IBM z/OS as a Native Platform for OCI
  - Neil Johnson (IBM z/OS) brief introduction(s)
- What's the story with ORAS? (Josh + Nisha)
    - How can it be redesigned to work better with images?
    - See: https://github.com/opencontainers/tob/pull/68
    - Perhaps (josh)
        - `umoci new --image new_image:new_tag --cache ./someplace`
        - `oras push new_image:new_tag --cache ./someplace`
        - OR `umoci new --image new_image:new_tag --export | oras push --stdin`
    - building blocks discussion: https://github.com/google/go-containerregistry/blob/main/pkg/v1/remote/transport/README.md
- Distribution-spec release check in (Josh)
    - 1.0.0-rc2 milestone: https://github.com/opencontainers/distribution-spec/milestone/5
    - Targeting end of feb. SPEAK NOW OR HOLD PEACE
- Initial discussions for [OCI Artifact Manifest](https://github.com/SteveLasker/artifacts/blob/artifact-manifest/artifact-manifest/artifact-manifest.md) for managing reference types like Notary v2, Helm, CNAB, WASM and others (Steve)
    - More artifact like [nydus image](https://github.com/dragonflyoss/image-service/blob/master/docs/nydus-design.md), [nydus artifact type](https://github.com/liubogithub/artifacts/blob/oci/artifact-manifest/artifact-manifest.md#nydus-image-reference) (Bo Liu)
- Updates on Seccomp Notify in OCI runtime-spec and runc.
  - [PR#1074](https://github.com/opencontainers/runtime-spec/pull/1074) (spec)
  - [runc PR#2682](https://github.com/opencontainers/runc/pull/2682) (implementation in runc)
- Listing stuff (Jon)
    - https://github.com/opencontainers/distribution-spec/issues/222


### Notes:

- IBM z/OS as a Native Platform for OCI
  - Possibly similar to Windows LCOW/WCOW, so possible collaboration with the Windows folks
- ORAS and Images
    - Unable to pull from Docker Hub
    - Historical question why ORAS doesn't support images. Is that part of the goal?
    - Should we add a roadmap for ORAS to OCI
    - Nisha - using Docker and Buildah
    - Would like push and build in-sync with each other
    - Isn't a client tool that supports OCI Artifact type images. Can ORAS be that tool?
    - Steve - ORAS was initiall intended to deal with everything else that would get pushed to a registry that wasn't an image. It could reference images, but not meant to manipulate images as there are other tools.
    - Steve [Added Discussions to ORAS](https://github.com/deislabs/oras/discussions/) to enable further collaboration and discussions
    - Phil - there area a bunch of registry tools evolving in GitHub. 
    - [TOB Notes for ORAS discussion](https://github.com/opencontainers/tob/pull/76)
- Artifacts
    - Jon
        - weak references in the registry would be a generally useful abstraction
        - wary of intermingling mutable things within the CAS

## January 20, 2021

### Agenda Items:
- Cancelled

## January 13, 2021

### Agenda Items:
- Cancelled, no agenda items

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
