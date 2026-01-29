# OCI Weekly Dev Meeting Notes Archive - 2022

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

## March 31, 2022

### Attendees:
- Brandon Mitchell
- Tianon
- vbatts
- Samuel Karp
- giinglis
- Syed Ahmed
- Brandon Klein
- Brian Goff
- Sajay Antony
- Ramkumar Chinchani

### Note Taker:
- _add note taker_

### Actionable Agenda Items:
- Recordings for Ref Type Working Group (Brandon)
- _add your items_

### Presentation/Discussion Agenda Items:
- [Extensibility clarification](https://github.com/opencontainers/image-spec/pull/902) (Brandon)
    - Should distribution-spec also be updated to define http status codes by registries that filter/validate manifests?
- [Annotations for end-of-life/support](https://github.com/opencontainers/image-spec/pull/903) (Brandon)
    - Recommendation to use reference types WG to append/dynamically EOL to existing images instead of picking a fixed time up front.
- _add your items_

### Notes:

## March 24, 2022

### Attendees:
- vbatts
- Brandon Mitchell
- Josh
- Sajay Antony
- Tianon

### Note Taker:
- _add note taker_

### Actionable Agenda Items:
- _add your items_

### Presentation/Discussion Agenda Items:
- KubeCon EU attendees?
- grooming?

### Notes:


## March 17, 2022

### Attendees:
- Phil Estes (AWS)
- Tianon
- Brandon Mitchell
- Samuel Karp
- Steve Lasker
- Mike Brown (IBM)
- Vincent Batts

### Note Taker:
- _add note taker_

### Actionable Agenda Items:
- _add your items_

### Presentation/Discussion Agenda Items:
- How should/can GC handle potential loops with reference types (Brandon)
    - https://groups.google.com/a/opencontainers.org/g/dev/c/mIv5XjKlBX0/m/RTH9IB1bDQAJ
- _add your items_

### Notes:

## March 10, 2022




### Attendees:
- vbatts
- Brandon Mitchell
- Tianon
- derek mcgowan
- brandon klein
- sajay antony
- mike brown
- ramkumar (ram) chinchani

### Note Taker:
- vbatts

### Actionable Agenda Items:
- _add your items_

### Presentation/Discussion Agenda Items:


### Notes:
- CNCF supply chain wg https://docs.google.com/document/d/1MTM782nluFl4_ybG-fXHmRT2k4bPN18ifdzpUltQQCw/edit#heading=h.1tv8gumsrtbf
- updates of our references WG from Brandon
- good to ensure CNCF Supply TAG and our references WG stay in the loop together
- OCI image layout
    -  wishing to see layout used in various CI pipelines, etc
    -  tagging vs digests, and how to best handle multi-arch
    -  work done in https://github.com/regclient/regclient
- sore spot: spec'ing out auth
    - https://github.com/opencontainers/distribution-spec/issues/110 ?
    - https://github.com/opencontainers/distribution-spec/issues/240
    - pains on edge cases of users that can push to multiple repos
    - there is no way to have say a load-balancer that routes GET to a read-only, and say PUT/POST/PATCH/DELETE to even a simple htpasswd backend, due to early token auth on the first GET
    - the problem of auth/and container image lifecyle needs more focus.. how do we ensure these images for specific users with specific access (push/pull mirror/local cache to gc of the mirrors/local caches (and killing of running containers)) "now expanding to phase II for adding security/cache policies of container images at the pod spec level and possible moving kubelet image manager/image gc manager code to the container runtime stack"
    - https://github.com/kubernetes/enhancements/issues/2535
    - https://github.com/kubernetes/kubernetes/pull/94899
    - (vb) this important enough that it needs to be coded into spec. Currently by not being specified, services and tools are primarily focused on not breaking their customers and tools. By coding it and where there is gray-space or rough edges, then implementations can more confidently unify and know they aren't breaking their customers, but also are reaching a broader set up tools and use-cases.
- 


---

## March 3, 2022

### Attendees:
- Jon Johnson
- Brandon Mitchell
- Ramkumar Chinchani (Cisco)
- Josh Dolitsky
- Vincent
- Sajay Antony
- Nisha
- _add yourself_

### Note Taker:
- _add note taker_

### Actionable Agenda Items:
- _add your items_

### Presentation/Discussion Agenda Items:
- `data` field (Jon)
    - https://github.com/opencontainers/image-spec/pull/826
    - (Would love to hear from ECR folks.)
- Charter Link is 404'ing: <https://github.com/opencontainers/image-spec/pull/898> (Brandon)

### Notes:

---

## February 24, 2022

**recording**: https://youtu.be/BP2jjOSj6JI

### Attendees:
- Brandon Mitchell
- Samuel Karp
- Vincent Batts
- Phil Estes
- Jon Johnson
- Josh Dolitsky
- Brandon T Klein
- Ramkumar Chinchani
- Sajay Antony

### Note Taker:
- Phil

### Actionable Agenda Items:
- _add your items_

### Presentation/Discussion Agenda Items:
- image-spec PRs (Brandon)
    - Data field: https://github.com/opencontainers/image-spec/pull/826
    - https://github.com/opencontainers/image-spec/pull/865
    - https://github.com/opencontainers/image-spec/pull/885
    - https://github.com/opencontainers/image-spec/pull/892
      - Related: https://github.com/containerd/containerd/pull/6479
    - https://github.com/opencontainers/artifacts/pull/53

### Notes:
- Reviewing open image-spec PRs: https://github.com/opencontainers/image-spec/pulls
- Side chat (in the actual Zoom chat) about continued slow progress and potential we still have fully inactive maintainers
  - Sam commented about a potential proposal to charter to handle this situation.
  - Josh: since this call isn't required for any kind of maintainer quorum should it just be presentations/demos? Maintainers would have to organize their own triage sync-ups

---

## February 17, 2022

**Recording**: https://youtu.be/SRdPdwwOahk

### Attendees:
- Samuel Karp
- Sajay Antony
- Brandon T Klein
- Steve Lasker (Microsoft)

### Note Taker:
- _add note taker_

### Actionable Agenda Items:
- _add your items_

### Presentation/Discussion Agenda Items:
- Distribution spec milestone review

### Notes:

---

## February 10, 2022

**Recording**: https://youtu.be/VKjFEJY_Hfw

### Attendees:
- Nisha Kumar
- Lachlan Evenson
- Phil Estes
- Ramkumar Chinchani (Cisco)
- Samuel Karp
- Brandon Mitchell
- Jason Hall (Red Hat)
- Josh Dolitsky
- Tiano
- ASP
- vbatts
- Sajay Antony
- Syed Ahmed
- _add yourself_

### Note Taker:
- Lachlan Evenson
- Jason 🥈 🍭

### Actionable Agenda Items:
- _add your items_

### Presentation/Discussion Agenda Items:
- Governance Discussion: (Nisha)
    - https://github.com/opencontainers/tob/issues/110 (Nisha)
        - How does the community reach out ot the TOB?
        - Seems to been 3 modes of comms - meeting, GH issues, email
        - Is there a priority?
        - Feel like we need a consolidated point where discussions on a topic happen
        - For things that require action, they should go through the mailing list (Josh)
        - From the charter - c. The TOB shall operate transparently with any discussions and mailing lists open to the community. (Samuel)
        - The language in the charter seems to enshrine the mailing list however any written format that's transparent should be okay (Samuel). Are we trying to capture preferences or what the charter says?
        - The spirit is operating transparently are we have different forums to do that (Nisha)
        - We can redirect as necessary (Phil)
        - Is the determination that community can reach out via any forum however we can redirect to the right forum if needed? (Nisha)
        - Where does TOB have their meeting? (Nisha)
        - This meeting is not meant for TOB business (Samuel)
        - It's published on the TOB repo, they don't happen often but are open (Samuel) - It's as needed (Phil)
        - There is not a single conclusive place to raise or close a conversation because other channels have come online. (Vincent)
        - Hope people come to this meeting to get maintainers' attention, not TOB's attention (Phil)
        - Are you concerned that things aren't being responded to? (Samuel)
        - Let's move these conversations to the mailing list (Nisha)
    - Charter Amendments - new and existing
- Dist spec 1.1.0-rc1 ? (Josh)
    - Can we put out a 1.1? Are there concerns with doing that? There's a milestone that has auth on there, can we remove? (Josh)
    - Should this be a 1.0.2 rather than a 1.1.0. I don't know if/what there are new features (Vincent)
    - Let's talk more in Github (Josh)
    - I feel like we could have a 1.0.2 (Vincent)
    - The risk is that without testing extensions could change underneath. We need a mechanism to test (Josh)
    - I'll start an issue with our next release (Josh)

### Notes:
- Do we think there are providers our there that won't want to list extensions via discovery? (Brandon)
-- 
---

## February 3, 2022

**Recording**: https://youtu.be/IeMYGjCXDOc


### Attendees:
- Phil Estes (AWS)
- Tianon
- Brandon Mitchell
- Samuel Karp (AWS)
- vbatts (MSFT)
- Brian Goff (MSFT)
- Flavian Missi
- Sajay Antony (MSFT)
- Ramkumar Chinchani (Cisco)
- Josh Dolitsky (Chainguard)

### Note Taker:

- Nisha Kumar

### Actionable Agenda Items:
- _add your items_

### Presentation/Discussion Agenda Items:
- TOB: Process documentation items? (Nisha)
- PR #111 - https://github.com/opencontainers/distribution-spec/pull/111 (sajay) 
- _add your items_

### Notes

Things to document
- How to become maintainers
- Policies can be separate from CHARTER
- CHARTER has PRs
- What is stale about the CHARTER
    - TDC is outdated, not well-defined
- CHARTER amendmends
    - Linux Foundation has legal oversight
    - In practice Chris and Amye helps with this and it's something we can write down

Note taking:
- Call out for notetaker

Triaging:
- Call for triage

Issue #111:
- Need distribution spec maintainers to merge
- Sajay who can approve this PR?
    - 3 maintainers on the call
    - Steve approved
    - Jon will take a look
    - Tianon will also look
- Reference types WG update
    - User stories organized and categorized by Josh
    - Know things, Discover things, and Store things
    - Idea: push, pull, discover, manage
    - Working 
    - Doc: https://docs.google.com/document/d/1ky0LMAvWL_XRnfId9h5GBswV7GGko5GejuyaMWCGX-Y/edit#heading=h.34dabm576nd3

---

## January 27, 2022

**Recording**: https://youtu.be/4jmcLPiZzME

### Attendees:
- Mike Brown (IBM)
- Sajay Antony (Microsoft)
- Phil Estes (AWS)
- Samuel Karp (AWS)
- Josh Dolitsky (Chainguard)
- Vincent Batts
- Michael Brown (AWS)
- Lachlan Evenson (Microsoft)
- Brandon Mitchell
- _add your name_

### Actionable Agenda Items:
- _add your items_

### Presentation/Discussion Agenda Items:
- Extension proposal?
    - https://github.com/opencontainers/distribution-spec/pull/111 (sajay)
    - 

### Notes:


## January 20, 2022

**Recording**: https://www.youtube.com/watch?v=-sNpTfB_UFs

### Attendees:
- Josh Dolitsky
- Mike Brown (IBM)
- Sajay Antony (Microsoft)
- Samuel Karp (AWS)
- Brandon Mitchell

### Actionable Agenda Items:
- Notes to ref types wg: [_add your items_](https://docs.google.com/document/d/1SVOWQTowigXzbYdorzfa7tMmrcm91yK12LvSONqziJY/edit#heading=h.xzjuckal2b2a)

### Presentation/Discussion Agenda Items:
- _add your items_

### Notes:
 - Discuss the [extensions PR #111](https://github.com/opencontainers/distribution-spec/pull/111) for next week and maybe consider merging in the current state depending on input from others. [sajay]

## January 13, 2022

**Recording**: https://www.youtube.com/watch?v=bJ3yqhzK0_o

### Attendees:
- Sajay Antony (Microsoft)
- Steve Lasker (Microsoft)
- Brandon Mitchell
- Samuel Karp (AWS)
- Mike Brown (IBM)
- Ramkumar Chinchani (Cisco)

### Actionable Agenda Items:
- <https://github.com/opencontainers/image-spec/pull/880>
- <https://github.com/opencontainers/distribution-spec/pull/111>
- _add your items_

### Presentation/Discussion Agenda Items:
- _add your items_

### Notes:

## January 6, 2022 🎉

**Recording**: https://youtu.be/Zr13sRtxlac

### Attendees:
- Tianon
- Brian Goff - MSFT
- Mike Brown (IBM)
- Brandon Mitchell (BoxBoat/IBM)
- Steve Lasker (Microsoft)

### Actionable Agenda Items:

- Reminder: [Reference Type Doodle Poll](https://doodle.com/poll/4z8s3bpgqdmg4c49) All times Pacific! 
- _add your items_

### Presentation/Discussion Agenda Items:
- _add your items_

### Notes:

- No agenda, ended meeting early

### Notes:

Open discussion
