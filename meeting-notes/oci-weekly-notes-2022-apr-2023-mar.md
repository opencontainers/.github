# OCI Weekly Dev Meeting Notes Archive - April 2022 to March 2023

## March 30, 2023

**Recording**: https://youtu.be/ERJPxtL5WjM

### Attendees:
- Brandon Mitchell
- Ramkumar Chinchani
- Tianon Gravi
- Aaron Friel
- Jon Johnson
- Jesse Butler
- Victor Lu
- Derek McGowan
- Jamie Wu
- Brandon Klein
- Michael Brown
- Jason Hall
- _add yourself_

### Note Taker:
- _add note taker_

### Actionable Agenda Items:
- Who's taking notes?
- Nits and shifting layer requirements: <https://github.com/opencontainers/image-spec/pull/1042>
- Add artifactType to image manifest: <https://github.com/opencontainers/image-spec/pull/1043>
- Define artifactType usage in referrers API response: <https://github.com/opencontainers/distribution-spec/pull/395>
- Archiving `artifacts` repo: <https://github.com/opencontainers/artifacts/issues/63>
- _add your items_

## March 23, 2023

**Recording**: https://youtu.be/w-FWd986Qic

### Attendees:
- Brandon Mitchell
- Aaron Friel
- John Kjell
- Ramkumar Chinchani
- Brandon Klein
- Jason Hall
- Jon Johnson
- Amye Scavarda Perrin
- Derek McGowan
- Jesse Butler
- ToddySM
- Victor Lu
- Tianon Gravi
- Samuel Karp
- _add yourself_

### Note Taker:
- _add note taker_

### Actionable Agenda Items:
- Who's taking notes?
- Warning header merged! 🎉 https://github.com/opencontainers/distribution-spec/pull/393
- <https://github.com/opencontainers/image-spec/pull/1029>
  - Should this be split into two PRs? (to get the nits merged)
  - How do we want to handle `mediaType` -> `artifactType` for artifacts without a dedicated config (pushing the scratch blob)
    - Opt 1: scratch = null so `mediaType` can mismatch content
    - Opt 2: custom `mediaType` extension (`+oci`)
    - Opt 3: define `artifactType` in the config descriptor
    - Opt 4: define `artifactType` in the image manifest
    - Option 4 was preferred by the team
- **Did not get to the below agenda items**
- Artifact manifest removal
  - merged in distribution-spec: <https://github.com/opencontainers/distribution-spec/pull/383>
  - image-spec: <https://github.com/opencontainers/image-spec/pull/999>
    - Need for updated RC to communicate to partners. Added by @sajay but might not able to make it this weeek and if the folks on the call want, we can move out to next week.
- Request for comments and review on https://github.com/opencontainers/image-spec/pull/1030
- Add insecure HTTPs support in conformance tests: https://github.com/opencontainers/distribution-spec/pull/394

Example of option 4:

```json
{
  "schemaVersion": 2,
  "mediaType": "application/vnd.oci.image.manifest.v1+json",
  "artifactType": "application/vnd.cyclonedx", // add new artifact type
  "config": {
    "mediaType": "application/vnd.oci.artifact.scratch.config.v1+json", // use static media type when artifactType defined
    "size": 2,
    "digest": "sha256:44136fa355b3678a1146ad16f7e8649e94fb4fc21fe77e8310c060f61caaff8a"
  },
  "layers": [
    {
      "mediaType": "application/vnd.cyclonedx+json",
      "size": 15362,
      "digest": "sha256:216c9f9553bf811a4ff2d6d60f0b007752414805e1bb62611282481837cf7def"
    },
    {
      "mediaType": "application/vnd.cyclonedx+xml",
      "size": 15362,
      "digest": "sha256:216c9f9553bf811a4ff2d6d60f0b007752414805e1bb62611282481837cf7def"
    }
  ],
  "annotations": {
    "org.opencontainers.artifact.created": "2023-03-03T19:42:34Z",
    "org.opencontainers.artifact.description": "CycloneDX JSON SBOM"
  },
  "subject": {
    "mediaType": "application/vnd.oci.image.manifest.v1+json",
    "size": 1024,
    "digest": "sha256:81b44ad77a83506e00079bfb7df04240df39d8da45891018b2e5e00d5d69aff3"
  }
}
```



## March 16, 2023

**Recording**: https://youtu.be/U9GXGABqP0Y

### Attendees:
- _add yourself_
- Josh Dolitsky
- Jason Hall
- Brandon Mitchell
- Jon Johnson
- Sajay Antony
- ToddySM
- Tianon Gravi
- Aaron Friel
- Mike Brown (IBM)
- Ramkumar Chinchani

### Note Taker:
- _add note taker_

### Actionable Agenda Items:
- Who's taking notes?
- RFC: server-sent warnings: https://github.com/opencontainers/distribution-spec/issues/390
  - deprecation vs warning header?
  - https://datatracker.ietf.org/doc/html/draft-dalal-deprecation-header-00#page-7
- Guidance for registry/client tool implementers wrt "artifacts"? This is holding up progress/releases.
  - https://github.com/opencontainers/image-spec/pull/1029
      - [Jon] Add a `+oci` [structured suffix](https://www.iana.org/assignments/media-type-structured-suffix/media-type-structured-suffix.xhtml) for single-layered artifacts?
  - Will this get a review after 1029? https://github.com/opencontainers/image-spec/pull/1030
- Minimum chunk size: https://github.com/opencontainers/distribution-spec/pull/391

## March 9, 2023

**Recording**: https://youtu.be/4qOyBLVTJaA

### Attendees:
- _add yourself_
- Aaron Friel
- Phil Estes (AWS)
- Brandon Klein
- Mark Rossetti
- James Sturtevant
- Bradley D. Thornton
- Ramkumar Chinchani
- Mike Brown (IBM)
- Sajay Antony
- Brian Goff (MSFT)
- Tianon Gravi
- Brandon Mitchell
- Jamie Wu
- Lachlan Evenson
- Michael Brown
- Syed Ahmed
- ToddySM
### Note Taker:
- _add note taker_

### Actionable Agenda Items:
- Who's taking notes?
- containerd security issue w/ large configs: https://github.com/containerd/containerd/security/advisories/GHSA-259w-8hf6-59c2
    - should OCI recommend a
- Last arg for clean Artifact Manifest. We are very close to standardizing something that will yield CVEs for years to come by overloading Image Manifest and standardizing the current behavior of registry implementations while ignoring the cost of additional complexity and ambiguity on client implementations. Overloading type definitions leads to type confusion and parsing vulnerabilities. Known issues:
  - The above issue with large configs is completely relevant. If artifacts upload arbitrary sized blobs to configs, runtime spec would like to specify that blobs have a limit when used in the config field.
  - Removing `mediaType` from manifests resulted in type confusion
    This is exactly what we're proposing to do for config blobs: the descriptor will describe the "artifactType", not the content of the blob.
    https://github.com/advisories/GHSA-qq97-vm5h-rrhg
    & https://www.cvedetails.com/cve/CVE-2021-41190/
  - Clients do not handle arbitrary/malformed image content well, e.g.: plausible path to RCE in Anchore when it scans a "specially crafted manifest".
    With lowercase-a artifacts, we expose more clients to arbitrary content. If we standardize this and encourage it, we have not done an analysis like [#1025](https://github.com/opencontainers/image-spec/issues/1025) on client behavior.
    https://www.cvedetails.com/cve/CVE-2020-11075/
  - Docker clients crashed due to trusting layers, blobs were valid for Images content ([see commit](https://github.com/moby/moby/commit/8d3179546e79065adefa67cc697c09d0ab137d30)).
    Just as with Anchore, we have not modeled the impact of giving arbitrary content to clients which trusted content to be configs & layers.
    https://www.cvedetails.com/cve/CVE-2021-21285
  - quay/claircore may have exactly this type of vulnerability here. Is it generally safe to treat any blob whose mediaType terminates in in ".tar" as a tarball? No! The media type of the config blob is undefined post-999.
    https://github.com/quay/claircore/blob/35f60dd69a229051d0c494b959bbc023842bd98e/libindex/fetcher.go#L261-L291
- Updating the image manifest, approval needed for at least one:
  - <https://github.com/opencontainers/image-spec/pull/1023>
  - <https://github.com/opencontainers/image-spec/pull/1029>
  - <https://github.com/opencontainers/image-spec/pull/1030>
- Request to remove blob delete from conformance tests (email from JFrog)
- Fix JSON Schema: <https://github.com/opencontainers/image-spec/pull/931>
- Chunked uploads need a minimum size header from the server: <https://github.com/opencontainers/distribution-spec/issues/374>


### Presentation/Discussion Agenda Items:
- _add your items_
- Windows LayerFolder https://github.com/opencontainers/runtime-spec/issues/1185

### Notes:

## March 2, 2023

**Recording**: https://youtu.be/lZ7LRwgEVTQ

### Attendees:
- Lachlan Evenson
- Brandon Mitchell
- Ramkumar Chinchani
- ToddySM
- Sajay Antony
- Tianon Gravi
- Aaron Friel
- Vincent Batts
- Amye SP
- Jesse Butler
- Michael Brown
- Brandon Klein
- John Kjell
- Phil Estes
- Mike Brown(IBM)


### Note Taker:
- _add note taker_

### Actionable Agenda Items:
- Who's taking notes? (Lachlan Evenson)
- _add your items_

### Presentation/Discussion Agenda Items:
- decision on 999
    - https://github.com/opencontainers/image-spec/pull/999
        - Can we consider codifying lower a artifacts into image-spec prior to this (aaron)
        - We need to codify the way to use image space prior to consider merging this PR (vbatts)
        - Do we have an action plan to merge 999? In order to merge 999 these things must first be merged? (vbatts)
        -
- Cleanup PRs
    - https://github.com/opencontainers/image-spec/pull/1013 - closed
    - https://github.com/opencontainers/image-spec/pull/1016 - closed
- descriptor schema: add missing data and artifactType definitions
    - https://github.com/opencontainers/image-spec/pull/1022
- manifest: provide guidance on SCRATCH descriptor (config and layer)
    - https://github.com/opencontainers/image-spec/pull/1023
    - https://github.com/opencontainers/image-spec/pull/1029

Discussion
- If 999 is to be accepted the following PRs should be merged prior and there should be a decision about if artifact manifest should be moved to a feature branch for continued work.
- Below is the list of PRs that are being considered prior to the merge of #999
    - https://github.com/opencontainers/image-spec/pull/1022
    - https://github.com/opencontainers/image-spec/pull/1023
        - Conversation - Drop the function, keep the const, clarify what scratch means, should we move forward with 1029
    - https://github.com/opencontainers/image-spec/pull/1030
- We should also add  issue #1025 table to a markdown and have it tagged. It's useful to have as a tool to have to understand the decision


- Not Covered
    - v1.1 milestone and possible timelines. (@sajay)

### Notes:

## February 23, 2023

**Recording**: https://youtu.be/YTzqnUr8z_A

### Attendees:
- Brandon Mitchell
- ToddySM
- Lachlan Evenson
- Victor Lu
- Mike Brown(IBM)
- Tianon Gravi
- John Kjell
- Michael Brown (AWS)
- Jon Johnson
- Aaron Friel
- albi
- Sajay Antony
- Phil Estes
- Nisha Kumar
- Jamie Wu
- Ramkumar Chinchani
- Jesse Butler
- cpuguy83 (Brian Goff)
- Amye
- _add yourself_

### Note Taker:
- _add note taker_

### Actionable Agenda Items:
- Who's taking notes?
- _add your items_

### Presentation/Discussion Agenda Items:
- Decide on a minimal image manifest: <https://github.com/opencontainers/image-spec/issues/1025>
- Clarify ignore:
  - <https://github.com/opencontainers/image-spec/pull/1028>
  - <https://github.com/opencontainers/image-spec/pull/902>
  - <https://github.com/opencontainers/image-spec/pull/1023>
- What could a new artifact manifest look like?
- _add your items_

### Notes:

## February 16, 2023

**Recording**: https://youtu.be/HOYIbfmGXLU

### Attendees:
- vbatts
- Aaron Friel
- Jason
- John Kjell
- Brandon Mitchell
- Josh Dolitsky
- Mike Majors
- Sajay Antony
- Brian Goff
- Tianon Gravi
- Mike Majors
- Ramkumar Chinchani
- Lachlan Evenson
- Jesse Butler
- Josh Dolitsky
- Jamie Wu
- _add yourself_

### Note Taker:
- _add note taker_

### Actionable Agenda Items:
- Who's taking notes?
- _add your items_

### Presentation/Discussion Agenda Items:
- [manifest: clarify that layers is technically OPTIONAL](https://github.com/opencontainers/image-spec/pull/1016)  @vbatts
- [manifest: provide guidance on SCRATCH config descriptor](https://github.com/opencontainers/image-spec/pull/1023) @vbatts
- https://github.com/opencontainers/image-spec/issues/1025
- Open to changing "ignored" language? @friel https://github.com/opencontainers/image-spec/pull/1028
  - https://github.com/opencontainers/image-spec/pull/902
- OK to merge https://github.com/opencontainers/distribution-spec/pull/383 ? (Josh)
- _add your items_

### Notes:

## February 9, 2023

**Recording**: https://youtu.be/WMcd0anCJVQ

### Attendees:
- vbatts
- Brandon Mitchell
- Sajay Antony
- Jason Hall
- Aaron Friel
- Josh Dolitsky
- Jesse Butler
- Tianon Gravi
- Jamie Wu
- John Kjell
- Derek McGowan
- Victor Lu
- Mike Brown, IBM
- Amye Scavarda Perrin
- Ramkumar Chinchani
- Michael Brown
- Toddy
- _add yourself_

### Note Taker:
- _add note taker_

### Actionable Agenda Items:
- `OCI-Subject-Processed` response header: https://github.com/opencontainers/distribution-spec/pull/379
- `OCI-Filters-Applied` response header: https://github.com/opencontainers/distribution-spec/pull/380
- https://github.com/opencontainers/distribution-spec/issues/378
- https://github.com/opencontainers/image-spec/pull/999
- https://github.com/opencontainers/image-spec/pull/1004

### Presentation/Discussion Agenda Items:
- _add your items_

### Notes:




## February 2, 2023

Cancelled

## February 1, 2023

**Recording**:

On-site hybrid event at CNSecurityCon:
<https://hackmd.io/moB5-fsQTbGmDpnrsY-4yg>

## January 26, 2023

**Recording**: https://youtu.be/w39590Jn5zg

### Attendees
- Ramkumar Chinchani
- Brandon Mitchell
- Sajay Antony
- Michael Brown
- Tianon
- Chris Crone
- Dave O'Connor
- Syed Ahmed


### Note Taker

### Actionable Agenda Items:
- **Jason:** deprecating non distributable layers?
  - <https://github.com/opencontainers/image-spec/pull/965>
- **Jon:** upon pushing a manifest with `subject`, the registry should respond with a header that says "I parsed and processed this subject, and updated referrers"; this is a clear positive signal that the registry supports the referrers API.
- **Jon:** https://github.com/opencontainers/image-spec/pull/999 - dropping Artifact Manifest from v1.1
- Agenda items for next week's meeting go here: (Feb 1, 2pm to 5pm in person and virtual)
    - https://hackmd.io/moB5-fsQTbGmDpnrsY-4yg

## January 19, 2023

**Recording**: https://youtu.be/E6RdnQxU5ZM

### Attendees:
- Brandon Mitchell
- Jon Johnson
- Vincent Batts
- Jesse Butler
- Tianon
- Severin Neumann
- Toddy Mladenov
- Jason Hall
- Brian Goff
- Sajay Antony
- Ramkumar Chinchani
- Aaron Friel
- Jamie Wu
- Mike Brown
- Amye Scavarda Perrin
-

### Note Taker:
- _add note taker_

### Actionable Agenda Items:
- Who's taking notes?
- _add your items_

### Presentation/Discussion Agenda Items:
- [1] Question: is it possible/feasible to make something like suggested in the issue below possible (obtain container/image id from within the container)?
    - https://github.com/opencontainers/runtime-spec/issues/1105
    - Main use case: correlate monitoring data from inside the container (application) with the outside (infrastructure)

- [2] Continued discussion, adding capabilities endpoint and client use case guidance
    - https://github.com/opencontainers/distribution-spec/issues/365
    - should this become two issues?
- [3] New Open Standards Survey: https://www.research.net/r/FG78BXB
- [4] [Specify accepted manifest types #373](https://github.com/opencontainers/distribution-spec/pull/373) @sajay
### Notes:

## January 12, 2023

**Recording**: https://youtu.be/SjF5PURhmw8

### Attendees:
- Brandon Mitchell
- Brandon Caton
- Dave O'Connor
- nisha
- Jon Johnson
- Jamie Wu
- cpuguy83
- Syed Ahmed
- Josh Dolitsky
- Victor Lu
- Michael Brown
- Jesse Butler
- Ramkumar Chinchani
- Brandon Klein
- Sajay Antony
- Tianon
- _add yourself_

### Note Taker:
- _add note taker_

### Actionable Agenda Items:
- Who's taking notes?
- _add your items_

### Presentation/Discussion Agenda Items:
- Check-in on 1.1 release
    - <https://github.com/opencontainers/image-spec/milestone/14>
    - <https://github.com/opencontainers/distribution-spec/milestone/6>
- Discuss adding version endpoint, client requirements
    - https://github.com/opencontainers/distribution-spec/issues/365
- ..

### Notes:

## January 5, 2023

**Recording**: https://youtu.be/RlWvaGxg_jg

### Attendees:
- Brandon Mitchell
- Phil Estes
- Ramkumar Chinchani
- Michael Brown
- Brandon Klein
- Tianon
- _add yourself_

### Note Taker:
- _add note taker_

### Actionable Agenda Items:
- _add your items_

### Presentation/Discussion Agenda Items:
- How are people feeling about 1.1 release at end of month? (Josh)
  - Milestone tracking:
    - <https://github.com/opencontainers/image-spec/milestone/14>
    - <https://github.com/opencontainers/distribution-spec/milestone/6>
- Discussion on the registry ability to not include annotations in referrers response
  - <https://github.com/opencontainers/distribution-spec/pull/367>
  - Recommend to refuse the manifest push rather than alter the referrers response per descriptor or filter out responses
  - Limit descriptor size to 40kb for a manifest with a subject
    - 40kb * 100 responses per page = 4mb limit on index
    - registries can then implement pagination with a fixed 100 entries per page rather than checking each additional descriptor for the limit
    - some clients already limit individual annotations to 4kb
    - allows arbitrary annotations for future use cases, but with a bounded max size
  - Registries MAY reject a manifest push that exceeds these limits
- _add your items_

## December 28, 2022

Canceled

## December 22, 2022

Canceled

## December 15, 2022

**Recording**: https://youtu.be/uuBb-2NTYIw

### Attendees:
- Brandon Mitchell
- Tianon
- Jesse Butler
- Michael Brown
- Sajay Antony
- Mike Brown
- Jason Hall
- Jon Johnson
- Toddy Mladenov
- Samuel Karp
-
- _add yourself_

### Note Taker:
- _add note taker_

### Actionable Agenda Items:
- Who's taking notes?
- _add your items_

### Presentation/Discussion Agenda Items:
- _add your items_
- WG Proposal for Authn/Authz: <https://github.com/opencontainers/tob/pull/119>
- Timeline for tagging 1.1 distribution/image-spec
  - Still want to see some implementations
  - Milestone tracking:
    - <https://github.com/opencontainers/image-spec/milestone/14>
    - <https://github.com/opencontainers/distribution-spec/milestone/6>
- Determining if registry supports the new manifest and referrers?
    - https://github.com/opencontainers/distribution-spec/issues/365 [@sajay]
- Meeting schedule for rest of the year
    - Calendars have been cleared until Jan - ASP
-

### Notes:

## December 8, 2022

**Recording**: https://youtu.be/PzWqxhqNrLQ

### Attendees:
- Brandon Mitchell
- Sajay Antony
- Jesse Butler
- Ramkumar Chinchani (Cisco/zot)
- Michael Brown
- Tianon
- Samuel Karp
-
- _add yourself_

### Note Taker:
- https://github.com/opencontainers/distribution-spec/issues/365
- _add note taker_

### Actionable Agenda Items:
- Who's taking notes?
- _add your items_

### Presentation/Discussion Agenda Items:
- _add your items_
- determining whether a registry supports reference types: https://github.com/opencontainers/distribution-spec/issues/365
  - There is a desire for client tooling to fail fast, before the blob push, when the future manifest push will fail

### Notes:


## December 1, 2022

**Recording**: https://youtu.be/PnuKGurvEn4

### Attendees:
- _add yourself_
- Brandon Mitchell
- Sajay Antony
- Tianon
- Brian Goff
- Jamie (AWS ECR)
- Jon Johnson
- Ramkumar Chinchani
- ToddySM

### Note Taker:
- _add note taker_

### Actionable Agenda Items:
- Who's taking notes?
- [Distribution PR #366](https://github.com/opencontainers/distribution-spec/pull/366) (Brandon)
- https://opencontainers.slack.com/archives/C0LQVA03W/p1669781318238629
- _add your items_

### Presentation/Discussion Agenda Items:
- _add your items_

### Notes:
- Discussing `artifactType` and blob `mediaType`
  - Some discussion happened at [KubeCon](https://hackmd.io/nZzK_4AfRz-xgya6KkqseA#Standardizing-artifact-media-types-and-annotations---allowing-interoperability-among-clients-Nisha-KumarBrandon-Mitchell)
  - Notary / COSE discussion: <https://github.com/notaryproject/notaryproject/issues/207>
- Must be ignored?
  - https://github.com/opencontainers/image-spec/blob/main/image-index.md?plain=1#L46
  - https://github.com/opencontainers/image-spec/pull/902
- Can clients detect when the new artifact manifest is not supported by a registry
  - Related discussion: https://fosstodon.org/@bmitch/109417666339330970
  - Push to not fallback or automatically upgrade because of portability concerns (Brandon)
  - No good answer to interpret different errors, Brandon is just giving the error back to the user as-is.

## November 24, 2022 is cancelled

## November 17, 2022

**Recording**: https://youtu.be/LL18erQULwc

### Attendees

- John Ericsson (Nix Community / Obsidian Systems)
- David Arnold (Nix Community / IOHK)
- Brandon Mitchell
- Ramkumar Chinchani (zot/Cisco)
- Brandon Klein (SNL)

### Note Taker:
- _add note taker_

### Actionable Agenda Items:
- Who's taking notes?
- _add your items_

### Presentation/Discussion Agenda Items:
- Ways to bring the Nix ecosystem closer to OCI
    - Maybe a new "non-conflicting" layer type?
    - Could work for other, too: eg. _Guix_

### Notes:

- Nix/Guix "layers"
  - Non-conflicting (disjoint mount points)
  - Immutable
  - Need to support numerous tiny images, no artificial limits.

  - Nix/Guix ideomatic usage
    - No "base image"
      - Turtles all the way down!

  - Read-only paths can be done with https://github.com/opencontainers/runtime-spec/blob/main/config-linux.md#readonly-paths

  - Jon Johnson: Seems like two things to consider:

    1. How to represent these images (image-spec)
    2. How to unpack these differently from overlay (runtime-spec)

  - Tianon Gravi: runtime-spec doesn't specify unpacking though, that's runtime-specific (runtime-spec just specifies "rootfs" and it's implementation defined how to create that from an image) O:)


  - Nisha Kumar: The problem with regarding to running a /store like rootfs is putting the right binary in the right place such that the container runtime can find it


  - Brandon Mitchell: I'm wondering if the implementation could be as easy as an annotation that indicates the name of the non-conflicting path, which has the potential to be backwards compatible.
    - John Ericson: Sounds great!!


## November 10, 2022

**Recording**: https://youtu.be/HV_4mACIWrY

### Attendees:
- Brandon Mitchell
- Jason Hall
- Phil Estes
- Derek McGowan
- Mike Brown (IBM)
- Josh Dolitsky
- Jon Johnson
- Kevin Parsons
- Sajay Antony
- Christian Kniep
- Kazu
- Brian Goff
- Tianon
- Toddy
- Michael Brown (AWS)
- Ramkumar Chinchani (zot/Cisco)
- _add yourself_

### Note Taker:
- _add note taker_

### Actionable Agenda Items:
- Who's taking notes?
- [Jason] wasi/wasm change needs image-spec approvers 🙏: https://github.com/opencontainers/image-spec/pull/964
- [Jason] Dockerhub doesn't actually support "OCI Artifacts"
    - continued harmful confusion about these terms
    - We should clarify that "OCI Artifacts" is this: https://github.com/opencontainers/image-spec/blob/main/artifact.md
    - ...and not this: https://github.com/opencontainers/artifacts
    - Jason's AI from OCI Summit to migrate artifact author guidance to image-spec, then archive/delete `artifacts` repo.
    - Tianon: "subject" field issue with Docker Hub is fixed as of today! 😇
- [Jason] referrers API: "registries MAY hoist the manifest contents into the `data` of the descriptor
    - which means we can change "annotations MUST be hoisted" to "annotations MAY be hoisted"
    - clients should be prepared to fetch manifests if they want to filter on annotation data
    - Jon's issue: https://github.com/opencontainers/distribution-spec/issues/357

### Presentation/Discussion Agenda Items:
- _add your items_

### Notes:

## November 3, 2022

**Recording**: https://youtu.be/kjleG_01EqQ

### Attendees:
- Brandon Mitchell
- Josh Dolitsky
- Sajay Antony
- Mike Brown (IBM)
- Michael Brown (AWS)
- Jesse Butler
- Tianon
- ASP
- Bjorn Neergaard
- Cory Snider
- Brian Goff
- Nisha Kumar
- Ramkumar Chinchani (zot/Cisco)

### Note Taker:
- _add note taker_

### Actionable Agenda Items:
- Who's taking notes?
- Road to releasing 1.1. What's left? (Michael Brown)
    - Should we set a target release date and work towards that? (Josh)
### Presentation/Discussion Agenda Items:
- Implied directories: <https://github.com/opencontainers/image-spec/pull/970>
- Support for Diff Pulls?: <https://github.com/opencontainers/distribution-spec/issues/360>
- _add your items_

### Notes:
- Road to releasing 1.1. What’s left? (Michael Brown)
    - [Image Spec Milestone](https://github.com/opencontainers/image-spec/milestone/14)
    - [Distribution Spec Milestone](https://github.com/opencontainers/distribution-spec/milestone/6)
    - [Zot is adding support](https://github.com/project-zot/zot/pull/936)
    - can we set a timeline?
    - Josh: maybe Jan 17
    - Amye: seems too soon, what about a few weeks later?
        - https://events.linuxfoundation.org/cloudnativesecuritycon-north-america/ is a good one to track to, Feb 2-3
    - Docker Hub currently has a filter/block on the subject field

## October 27, 2022

**Recording**: https://youtu.be/IuTYxTUj-bA

### Attendees:
- Brandon Mitchell
- Jon Johnson
- Brandon Klein
- Jadjit Singh
- Tianon
- _add yourself_

### Note Taker:
- _add note taker_

### Actionable Agenda Items:
- Who's taking notes?
- _add your items_

### Presentation/Discussion Agenda Items:
- _add your items_
- Adding a header for pulls <https://github.com/opencontainers/distribution-spec/pull/358>
- Relaxing annotation requirement on referrers API response <https://github.com/opencontainers/distribution-spec/issues/357>
- CNCF/KubeCon meeting <https://hackmd.io/nZzK_4AfRz-xgya6KkqseA>

### Notes:
- (Jon and Brandon Mitchell had some productive chatting)

## October 24, 2022

KubeCon NA in Detroit!

**Recording**: https://youtu.be/8lPr9cbLSmA
**Event specific notes**: https://hackmd.io/nZzK_4AfRz-xgya6KkqseA

## October 20, 2022

**Recording**: https://youtu.be/O1aNjcC_0d8

### Attendees:
- Lachlan Evenson
- Amye Scavarda Perrin
- Brandon Mitchell
- Nisha Kumar
- Tianon Gravi
- Michael Brown
- Josh Dolitsky
- Phil Estes
- Jon Johson
- Sajay Antony

### Note Taker:
- _add note taker_

### Actionable Agenda Items:
- Who's taking notes?
- <https://github.com/opencontainers/image-spec/pull/957>
- _add your items_

### Presentation/Discussion Agenda Items:
- OCI summit Monday, October 24 (before KubeCon): https://hackmd.io/nZzK_4AfRz-xgya6KkqseA
- Propsal: Change artifactType from SHOULD to MUST (Lachlan) - https://github.com/opencontainers/image-spec/issues/968
- Improvements to artifactType definition and examples for clarity (Lachlan)
- _add your items_

### Notes:

## October 13, 2022

**Recording**: https://youtu.be/UbbbFroXIAQ

### Attendees:
- Brandon Mitchell
- Michael Brown
- Samuel Karp
- Nisha
- Sajay

### Note Taker:
- _add note taker_

### Actionable Agenda Items:
- Who's taking notes?
- Artifact Testing Reviews needed <https://github.com/opencontainers/image-spec/pull/942>
- _add your items_

### Presentation/Discussion Agenda Items:
- _add your items_
- OCI summit Monday, October 24 (before KubeCon): https://hackmd.io/nZzK_4AfRz-xgya6KkqseA
- Deprecating foreign layers [Jason]
    - The only use of them in the wild is [moving away from them](https://techcommunity.microsoft.com/t5/containers/announcing-windows-container-base-image-redistribution-rights/ba-p/3645201)
    - [Justin says](https://twitter.com/justincormack/status/1580536342114492417) they can be deprecated
    - Can we add language [here](https://github.com/opencontainers/image-spec/blob/main/layer.md#non-distributable-layers) along the lines of, "This layer type is considered deprecated, and not recommended for future use. Clients should still consider them when moving images (for backward compatibility) but in general SHOULD NOT produce new layers with that type."
- Wasm considerations for image-spec [Jason]
  - Wasm is using OCI images to package and distribute (that's good!)
    - ...but currently only building single-platform images, and lying about their OS+arch being `linux/amd64` (that's bad!)
  - want to do better, but image-spec guidance is lacking
    - `.platform.os` field is `REQUIRED` but not meaningful to Wasm
  - guidance is to use values of Go's `GOOS` and `GOARCH`
    - As specified, this would mean `os=js`, `arch=wasm`
    - Go's Wasm support is lagging far behind Rust and TypeScript.
    - aside: `GOARCH=wasm` is 32-bit -- `wasm64` may come later
    - aside: `amd64` variants [#852](https://github.com/opencontainers/image-spec/issues/852)
  - Wasm may have variants (`spin` and `slight` today) -- should they register them with OCI?
  - They seem okay with `os=wasi`, `arch=wasm`, `variant=spin` (etc)
  - **Specific asks:**
    - specifying an exception to the `GOOS` rule for `wasi`?
    - specifying known variants for when `arch=wasm`, but you can also BYO?
  - Questions from Jon:
    - what's the layer media type? (A: `application/vnd.docker.image.rootfs.diff.tar.gzip`)
    - do they set the entrypoint? (A: No, not today, but we could recommend/require it)
- Resuming interrupted PATCH request (Brandon)
    - API to get status of an upload is not defined
    - Procedure to get the current "Location" and "Range" is not defined by OCI
    - Docker API has a `GET /v2/<repo>/blobs/uploads/<uuid>` ([ref](https://github.com/distribution/distribution/blob/5cb406d511b7b9163bff9b6439072e4892e5ae3b/docs/spec/api.md#upload-progress))
    - Related: <https://github.com/opencontainers/distribution-spec/issues/352>
- New Netlify image is needed <https://github.com/opencontainers/opencontainers.org/issues/120> (Brandon)
- Embedding Platform in Config <https://github.com/opencontainers/image-spec/pull/949> (Brandon)

### Notes:

## October 6, 2022

**Recording**: https://youtu.be/8X8vxWohmqA

### Attendees:
- Brandon Mitchell
- _add yourself_

### Note Taker:
- _add note taker_

### Actionable Agenda Items:
- Who's taking notes?
- _add your items_

### Presentation/Discussion Agenda Items:
- _add your items_
- https://hackmd.io/nZzK_4AfRz-xgya6KkqseA

### Notes:

## September 29, 2022

**Recording**: https://youtu.be/DyUfew4gF3c

### Attendees:
- Brandon Mitchell
- ASP
- Sajay Antony
- Mike Brown (IBM)
- _add yourself_

### Note Taker:
- _add note taker_

### Actionable Agenda Items:
- Who's taking notes?
- _add your items_

### Presentation/Discussion Agenda Items:
- _add your items_
- OCI Meeting at KubeCon + virtual; October 24th from 10am to 12pm Central
- RC2 is looking for votes: <https://github.com/opencontainers/image-spec/pull/958>

### Notes:

## September 22, 2022

**Recording**: https://youtu.be/F9gmGcKq9rM

### Attendees:
- Lachlan Evenson
- Mike Brown (IBM)
- Brandon
- Sajay
- Tianon
- Brian Goff
- VBatts
- Nisha
- Ramkumar Chinchani

### Note Taker:
- _add note taker_

### Actionable Agenda Items:
- Who's taking notes?
- _add your items_

### Presentation/Discussion Agenda Items:
- Continue discussion on RC1 release [Brandon/Josh/Sajay]
    - Distribution spec - https://github.com/opencontainers/distribution-spec/pull/348
    - Image Spec - https://github.com/opencontainers/image-spec/pull/953
- Reviewing 1.0.3 tagging option: <https://github.com/opencontainers/image-spec/issues/918>
- _add your items_

### Notes:

## September 15, 2022

**Recording**: https://youtu.be/jqtaJn6s6uo

### Attendees:
- Samuel Karp
- Sajay Antony
- Brandon Mitchell
- Josh Dolitsky
- Michael Brown (IBM)
- Michael Brown (AWS)
- Brian Goff
- Brandon Klein
- _add yourself_

### Note Taker:
- _add note taker_

### Actionable Agenda Items:
- Who's taking notes?
- _add your items_

### Presentation/Discussion Agenda Items:
- [Rename refers field to subject](https://github.com/opencontainers/image-spec/pull/950)
  - [Distribution Spec](https://github.com/opencontainers/distribution-spec/pull/344)
  - Need approval from maintainers @sajay
- Discuss about process for release of spec to enable downstream consumers of the new specification @lachie83 (out on jury duty)
  - https://github.com/opencontainers/image-spec/issues/952
  - https://github.com/opencontainers/distribution-spec/issues/337
- Remaining items:
  - <https://github.com/opencontainers/image-spec/issues/940>
  - <https://github.com/opencontainers/distribution-spec/issues/337>
- Cutting an RC:
    1. Open a PR titled `v1.0.0-rc0`
    2. TODO (contents of PR)
    3. Email to `dev@opencontainers.org.`
    4. Subject `[image-spec VOTE] tag <shorthash> as v1.1.0-rc0 (closes Mon 19 Apr 2021 10:00:00 PM UTC)` (date is 7 days from now)
    5. Body:
    ```

    ```
- _add your items_

### Notes:

## September 8, 2022

**Recording**: https://youtu.be/9k2QbsrbkY0

### Attendees:
- Samuel Karp
- _add yourself_

### Note Taker:
- _add note taker_

### Actionable Agenda Items:
- Who's taking notes?
- _add your items_

### Presentation/Discussion Agenda Items:
- <https://github.com/opencontainers/image-spec/issues/940>
- <https://github.com/opencontainers/opencontainers.org/pull/118>
- _add your items_

### Notes:


## September 1, 2022

**Recording**: https://youtu.be/t28jnJgPOqI

### Attendees:
- Brandon Mitchell
- Michael Brown
- Josh Dolitsky
- Nisha Kumar
- Sam Karp
- Brandon Thorin Klein
- _add yourself_

### Note Taker:
- _add note taker_

### Actionable Agenda Items:
- Who's taking notes?
- _add your items_

### Presentation/Discussion Agenda Items:
- <https://github.com/opencontainers/image-spec/issues/940>
- <https://github.com/opencontainers/distribution-spec/issues/337>
- _add your items_

### Notes:
- [Michael] turn [this issue](https://github.com/opencontainers/distribution-spec/issues/340) into a vote.
- Nisha is adding alternatives to refers/referrers to <https://github.com/opencontainers/image-spec/issues/940>

## August 25, 2022

**Recording**: https://youtu.be/yycxvdu8HpM

### Attendees:
- Phil Estes
- Lachlan Evenson
- Brandon Mitchell
- Mike Brown
- Vincent Batts
- Sajay Antony
- Jesse Butler
- Tianon Gravi
- Ramkumar Chinchani
- Kyle Smith
### Note Taker:
- _add note taker_

### Actionable Agenda Items:
- Who's taking notes?
- _add your items_

### Presentation/Discussion Agenda Items:
- Working Group Proposal Merge (Brandon):
  - [image-spec](https://github.com/opencontainers/image-spec/pull/934)
  - [distribution-spec](https://github.com/opencontainers/distribution-spec/pull/335)
- Issue and PR review (Brandon)
- _add your items_

### Notes:
- Future TODO items:
  - Update image-spec spec.md definitions to match distribution-spec
  - "Refers": add "field" or "to"?
  - "Referrers": add "list"?
  - Change Object to *object*
  - Change "registry SHOULD accept a manifest with a `refers`" to "MUST"
    - include details of why, how to GC
  - Change `<reference>` to `<digest>` and define `<digest>`
    - "tags may be added in the future"
  - Add "note" to "Multiple clients could attempt to update the tag simultaneously resulting in race conditions and data loss."

## August 18, 2022

**Recording**: https://youtu.be/d7WHS5fPl3k

### Attendees:
- _add yourself_

### Note Taker:
- _add note taker_

### Actionable Agenda Items:
- Who's taking notes?
- Working Group Proposal Updates (Brandon):
  - [image-spec](https://github.com/opencontainers/image-spec/pull/934)
  - [distribution-spec](https://github.com/opencontainers/distribution-spec/pull/335)
- Possibility of project meeting at KubeCon? (ASP)
    - Need to check on availability for hybrid
- [Naming discussion](https://github.com/opencontainers/wg-reference-types/issues/41)
- _add your items_

### Presentation/Discussion Agenda Items:
- _add your items_

### Notes:

## August 11, 2022

**Recording**: https://youtu.be/Hfy8umF8p20

### Attendees:
- Brandon Mitchell
- Sajay Antony
- Josh Dolitsky
- Jimmy Zelinskie
- Vincent Batts
- Lachlan Evenson
- Michael Brown (AWS)
- Nisha
- Samuel Karp
- Brian Goff
- Trianon Gravi
- Ramkumar Chinchani
- _add yourself_

### Note Taker:
- _add note taker_

### Actionable Agenda Items:
- Who's taking notes?
- Working Group Proposal (Brandon, Josh, Sajay, Nisha, and many others):
  - [image-spec](https://github.com/opencontainers/image-spec/pull/934)
  - [distribution-spec](https://github.com/opencontainers/distribution-spec/pull/335)
- _add your items_

### Presentation/Discussion Agenda Items:
- _add your items_

### Notes:


- next-steps on the referers API WG:
  - Get this Zoom recording, and share for review
  - https://github.com/opencontainers/image-spec/pull/934
  - https://github.com/opencontainers/distribution-spec/pull/335
  - Allow for 2wks - 1mo for review before merge
  -

## August 4, 2022

No agenda, canceled

## July 28, 2022

No agenda, just a short informal discussion on GC policies and the working group.

## July 21, 2022

No agenda, canceled

## July 14, 2022

No agenda, canceled

## July 7, 2022

### Attendees:
- _add yourself_
- Brandon Mitchell
- Ramkumar Chinchani (Cisco/zot)
- Sajay Antony
- Mike Brown (IBM)

### Note Taker:
- _add note taker_

### Actionable Agenda Items:
- Who's taking notes?
- _add your items_

### Presentation/Discussion Agenda Items:
- _add your items_
- How should new specs be delivered from a WG to OCI?
- [Draft: WG for Reference Spec](https://github.com/opencontainers/tob/pull/114)
- https://github.com/opencontainers/artifacts/pull/56
- image-spec needs some pruning:
  - https://github.com/opencontainers/image-spec/pull/927
  - https://github.com/opencontainers/image-spec/pull/926

### Notes:

## June 30, 2022

### Attendees:
- Brandon Mitchell
- Phil Estes
- Ramkumar Chinchani (Cisco)
- Tianon
- _add yourself_

### Note Taker:
- _add note taker_

### Actionable Agenda Items:
- Who's taking notes?
- _add your items_

### Presentation/Discussion Agenda Items:
- Options for immutable tags [distribution-spec PR #320](https://github.com/opencontainers/distribution-spec/pull/320) (Brandon)
- Creation of a working group to standardize the reference syntax. (Brandon)
  - [PR Opened](https://github.com/opencontainers/tob/pull/114)
- Cross-registry blob mounting ([distribution-spec#323](https://github.com/opencontainers/distribution-spec/issues/323)) interest? (Jon)
- _add your items_

### Notes:

## June 23, 2022

### Attendees:
- Tianon
- Jason
- Flavian
- _add yourself_

### Note Taker:
- _add note taker_

### Actionable Agenda Items:
- Who's taking notes?
- Nisha: are registries required to verify digests on push?
    - Tianon: image-spec says SHOULD, no conformance test though
    - https://github.com/opencontainers/image-spec/blob/v1.0.1/descriptor.md#verification
    - Nisha: zot seems to not verify
    - Jason: zot is listed as conformant
    - https://github.com/opencontainers/oci-conformance/tree/main/distribution-spec/v1.0/zot
- [Jason] OCI recommending a header for manifest/blob pulls to denote the image ref that request is being made for
  - help registry operators attribute pulls to images --> better rate limits
  - build this into clients
  - go-containerregistry prototype [here](https://github.com/google/go-containerregistry/pull/1369)
  - Flavian: potentially also a useful signal for GC -- e.g., don't GC something that was implicated in a pull in the last N days
  - Quay does something similar, where blobs are associated with a repo instead of a manifest until a subsequent manifest push references the blob; blobs only referenced by repos and not by manifests are GCed after ~1h.

### Presentation/Discussion Agenda Items:
- _add your items_

### Notes:

## June 16, 2022

### Attendees:
- _add yourself_

### Note Taker:
- _add note taker_

### Actionable Agenda Items:
- Who's taking notes?
- _add your items_

### Presentation/Discussion Agenda Items:
- _add your items_

### Notes:

## Jun 9, 2022

### Attendees
- David Arnold
- Zack Newman
- Flavian Missi
- Tianon
- Brandon Mitchell
- Josh Dolitsky
- Sajay Antony
- _add yourself_

### Note Taker:
- Brandon

### Actionable Agenda Items:
- _add your items_

### Presentation/Discussion Agenda Items:
- OCI Image support for Nix Store Paths:
    - https://github.com/opencontainers/image-spec/issues/922

### Notes:

- Looking to store Nix data in OCI blobs
- Can't use layers because of overlay limits on number of layers
- Would use their own distribution-spec implementation
- Need some kind runtime to assemble filesystem without overlay for Nix components
- Nix currently has a cache, sometimes forced to rebuild on a cache miss, would like a registry to keep the store
- When glibc updates, all child objects in the store need to be recreated

## Jun 2, 2022

### Attendees
- Brandon Mitchell
- Tianon
- Nisha
- Josh Dolitsky
- Mike Brown
- _add yourself_

### Note Taker:
- Nisha/Brandon

### Actionable Agenda Items:
- Who's taking notes?
- PR https://github.com/opencontainers/image-spec/pull/919
    - How do we bother the image spec maintainers
    - Brandon did a ping all maintainers on github
    - Josh will reach out to Steveeo(?)
- [Proposal F](https://github.com/opencontainers/wg-reference-types/issues/50)
    - Still waiting for PR to review
- _add your items_

### Presentation/Discussion Agenda Items:
- _add your items_

### Notes:

## May 26, 2022

### Attendees
- Brandon Mitchell
- Tianon
- Brandon K
- Nisha
- _add yourself_

### Note Taker:
- _add note taker_

### Actionable Agenda Items:
- Who's taking notes?
- PR https://github.com/opencontainers/image-spec/pull/919
- _add your items_

### Presentation/Discussion Agenda Items:
- _add your items_

### Notes:

## May 12, 2022

### Attendees:
- Phil Estes (AWS)
- Sajay Antony
- Tianon
- Flavian Missi
- Silvin Lubecki
- _add yourself_

### Note Taker:
-

### Actionable Agenda Items:
- ~~Punted from last week: [image-spec maintainers](https://github.com/opencontainers/image-spec/pull/910) (Josh)~~
    - Merged 🎉
- [Minimum criteria for new maintainers](https://github.com/opencontainers/image-spec/issues/912) (Josh)
    - 2 PRs already open to add [Sajay](https://github.com/opencontainers/image-spec/pull/911) and [Brandon](https://github.com/opencontainers/image-spec/pull/909)
    - The issue of timezones

### Presentation/Discussion Agenda Items:
-

### Notes:
- New maintainers: a new PR template will be added so that existing maintainers can nominate new maintainers (Nisha volunteered to submit PR)
-

## May 5, 2022

### Attendees:
- Sajay Antony
- Brandon Mitchell
- Flavian Missi
- _add yourself_

### Note Taker:
-

### Actionable Agenda Items:
- [image-spec maintainers](https://github.com/opencontainers/image-spec/pull/910) (Josh)
- [distribution-spec registry vs repository](https://github.com/opencontainers/distribution-spec/pull/325) (Brandon)

### Presentation/Discussion Agenda Items:
- How should changes to distribution-spec be proposed? https://github.com/opencontainers/distribution-spec/issues/324 (Brandon)

### Notes:
-


## April 28, 2022

### Attendees:
- Sajay
- Brandon M
- Brandon K
- Ram
- Tianon
- Josh
- MII
- Kyle S

### Note Taker:
-

### Actionable Agenda Items:
-

### Presentation/Discussion Agenda Items:
- https://github.com/opencontainers/image-spec/issues/907

### Notes:
-


## April 21, 2022

### Attendees:
- Vincent Batts
- Brandon Mitchell
- Samuel Karp
- Mike Brown (IBM)
- Brandon Klein
- Kyle Smith (Full Sail)

### Note Taker:
- _add note taker_

### Actionable Agenda Items:
- _add your items_

### Presentation/Discussion Agenda Items:
- _add your items_

### Notes:
- Areas for future standards
  - Authentication
  - Defining the reference and how "alpine" goes to Hub
  - Allowing redirects in distribution-spec response codes
- What is needed for [Proposal E](https://github.com/opencontainers/wg-reference-types/pull/38) to get merged in spec changes
- [[RFC] move descriptor (and layout?) to distribution-spec](https://github.com/opencontainers/image-spec/issues/907)
- Issue with slack join link is being worked on


## April 14, 2022

### Attendees:
- Brandon Mitchell
- Phil Estes
- Vincent Batts
- Tianon
- Amye
- Brandon Klein
- Brian Goff
- Josh Dolitsky
- Steve Lasker
- Sajay
- Ramkumar Chinchani
- Mike Brown(IBM)
- Kyle Smith

### Note Taker:
- _add note taker_

### Actionable Agenda Items:
- _add your items_

### Presentation/Discussion Agenda Items:
- [Immutable tags](https://github.com/opencontainers/distribution-spec/pull/320) (Brandon)
- Working Group Update: [Proposal E](https://github.com/opencontainers/wg-reference-types/pull/38) (Brandon)
- _add your items_


### Notes:
