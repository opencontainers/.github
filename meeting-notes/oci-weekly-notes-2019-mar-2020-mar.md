# OCI Weekly Dev Meeting Notes Archive - March 2019 to March 2020

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

## December 11, 2019

**recording available**: https://youtu.be/nPWqRjxtFEM

### Attendees:
- Nisha Kumar (VMware)
- Josh Dolitsky (Blood Orange)
- Vincent Batts
- Mike Brown (IBM)
- Ram Chinchani (Cisco)
- Kat Cosgrove
- Rose Judge
- Steve Lasker
- Jon Johnson
- .. a phone number
- serge
- .. another phone number

### Agenda Items:
- App centric rootfs builds for containers (nisha)
    - Joshua Lock and Nisha Kumar (VMware) gave a talk on using linux distro tools to build container images: https://youtu.be/BN7nWlAcz-o
    - Possible/Inevitable collaboration with SIG-Security: https://github.com/cncf/sig-security/tree/master/supply-chain-security
    - Timezone issue: Joshua and other stakeholders are in the EU (and possibly Asia) and the regular meeting hour is not easy

- OCI distribution conformance strategy (jdolitsky)
    - Distribution spec endpoints: https://github.com/opencontainers/distribution-spec/blob/master/spec.md#detail
    - Starting points for test harness
        - Quay tests: https://github.com/quay/quay/blob/master/test/registry_tests.py
        - Zot: https://github.com/anuvu/zot
            - https://github.com/anuvu/zot/blob/master/pkg/compliance/v1_0_0/check.go
      - https://github.com/kinvolk/ocicert
    - Self-certification model
        - k8s conformance example: https://github.com/cncf/k8s-conformance
        - existing OCI repo: https://github.com/opencontainers/oci-conformance
    - Recent discussion
        -  https://groups.google.com/a/opencontainers.org/forum/#!topic/dev/JCpfBI-_woQ
    - Prior discussions (2018)
        - https://github.com/opencontainers/distribution-spec/issues/24
        - https://groups.google.com/a/opencontainers.org/forum/#!topic/dev/jL5yhEIv3Ac

### Notes:
- app centric rootfs
    - looking to build with the constraint of:
        - no external infrastructure (vb: what all does this mean?)
            - (Nisha) means no reliance on any one organization's internal infra or a picky build system
            - Typically, each org has a way of mirroring source code and rolling their own build system to build artifacts. We'd like this to be easily accessable/usable by any developer.
        - provide a manifest of whats included
        - and the sources of the things included
    - we looked at a number of distro tools
    - we want users to be able to do this and not have to set up sophisticated build environments
    - (vb) sounds like https://reproducible-builds.org/ is the place for the conversation
    - Consensus is that although it is a good topic, it is too vast to include in OCI and too young to include in CNCF
    - Next steps is the set up a meeting with individuals who are interested in this topic and come up with goals and outcomes for a SIG
- (vb) no complaints on the approach that dolitsky is taking for the distribution conformance
    - one day maybe having a live leaderboard would be interesting,
    - but for now having tooling that outputs a result, and a github repo for folks to commit the output of their results is a good first step
    - we could even make a generated matrix of results from the committed reports to the repo
    - the pieces to include need to have: 1) version of their tool; 2) a README on the enviroment; 3) version of the conformance tool; etc.

## December 4, 2019
**Recording available:** https://www.youtube.com/watch?v=FgFcXdr5h2c

### Attendees:
- Steve Lasker (Microsoft)
- Nisha Kumar (VMware)
- Vincent Batts
- Brandon Lum (IBM)
- Phil Estes
- Ken Brooks (JPMC)
- Mike Brown (IBM)
- Josh Dolitsky
- Peter Hunt (Red Hat)
- Tycho Andersen (Cisco)
- Eric Ernst
- Derek McGowan
- Ram Chinchani
- Rose Judge
- Sean McGinnis (Dell)
- Serge Hallyn
- Joseph Jones
- Joshua Lock
- Jimmy Zelinske
- Philip Rhoades

### Agenda Items:
- Notary v2 beginnings - identifying the use cases and scenarios. 
- What's needed to declare Distribution 1.0?  
    Are there any breaking changes we should consider now, to avoid a breaking change between 1.0 and +1?
    - Artifact Index work is additive
    - listing images has a clear path with the `_catalog` issue closed (Joey Schorr of quay has a pubsub proposal with general agreement)
    - ("search" has been unrelated and is horribly still a registry v1 API 😬)
    - Notary v2 - seems additive (perhaps we can discuss a "KEP" style provided features)
    - error codes
    - pull in API conformance testing (quay is now open source!)
- SBoM management proposal first pass (TL;DR version because lots of items today)
- App centric rootfs builds for containers?
- FOSDEM dev space for OCI/containers? (https://fosdem.org/2020/schedule/track/containers/)
- runc v1, please!!
    - the hooks discussion is so close to a consensus
    - we should also discuss changing the way we do releases for runc (the voting setup only makes sense for specifications)
- umoci inclusion into OCI
    - call for new maintainers
    - any objections?

### Notes:
- SL - Kickoff
- welcome... large group in attendence 
- Notary: 
    - Stever Lasker: official soln wip for the last year; end to end scenario discovery efforts underway.
    - references:
      - Justin Cormack talk from KubeCon NA: [Redesigning Notary in a Multi-registry World](https://www.youtube.com/watch?v=rB8-rUtrtXM)
      - Notary on DockerHub: https://hub.docker.com/_/notary
      - Notary v2 channel on CNCF slack: https://app.slack.com/client/T08PSQ7BQ/CQUH8U287
      - Notary v2 working Google doc: https://docs.google.com/document/d/1OeH1-PpERE_9bs12klQstlaf-Omn-1_Rapu0DF7FiVg/edit#
    - kubecon NA discussions were successful in part; 
    - Vincent: Red Hat went their own direction based on some of these limitations; interested to collaborate if we can find a common signing solution that meets all requirements.  
    - Support not just images, but other items since work to store [artifacts in oci registries](https://github.com/opencontainers/artifacts) in progress
    - Seattle meeting planned for December 12; may be a dial in (steve add links..for meeting slack etc.) hook up with Steve for details... should be added here soon.
    - Nisha: for discussion: content of the bill of materials integration with notary is this metadata, should metadata efforts be leveraged
- Distribution:
    - Conformance Testing: 
        - [Existing test suite from quay](https://github.com/quay/quay/blob/master/test/registry_tests.py)
        - MVP is that the registries conform/implement the endpoints
    - Error Codes:
        - Error codes, prior work from [Quay](https://github.com/quay/quay/blob/master/endpoints/v2/errors.py)
    - status: waiting to see if there are breaking changes; none noted.. should all be additive.
    - Vince: additive stuff: catalog is not search, looking forward to pub/sub catalog replacement (again additive)
    - Vince: conformance.. requirement for the api? Need status update; quay is open source now.. is there a way to mirror or use that for conformance?
    - Josh: sounds straight forward to make quay agnostic (vince will touch base)
        - Ken Brooks: I also have a bit of bandwidth and I took a look at what Joey linked me to in the Quay repo. Fairly comprehensive, not 100% sure how hard to make it more generic yet.
        - Open Question: Do we move them and to where? mike: probably distribution can we vendor?
    - Derek: small dependency issue before approval: some ambiguity, cleanup effort needed for error codes see issue [#68](https://github.com/opencontainers/distribution-spec/issues/68)
    - References
      - https://github.com/anuvu/zot#compliance-checks
      - [Existing test suite from quay](https://github.com/quay/quay/blob/master/test/registry_tests.py)
      - Error codes, prior work from [Quay](https://github.com/quay/quay/blob/master/endpoints/v2/errors.py)
- SBoM: 
    - Nisha: demo'd an example... index.json includes license info, project and download url, checksum for images (extra meta for image blob) idea is to add a text/plain media type as a blob refering to another blob
    - Vince: has a source code scenario that could go this route with metadata fields for source ids and such
    - Nisha: looking for a meetup... none noted on the call
    - References:
        - [Spdx](https://spdx.org/)
- Wrap up
    - There is time to plan for in peron discussions at KubeCon in March

### Action Items:
- Take first cut to remove Non-Distribution spec items - Jimmy to send email to coordinate meeting to take a crack at it.


## October 30, 2019
**Recording available:** https://www.youtube.com/watch?v=Z9An7H1_lAY

### Attendees:
- Steve Lasker (Microsoft)
- Mike Brown (IBM)
- Renaud Gaubert (RenaudWasTaken) (NVIDIA)
- Matthew Russo (AWS)
- Andrew Sharon (AWS)
- Sam Berning (AWS)
- Eric Ernst (intel)
- Tianon
- Archana Shinde (Intel)

### Agenda Items:
- Hooks naming (RenaudWasTaken): https://github.com/opencontainers/runtime-spec/pull/1008
    - prestart-runtime, mount, start
        - pros: More consistent for hooks authors as "mount" and "start" match LXC's hooks
        - link to one of the pr's for runc.. just for investigation purposes:
            - https://github.com/opencontainers/runc/pull/392/files#diff-ec0220f977914208b5bf7c1ff362365f
    - create-runtime, create-container, start-container
        - pros: names are more descriptive and consistent between themselves
- Artifacts - Closing on `+` vs. `.` for new `manifest.config.mediaTypes` (Steve Lasker)
- _add your topics_

### Notes:
- mediaTypes 
  - Jon provided more details to the RFC for mediaTypes. Steve promises to read the full RFC, so Jon doesn't have to keep ansewring the same question. Steve to put enough context in the artifacts spec, but point to the RFC for details so we don't reinvent what's already there. 
  - Artifacts will move forward with the following approach
    - the uniqueness of an artifact will be the left portion of the `config.manifest.mediaType`, up to, but not including the `+`
    - `application/vnd.oci.image.config.v1` = the uniqueness the `+json` provides the encoding of the config.
    - Artifact authors may choose which encoding they wish to support for their artifact type. OCI may continue to support `+json`, while helm may use `+yaml`. *(Note: Helm will likely continue with json, we're just using this as an example)* The artifact author may choose to support multiples, but we won't expect all artifact types to support all encoding types. Doing so would mean every artifact tool and registry operator would have to support every encoding type, which will just leave to anarchy - ok, difficulty providng consistent support.
    - Artifact authors may choose to NOT provide an actual config object. They may pass `/dev/null` for the value of the config. If an artifact author doesn't use the config object, they don't specify an encoding of the config. `application/vnd.bloodorange.markymark.config.v1` without `+json` provides the unique artifact type, but also says there's no actual config object. If markymark adds a config object, they would rev the version to v2. It would look like: `application/vnd.bloodorange.markymark.config.v2+yaml`
    - As is already covered in the artifacts spec, registry operators are NOT required to parse config objects. They choose to parse them for specific media types.
  - The reason layers use `.tar` is not becuase the format is tar. Rather, `.tar` is part of the unique mediaType: `application/vnd.oci.image.layer.v1.tar` defines a unique diff. If the diff is encoded with compression, like gzip, it would be a `+gzip`
  - Valiating mediaTypes on push: To be compliant with the artifacts spec, a registry MUST support additional mediaTypes, representing new artifacts. However, a registry operator MAY choose which additional Artifact Types they choose to support. A regsitry operator MAY leave validation open, and let a specific registry instance (contoso), decide they only allow a subset of mediaTypes. These are business decisions of the registry operator. 
  - We disscussed the value of understanding what Artifact Types are supported. Either globally, at the registry operator level, or perhaps at a specific registry instance. We will need a spec, and Steve was soliciting help in defining that api. We agreed the api belongs on distribution. 
  - KubeCon - we discussed possibly getting together, to catch up, or have a specific agenda. We also said we'd proactively cancel the OCI call the week of KubeCon. (November 20)

## October 23, 2019
**Recording available:** https://youtu.be/1f5zncjqdBI

### Attendees:
- Steve Lasker (Microsoft)
- Mike Brown (IBM)
- Brandon Lum (IBM)
- Tianon
- Jon Johnson (Google)
- Jeff Borek (IBM)
- Brandon Lum (IBM)
- Jimmy Z
- Rose Judge
- Derek McGowan (Docker)
- Ram Chinchani (Cisco)

### Agenda Items:

- [Artifacts Spec PR Feedback](https://github.com/opencontainers/artifacts/pull/13) Steve Lasker

### Notes:
- Should a tar layer have additional type data.. such as helm version. 
    - Most responses were not necessary, could be useful.
    - Derek/Jimmy: if type data is necessary in the expansion, let's discuss it at that point.
From Jimmy Zelinskie to Everyone:  02:42 PM
https://github.com/facebook/zstd
From Me to Everyone:  02:43 PM
https://www.iana.org/assignments/media-types/media-types.xhtml
From Jon Johnson to Everyone:  02:46 PM
https://www.iana.org/assignments/media-type-structured-suffix/media-type-structured-suffix.xhtml
^ the suffix registry
Would also be a good exercise to add OCI media types to the media type registry?
From Jimmy Zelinskie to Everyone:  02:48 PM
https://github.com/opencontainers/distribution-spec/milestone/3
    - Jimmy: how will this associate with Licensing? This is likely an SBOM content type, which could/would also be signed

## October 19, 2019

No agenda, meeting cancelled

## October 9, 2019
**Recording available:** https://www.youtube.com/watch?v=nVHDaUxdpWs

### Attendees:
- Steve Lasker (Microsoft)
- Mike Brown (IBM)
- Tianon
- Amye SP (CNCF)
- Phil Estes (IBM)
- Jon Johnson (Google)
- Derek McGowan (Docker)
- Chris Aniszczyk (CNCF/OCI)
- Jeff Borek (IBM)
- Casey (JFrog)

### Agenda Items:
- Artifacts Spec Updates (Steve Lasker)
- Review [`_catalog` removal PR](https://github.com/opencontainers/distribution-spec/pull/69)

### Notes:
- General discussion on how to move along with the removal of the [`_catalog` endpoint](https://github.com/opencontainers/distribution-spec/pull/69) as a required part of the 1.0 distribution spec. It will be a reserved API route, but there will be no recommended (or optional) implementation of a Catalog API.
  - agreement from a few maintainers on the call to get reviews completed soon, no disagreement on the general direction and wording.
- Steve Lasker discussing current status of artifacts; referred to [opencontainers/artifacts#13](https://github.com/opencontainers/artifacts/pull/13) in the chat.
  - Noted a dependency: to finalize an artifacts "1.0" spec there is a dependency on releases of image-spec and distribution-spec

## October 2, 2019 
**Recording available:** https://www.youtube.com/watch?v=-8ZN2f-anHI

### Attendees:
- Matthew Russo (AWS)
- Mike Brown (IBM)
- Phil Estes (IBM)
- Steve Lasker (Microsoft)
- Amye Scavarda Perrin (CNCF)
- Nisha Kumar
- Ram Chinchani (Cisco)
- Tycho Andersen (Cisco)
- Serge Hallyn
- Jon Johnson
- Rose Judge
- Tianon
- Derek McGowan

### Agenda Items:
- [zot](https://github.com/anuvu/zot): A reference implementation of [distribution-spec](https://github.com/opencontainers/distribution-spec) (Ram Chinchani - Cisco)

### Notes:
- Zot is an alternative reference implmentation to [docker/distribution](https://github.com/docker/distribution)
- Focused on oci-distribution spec as first class experience. Using the OCI layout

## September 26, 2019

Registry Operator Focus: (US, Europe and China representation)

> Special Time: 7am PST, 10am EST, 3pm UK, 4pm Europe, 10pm AEST
> See above for the call info
> [Google Calendar entry](https://calendar.google.com/event?action=TEMPLATE&tmeid=NmxwbWRtdmN2b3F0azlnNWltZm4zNGxxZTkgZXN0ZXNwQG0&tmsrc=estesp%40gmail.com)

Recording available: https://www.youtube.com/watch?v=fuDtIFvgLxk
### Attendees:

- Steve Lasker (Microsoft)
- Ravi Chamarthy (Cisco)
- Justin Cormack (Docker)
- Matthew Russo (AWS)
- Amye Scavarda Perrin (OCI) 
- Phil Estes (IBM)
- Stuart Hayton (IBM Container Registry)
- Jack Baines (IBM Container Registry)
- Jon Johnson (Google CR)
- Josh Oberwetter
- Nisha Kumar (VMware)
- Jimmy Zelinske
- Omar
- 3 dial-in participants

### Agenda Items:

- [Artifacts Baseline](https://github.com/opencontainers/artifacts) discussion with various operators (Steve Lasker - group)
- [OCI Artifact Signing - Requirements](https://hackmd.io/Rs4G0I4lSAO-Fdrdchweqg) (Steve Lasker - group interest)
- [OCI Artifact Search Requirements](https://hackmd.io/mF80aTt8TC-GiGHOyPG-dw) (Steve Lasker - group interest)

### Notes:

- Artifacts Baseline
    - Steve Lasker discussed general overview of artifacts background; ACR adding Helm, rethinking concepts of basic registry capabilities.
    - Presented [OCI Artifacts Deck](https://github.com/SteveLasker/Presentations/blob/master/ACR/OCIArtifactRegistries.pptx)
    - Issues for commonality:
      - Search (non-standard "catalog" API)/query.
      - Common understanding of media types (beginning to be solved with the new artifacts project)
      - Signing (on the agenda for discussion-TUF vs. ?)
    - [Nisha] How does SPDX/bill of materials metadata fit into this discussion vs. "OCIv2" discussion, etc.
    - [Jimmy](/KtL_LoykQdaoh1bpwsU8kg) separating discussion of metadata for registry search (indexable/"annotation" data that helps provide search capabilities) vs. content-specific "metadata"
- Artifact Signing Reqs
    - Steve shared the [HackMD link](https://hackmd.io/Rs4G0I4lSAO-Fdrdchweqg) with a basic description of open issues to get to a common signing solution. Open question: do we move this somewhere more formal in OCI to start a broader discussion?
    - [Josh] AWS ECR working on this topic now; definitely some issues with trying to maintain DCT support and support customer-required features.
    - [Justin] working on a draft proposal to help with some issues of current Notary/TUF/DCT implementation (e.g. storing signatures in registry vs. Notary's db)
    - [Jimmy] usable vs. adopted security discussion; Notary/TUF solves real security issues but adoption is low.
    - [Justin] schema1 meant all images were signed, but was totally useless :) finding the actual requirements and then determining the right path is important to the discussion
- Artifact Search Reqs
    - Ran out of time to discuss search topic.


## September 25, 2019

### Agenda Items:
- No agenda items for this week

## September 18, 2019 

### Attendees:
- Derek McGowan
- Phil Estes
- Mike Brown (IBM)
- Tianon
- Brandon Lum
- Josh Dolitsky
- Jon Johnson
- Nisha Kumar

### Agenda Items:
- [Media types](https://github.com/opencontainers/image-spec/issues/791) (Derek McGowan)

### Notes:
- Discussion about "taming" media types (see image-spec [issue 791](https://github.com/opencontainers/image-spec/issues/791)) regarding endings of the media type strings ('+tar' or '+json' vs. '.tar' or '.json' as one example)
- [dmcg] do we want a clearly parseable format with ordering as to how to "unpack" a certain media type?
- [jonjohnson] Want the ease of being able to write a client that can handle (generally) new media types without one-off handling of each new type.
- [dmcg] do we need/want pre-defined suffixes registered? (per RFC) Speed of that process probably too slow.
- [jonjohnson] but maybe the spirit of that without the explicit process of the RFC registration
- [jonjohnson] would be nice to clean up foreign layer implementation along with this at the same time
- [josh] Helm mediatypes: [code](https://github.com/helm/helm/blob/dev-v3/internal/experimental/registry/constants.go#L19) [docs]( https://v3.helm.sh/docs/topics/registries/#where-are-my-charts)
    - `application/vnd.cncf.helm.config.v1+json`
    - `application/vnd.cncf.helm.chart.content.layer.v1+tar`
- [dmcg] work items: (1) add something to image-spec with description of known media types, link to RFC, (2) add guidance to artifact repo on how to create new media types, (3) add compatability plan for supporting zstd in v1.1 and more generally for v1.1+
- [dmcg] encryption case: let's discuss what it means to have an encrypted layer media type
- [brandon] opinion is that the marker in the media type should remain generic and will not explicitly specify the encryption algorithm. Changes will happen there regularly and cause churn.
 
## September 11, 2019

### Agenda Items:
- No agenda this week; we will **not** have a meeting.

## September 4, 2019

### Agenda Items:
- No agenda this week; we will **not** have a meeting.

## August 28, 2019

### Attendees:
- Steve Lasker (Microsoft)
- Mike Brown (IBM)
- Radu Matei (Microsoft)
- Trishank Kuppusamy (Datadog)
- Tianon
- Nisha Kumar (VMware)
- Phil Estes (IBM)
- Amye Scavarda Perrin (CNCF)
- Andrew Sharon (AWS)
- Samuel Karp (AWS)
- Kay Williams
- Jacob LeGrone (Datadog)
- Samuel McGraw
- Rose Judge
- Tue Tran (AWS)

### Agenda Items:
- Artifacts & TUF support (Steve Lasker)
- Guidance on incrementing the index schema version (Radu Matei) - [WIP PR](https://github.com/radu-matei/image-spec/pull/1) and [meeting notes from Barcelona](https://hackmd.io/w6pY2gAVSq6tD_exH7_f0g#Index-Conversations)
- ...

### Notes:
- Artifacts & TUF support 
    - [Phil] IBM Registry has also implemented TUF & Notary and having similar challenges. 
    - [Phil] Should the signing meta-data travel with the artifact (image)
    - [Hackmd: Early conversations about a cross registry signing solution](https://hackmd.io/xYjvPhRMSYi7FqKYc4AWDA)
    - [Nisha] Looking for a way to attach container providance info with an image. Concern over how to verify where the conent was sourced from, and where it went.
    - [Trishank] - does it matter where it came from, as long as we know: (1) which keys are supposed to sign for which things, and (2) the things we care about haven't been tampered with since it was created?
    - [Trishank] - TUF tells you whether things (e.g., container images) have been tampered with between repositories and end-users. in-toto tells you about the provenance of things (e.g., container images) in your software supply chain: who wrote which source code, which source code did CI use to produce container images from, and so on. Using both TUF and in-toto gives you end-to-end guarantees about the authenticity and integrity of things (e.g., container images, or bundles), regardless of where they came from.
    - [Steve] - propose a follow-up meeting, at a time those in Europe (IBM registry folks and Justin Cormack) and China (Harbor) can join. They have expressed interest in the signing topics.
    - [Nisha] Concern over how the content, as it's built and traveled is accounted for.
    - [Nisha/Steve] Is there a means for how history of the artifact can be tracked?
    - [Radu] ^ this is what CNAB is doing with in-toto & tuf
    - [Radu] For things like OPA bundles that might be persisted to things outside an OCI Registry, the signature should be on the content, not the manifest. The manifest is an OCI/Distribution thing. Can the approach take into conseration the signing content is just a paylaod that gets stored with the artifact?
- Guidance on incrementing the index schema version
    - [Radu] How do we increment the version?
    - [Radu] Should `index.config` be optional or required?
    - [Phil/Mike] For the [go versioning](https://github.com/opencontainers/image-spec/blob/master/specs-go/version.go), there's a versioning reference.
    - [Steve] The proposal is about reving the Index Schema to a newer version which clients can choose to support. Would need to validate existing clients would know to check for new versions, or not support new versions unless they opt in. 


## August 21, 2019

No meeting this week as several people are at the Open Source Summit.

## August 14, 2019

### Attendees:
- Steve Lasker (Microsoft)
- Tianon
- Phil Estes (IBM)
- Jeff Borek (IBM)
- Nisha Kumar (VMware)
- Mike Brown (IBM)
- Chris A (CNCF/OCI/LF)
- Vincent Batts
- Derek McGowan
- Jimmy Zelinskie

### Agenda Items:
- Distribution Spec (Derek)
- [Artifacts TOB](https://github.com/opencontainers/tob/pull/60) discussion (Steve Lasker)

### Notes:
- derek things:
  - distribution-spec
  - fix the "optional" nature for intrepreting the spec
  - https://github.com/opencontainers/distribution-spec/milestone/3
  - closed https://github.com/opencontainers/distribution-spec/pull/45
  - lasker to do the amended PR
  - mirroring PR https://github.com/opencontainers/distribution-spec/pull/66
  - thoughts on the server-side behavior for caching (zelinskie)
- lasker on artifacts
  - https://github.com/opencontainers/tob/pull/60/files
  - https://github.com/opencontainers/tob/

## August 7, 2019

### Attendees:
- Steve Lasker (Microsoft)
- Phil Estes (IBM)
- Nisha Kumar (VMware)
- Mike Brown (IBM)
- Jimmy Z
- Amye (OCI/LF)
- Derek McGowan (Docker)

### Agenda Items:
- None

### Notes:
- Brief discussion on artifact TOB PR process moving towards a formal vote after next week's meeting
- Discussed agenda-by-Friday plan going forward for better planning/use of time

## July 24, 2019

### Attendees:
- Alban Crequy (Kinvolk)
- Phil Estes (IBM)
- Nisha Kumar
- Mauricio Vasquez
- Tianon
- Rose Judge
- Amye (OCI/LF)
- Matthew Russo (AWS)

### Agenda Items:
- How I use OCI Hooks in Inspektor Gadget and limitations (Alban)
    - Slides https://docs.google.com/presentation/d/1i8csKAf15j3ZDeHxuUlHBDvHiBI44_UxATdaaAy-pjE/edit

### Notes:
- OCI Hooks: talk about it at sig-node (CRI annotations idea on Alban's last slide)
- OCI Hooks: status of spec and runc 1.0 with regards to hook implementation? [runtime-spec#1008](https://github.com/opencontainers/runtime-spec/pull/1008)
    - Fortunately for Inspektor Gadget, it would work regardless of the change in the spec above.

## July 17, 2019 


### Attendees:
- Steve Lasker (Microsoft)
- Andrew Sharon (AWS)
- Phil Estes (IBM)
- Derek McGowan (Docker)
- Mike Brown (IBM)

### Agenda Items:
- OCI Artifact Registries - [Discuss a new repository for artifacts](https://github.com/opencontainers/tob/issues/59) (Steve Lasker)

- _add your topics_

### Notes:
- Steve to use the [digests propsoal](https://github.com/opencontainers/tob/blob/master/proposals/digest.md) as a starting point for artifacts, and move the [artifact issue](https://github.com/opencontainers/tob/issues/59) to a PR on the TOB. 
    - At the top of the artifacts explain the index and manifest defintions
    - Within the repo have a collection of exsting artifacts, including the image spec mediaTypes, similar to the [PR on distribution](https://github.com/opencontainers/distribution-spec/pull/65/)
    - set of maintainers:
        - Steve Lasker (Microsoft)
        - Derek McGowan (Docker)
        - Mike Brown (IBM)
    - Once proposal apporved, Chris to create the repository 
- _meeting minutes_
- 
## July 10, 2019

### Attendees:
- Alban Crequy (Kinvolk)
- Steve Lasker (Microsoft)
- Tianon
- Phil Estes (IBM)
- Andrew Sharon (AWS)
- Matthew Russo (AWS)
- Michael Brown (AWS)
- _add yourself_

### Agenda Items:
- (alban) Container Escape Bounty: status update on the implementation
  - GitHub: https://github.com/kinvolk/container-escape-bounty
  - Slack: CNCF slack #containerescape
  - Slides: https://docs.google.com/presentation/d/123eRB2ksS1_S-UGCfpgK6ZQgTBOCnHndgyFaOUWuh9Y/edit
  - Demo: temporary URLs
      - https://albanbox.selinux.contained.nicht.fun/
      - https://albanbox.apparmor.contained.nicht.fun/
      - User: user
      - Password: 
- OCI Artifact Registries - Discuss [feedback whether OCI is the right working group](https://github.com/opencontainers/distribution-spec/pull/65/) (Steve Lasker)

### Notes:
- Alban presented the above escape bounty work; slides and demo links in the agenda.
- Steve presented on the distribution spec PR #65; Derek provided feedback and a general plan was made to move forward on this work within the OCI.

## July 3, 2019

### Attendees:
- Alban Crequy (Kinvolk)
- Steve Lasker (Microsoft)
- Tianon
- Phil Estes (IBM)
- Samuel Karp (AWS)
- Matthew Russo (AWS)
- Andrew Sharon (AWS)
- Michael Brown (AWS)

### Agenda Items:
- Without much of a quorum today, we decided to take the 2 agenda items and copy them to July 10th and hope for better turnout to discuss these items.

### Notes:
- See agenda

## June 26,2019 

### Attendees:
- Steve Lasker (Microsoft)
    - "Apologies. I’m in customer meetings that are running longer than planned."
- Tianon
- Matthew Russo (AWS)
- Vincent Batts
- Andrew Sharon (AWS)
- Samuel Karp (AWS)
- Michael Brown (AWS)
 

### Agenda Items:
- OCI Artifact Registries - Discuss [feedback whehter OCI is the right working group](https://github.com/opencontainers/distribution-spec/pull/65/) (Steve Lasker)
- 

### Notes:
- alternative mime-type behaviour as a registry provider
  - AWS registry (ECR) does a white list of mime-types
  - if there are random new mime-types being pushed here, they would fail
  - AWS is more of a wait-and-see what folks use and need
  - (vb) we need to arrive at what kind of generic building blocks of API for discovering mime-types supported by a registry.
  - (vb) otherwise folks looking to copy/push and image with say the source container representation to that cloud providers registry will get failures and has less than favourable experience
  - (vb) further, if we can iron out this API interaction then it could easily be where registry providers build a value add layer to enable "enhanced" media being pushed to the user's registry


## June 12, 2019 

### Attendees:
- Josh Dolitsky
- Mike Brown (IBM)
- Brandon Lum (IBM)
- Samuel Karp (AWS)
- Clare Liguori (AWS)
- Michael Brown (AWS)
- Matthew Russo (AWS)
- Eric Ernst
- Phil Estes (IBM)
- Nisha Kumar
- Steve Lasker
- Rose Judge
- Radu Matei (Microsoft)
- Andrew Sharon (AWS)
- Kenneth Brooks (JPMC)
- Tianon (just long enough to hear the meeting end ;.;)

### Agenda Items:
- Encrypted container images proposal. More details/links in [this message](https://groups.google.com/a/opencontainers.org/forum/#!topic/dev/wjsxe-4k2Io)
- Quick intro to [Bundle Bar](https://bundle.bar/) - Josh Dolitsky
- How do you whitelist mediaTypes in docker/distribution? - Josh Dolitsky
    - See [docker/distribution#2928](https://github.com/docker/distribution/issues/2928)

### Notes:
- Brandon Lum (firstname.lastname(at ibm.com)) from IBM Research presented on encrypted container images - can share deck that was shared in Zoom.
  - OCI intersection is a proposal to add encrypted layers to image spec [PR #775](https://github.com/opencontainers/image-spec/pull/775)
  - [Slides](https://ibm.box.com/s/jheivnn2ztj63zc4ik78ix7im8j6f9r7)
  - [DockerCon Presentation](https://www.docker.com/dockercon/2019-videos?watch=enabling-high-assurance-sensitive-container-workloads-with-e)

## May 29, 2019

### Attendees:
- Nisha Kumar
- Steve Lasker
- Mike Brown (IBM)
- Vincent Batts
- Clare Liguori (AWS)
- Samuel Karp (AWS)
- Kenneth Brooks (JPMC)
- Rajat Chopra (Nvidia)
- Matthew Fisher (Microsoft)
- Radu Matei (Microsoft)
- Josh Dolitsky

### Agenda Items:
- SPDX document as a container BoM. Here is an [example doc](https://github.com/nishakm/tern/blob/c3f8f7954f6970ad814566044f46a45723b43061/docs/spdx_output_golang_1.12_alpine.txt) - Nisha Kumar
- OCI Artifact Registry recap from KubeCon meeting - Steve Lasker
  - [Full notes here](https://hackmd.io/s/S1X6JNnTN)
  - [Distribtuion Spec PR](https://github.com/AzureCR/distribution-spec/blob/artifact-registry/artifacts.md)

- Follow up on pre-start/mount hooks https://github.com/opencontainers/runtime-spec/pull/1008 - Rajat Chopra
- vbatts, call to action

### Notes:
- spdx as a BoM, nisha
    - https://spdx.org/
    - last year at kubecon NA, nisha had a bof about build manifests that had good interest and reception
    - container build manifest - https://docs.google.com/document/d/1J4G45vmQQiemYN0C4Thn1mbA83RZ0iS2uTQFft9DJhU/edit
    - this currently done on the end-result container image artifact (so steps along the way, like crazy one-liners, multi-stage and squashed images would be lossy)
    - upstream spdx has parsers and validators
    - just provide your own generator
    - license fingerprinting is a caveat
    - looks similar to https://github.com/docker-library/repo-info/tree/master/repos/wordpress/local by tianon
- kubecon OCI Artifacts discussion recap, lasker
    - see [notes](https://hackmd.io/s/S1X6JNnTN)
    - pushing more mediatypes than just manifests, image configs or tars, is generally agreed as a valid approach
    - this may be an assumption than many clients fail on
    - gareth showed a test with this with an opa manifest, and docker client failed (expected)
    - next steps
      - open an issue on image-spec to add `index.config`
      - open PR on distribution spec to define how to process the new manifest and index types. [Distribution-Spec OCI Artifacts](https://github.com/AzureCR/distribution-spec/blob/artifact-registry/artifacts.md)
      - Review the foreign manifests requirement in a subsequent meeting
- hooks follow-up, rajat
    - this needs closure. runtime maintainers, please review the PR below
    - https://github.com/opencontainers/runtime-spec/pull/1008

## May 01, 2019

### Attendees:
- Steve Lasker
- Vincent Batts
- Michael Brown
- Vanessa Sochat
- Aleksa Sarai
- Atlas Kerr
- Jeff Borek
- Nisha Kumar
- Colin Rice

### Agenda Items:
- `/_catalog` https://github.com/opencontainers/distribution-spec/pull/45#issuecomment-487030819
- new listing api disucssion https://hackmd.io/s/BJPAUxDvV#OCI-Catalog-Listing-API---Workgroup
- artifact registry update
- new hooks for runtime-spec https://github.com/opencontainers/runtime-spec/pull/1008

### Notes:
- (see recording)
- `_catalog`
    - (lasker) there are registries that have not implemented it and will not.
    - So removing `_catalog` from the spec doesn't mean that folks will have to remove it from their registry, but rather that it will be easier for others to be compliant.
- new listing API workgroup
    - https://hackmd.io/s/BJPAUxDvV#OCI-Catalog-Listing-API---Workgroup
    - https://github.com/opencontainers/distribution-spec/issues/22#issuecomment-417143466
    - https://github.com/opencontainers/distribution-spec/issues/22#issuecomment-470727620
    - TODO present this (mbrown, slasker)
    - (vb) my concern is removing the `_catalog` API without having an actionable plan to provide listings. Having considered ACLs and performance impacts.
- path forward for contributions
    - writing tools
    - solving an actual use-case
    - working groups, for a use-case. A timeline, then a presentation with an action from the maintainers.
- artifact update
    - mediaTypes. how to add or advertise
    - adoption on azure, helm, CNAB and singularity [Azure Container Registry now supports Singularity Image Format containers](https://azure.microsoft.com/en-us/blog/azure-container-registry-now-supports-singularity-image-format-containers/)
    - lasker, feels good about the agreement with zelinski for whitelist/blacklist mediatTypes for what a registry supports. Whether a registry whitelists, or blacklists will likey be a registries unique decision. Without a[mediaType mapping](https://github.com/SteveLasker/RegistryArtifactTypes/blob/master/mediaTypeMappings.json), a registry could only show the `mediaType` in their UI. We're hopeful it will be super easy to just import a mapping to get a clean string and icon. We'll know more as we get more of the APIs and experience complete. 
- Bill-of-materials
    - nisha give a bit of an update on her Tern research
    - aleksa: definitely interested
    - colin: works on grafeas and feels that there is Bill of Materials features that could be useful here
    - aleksa: let's set up a WG and see how it goes

From Zoom chat:
17:21:08	 From vbatts : https://github.com/opencontainers/distribution-spec/issues/22
17:21:56	 From jonjohnson : That was my "let's not reinvent everything" proposal if we want to land something in v1
17:24:32	 From jonjohnson : couldn't get a room so no mic
17:24:36	 From jonjohnson : https://github.com/opencontainers/distribution-spec/issues/22#issuecomment-417143466
17:24:43	 From jonjohnson : ^ what other folks are doing instead of catalog (us included)
17:27:46	 From jonjohnson : docker/distribution does have catalog: https://github.com/docker/distribution/blob/c192a281f8ac6f2a351fe729c8a56108f8edb377/registry/handlers/catalog.go#L36


## April 17, 2019 

https://youtu.be/h2oapEhNaBA (vb) I don't know how to youtube org for this to live not on my account.

### Attendees:
- Renaud Gaubert (NVIDIA)
- Rajat Chopra (NVIDIA)
- Alban Crequy (Kinvolk)
- Vincent Batts
- Tianon
- Jimmy Z
- Gilbert Song
- Michael Brown (AWS)
- Samuel Karp (AWS)
- Eric Ernst
- Vanessa Sochat

### Agenda Items:
- Runc pre-start hooks (added by Renaud Gaubert, NVIDIA)
  - "libcontainer: call Prestart, Poststart hooks from correct places" https://github.com/opencontainers/runc/pull/1811
- Proposal to add Scientific Filesystem (added by Vanessa Sochat, Stanford)
  - https://github.com/opencontainers/tob/pull/58
  - we can move to next week if the first topic needs majority of time

### Notes:
- nvidia and runc hooks (Renaud Gaulbert)
  - cuda linking includes a number of linking (10-15 shared objects) (tightly coupled to kernel driver version)
  - (rajat) the binary is not portable, as it is dependent on the hardware
  - even the kernel, the module doesn't do reload, as it gets bound to the hardware
  - device nodes, ipc, and cuda.so
  - the problem is that the current prestart-hook, is already in the container so it is cut off from the host. The OCI pre-start is very similar to what LXC does, except that LXC pre-start happens with host access
  - the way runc currently does it works, but the spec is not clear that it happens _before_ pivot_root
  - (ernst) though this assumption gets dicey when the "inside container" is a VM. Would be good to be more explicit on where the hook is expcted to run
  - (renaud) kata behaves like runc does, where it expects to be before pivot_root
  - (vbatts) this sounds like an update to the runtime-spec to line up with how runc is, and if it is actually how runc works, then just line up the spec. 
  - summarize this discussion, and aleksa is a stakeholder. Ideally this is resolvable on list or PR
  - (vbatts) the hellish thing here is: a change to the spec like this could be considered "breaking", therefor a v1.1. So it would begin the skew of "which version of the spec you conform to"; and a change like adding a `pre-start-host` to the spec, and then getting runc to split the current behavior into the two (one on host, then `pre-start` in container) would cause a hellish compatibility matrix among runc versions out there.
  - (rajat) this is going to happen either way, so it is a matter of accepting the choice of pain
  - (vbatts) fair
  - (vbatts) (post-meeting delirium) i wonder if the least hellish option here is the one that adds most cruft. If we leave the current ambiguous wording of `pre-start`, with the assumption that folks implement bug-for-bug with runc, and then add _two_ hooks that are painfully clear like `pre-start-host` and `pre-start-container`. Then existing implementations can continue as is, the spec wouldn't have to introduce a "breaking" version and now there is a target for nvidia's workflow.
        @vbatts you were drinking wine! It's the winirium :)
        (vb) also fair
  - (tianon) maybe `pre-start-inside` vs `pre-start-outside` so it's slightly more generic where terms like "host" and "container" might still be ambiguous? (or perhaps bike-shedding too far /o\\)
         
- scientific filesystem
  - proposal to add to OCI
  - "semantic web for compute units"
  - specification for organization and interaction with (internal) modules "apps" in a container
  - goals are discoverability and programmatic accessibility for metadata, help, labels, etc.
  - It provides more than one entrypoint (runscript), help snippet, labels, environment for a single container
  - You can find a black box container and know the applications, usage, etc. inside without being the creator or having the Dockerfile
  - @vsoch is (about halfway?) done with a GoLang implementation of the spec, and will (re-propose) to the TOB list when she finishes. TBA!


## April 03, 2019

UberConf?!?!?
we're going to have to evaluate other conf options!
cleared for next week: https://zoom.us/my/opencontainers

### Attendees:
- Alban Crequy (Kinvolk)
- Steve Lasker
- Atlas Kerr
- Vincent Batts
- Tianon
- Samuel Karp
- Vitalii Syrovatskyi
- Gilbert Song
- Richard Nguyen
- Phil Estes (visually only)
- (really tough to say; technical difficulties)

### Agenda Items:
- (alban) Container Escape Bounty
  - Slides: http://bit.do/containerescapeslides (draft)
  - GitHub: https://github.com/kinvolk/container-escape-bounty
  - Slack: CNCF slack #containerescape
  - (Tianon) https://twitter.com/jessfraz/status/1030478243328077824 is related (bounty on contained.af)
- (Steve) OCI Artifact PR: https://github.com/opencontainers/image-spec/pull/770
- (Mike, Steve, Atlas) Catalog & Tag Listing  Requitements & Scenarios
- (Atlas) Rehash ideas on Content Management/Registry spec

### Notes:
- Container escape bounty
    - CVSS scoring would be correlated to the reach of the escape
    - should we have multiple scenarios? from least strict (loose seccomp, no LSM, no userns), to most strict ()
    - we should have a trial to test out the scenarios
    - this ought to be a time boxed bounty
    - Action: 
- uberconf booted our call!
- switch to zoom.us
- Artifact type PR

## March 27, 2019

Small group of attendees joined; no specific topics had been added to agenda. Agreed to adjourn and focus on an agenda and right participants for next week.

## March 20, 2019

### Attendees:
- Phil Estes
- Vincent Batts
- Mike Brown
- Tianon
- Vanessa Sochat
- Jon Johnson
- Kenneth Brooks
- Samuel Karp
- Vitalii Syrovatskyi
- Steve Lasker
- Clare Liguori
- Michael Brown !! (the 2nd?) :)
- Richard Nguyen
- Nisha Kumar

### Agenda Items:
- OCI support for OSS compliance (based on https://hackmd.io/xYjvPhRMSYi7FqKYc4AWDA or other?) 
- [Catalog API Discussion](https://hackmd.io/s/BJPAUxDvV#OCI-Catalog-Listing-API---Workgroup)
- [Artifact PR](https://github.com/opencontainers/image-spec/pull/770/)

### Notes
#### OCI support for OSS compliance
- Nisha
    - folks seem to be treating the whole image as an artifact
    - but the whole bundle is an OS, so distributing it you become an OS provider
    - Therefore it is not just the source of your application, but the source of all the components
    - there is no information about the images that were used in the production of the resulting image, and their sources
    - I see the best approach is to use annotations
    - vbatts thoughts would be to append an object that is a kind of manifest list, like:
```json
{
        "packages": [
                {
                        "name": "acl",
                        "format": "rpm",
                        "version": "2.2.51",
                        "release": "12.el7",
                        "arch": "x86_64",
                        "source": {
                                "format": "rpm",
                                "name": "acl-2.2.51-12.el7.src.rpm",
                                "digest": "sha256:deadbeef...",
                                "url": "https://my.content.store.com/..."
                        }
                }
        ]
}
```
- cont.
    - even to have a bill-of-material (BoM) would be tremendous
    - sochat: container-diff
    - this is very important, and there is some trickiness in having the runtime _and_ the source produced potentially out of band of each other, but tied to each other. From one you can discover the other. And clients can fetch only what they're interested in.
    - nisha: the other concern here is whether this is inventing new concepts that clients are not compatible with.
    - vbatts: that is definitely a point of this, to innovate withing what is already supported, or will not break existing clients even if they can not use the new features.
    - tianon has some automation around this for images built, like https://github.com/docker-library/repo-info/tree/master/repos/wordpress/local
    - nisha: feedback is to have a registry type(?) that will store metadata which can be queried independent of downloading the image but can be used to get info for said image if a user so chooses

#### Catalog Listing API thread
- Mike B. like stevvooe's proposal: https://groups.google.com/a/opencontainers.org/d/msg/dev/MFUjpt5fxNc/MjXye3rhCQAJ
    - registry behavior on "Accepts" headers
    - tianon has seen where some Accepts can be a list in a single header, but some registries expect multiple Accept headers with a single value
        - https://github.com/docker/distribution/pull/1782 (fixed in Docker's registry implementation)
- steve lasker: catalog API
    - Can we set a deadline for use cases and constraints by end of April? This would enable us to transistion into designing an API. Perhaps, meet at KubeCon to hash out in person.
    - https://hackmd.io/s/BJPAUxDvV#OCI-Catalog-Listing-API---Workgroup
- mike b. to set of a gathering at KubeCon Barcelona

#### Registry Artifacts

- Steve Lasker
    - Would like to get some more feedback on the [image-spec PR 770](https://github.com/opencontainers/image-spec/pull/770/) before moving to a distribution-spec PR. Thanks to Venessa, Atlas & Clare thus far.
    - Planning on having the Helm 3 Repository work in alpha state by KubeCon
    - Will queue up a discussion for next weeks call

## March 13, 2019

Tomorrow is Pi Day :)

### Attendees:
  - Vincent Batts
  - Tianon
  - Phil Estes
  - Vanessa Sochat
  - Filipe Brandenburger
  - Clare Liguori
  - Giuseppe Scrivano
  - Samuel Karp
  - Mrunal Patel
  - Atlas Kerr
  - Crosby Michael
  - Mike Brown

### Agenda Items:
  - Catalog API Discussion
  - [HackMD Integration Degree](https://github.com/opencontainers/org/pull/13#issuecomment-471387467): 
      - should we link to allow automatic pull requests? 
      - are the permissions okay so we don't place our content at risk?
  - Cgroupv2 in OCI and runc ([@filbranden](https://github.com/filbranden))
      - Adapting OCI to cgroupv2: [memory container case study](https://github.com/opencontainers/runtime-spec/issues/1005)
      - [Improve libcontainer's systemd cgroup driver](https://github.com/opencontainers/runc/issues/2007)
  - [Management spec](https://github.com/open-package-management/spec)
 

### Notes

* Catalog API (lasker and atlas)
  * atlas' topic is a biggie
  * currently the /v2 API is a nested URL based name
  * VERB should be used instead of URL approach (i.e. `.../list`)
  * "what is the scope?"
  * dropping --> https://github.com/opencontainers/distribution-spec/blob/master/spec.md#listing-repositories
  * but not dropping --> https://github.com/opencontainers/distribution-spec/blob/master/spec.md#listing-image-tags
  * drop `/v2/_catalog` https://github.com/opencontainers/distribution-spec/pull/45
* str8-to-repo (vsochat)
    * trust level on app permissions VS 
* cgroup V2 (filipe)
    * many things map, but not everything
    * systemd has mapped the generic settings, but not all nice new features of v2/unified
    * freezer is looking like kernel v5.2
    * hybrid mode? may work for migration, but would be sloppy and slow. could be too confusing
    * nested containers could mount legacy cgroup, but the host may be only unified
    * freezer feels like the only acceptable option for atomic operation on the pids/tasks. SIGSTOP approach feels like ducktape
    * device controller is now ebpf and there is gaps
    * new spec semantics is whitelisting, which is fine
    * old spec semantics has blacklisting, which is not possible
    * if you can "block all, and add back whats needed" then this is acceptable
    * need to look into mknod for what breaks
    * libcontainer2? [runc#1991](https://github.com/opencontainers/runc/pull/1991)
    * crosby (and mrunal) pls2give feedback :smile: !
* 

### Action

* [distribution maintainers review #45](https://github.com/opencontainers/distribution-spec/pull/45)
* mikebrown to coordinate working group for
    * use-cases and scope of listing API
    * spec (and ideally a PoC)
    * https://hackmd.io/s/BJPAUxDvV#OCI-Catalog-Listing-API---Workgroup
* vbatts to set up a time in next days for video chat to walk through this github app with Vanessa
* runc maintainers review https://github.com/opencontainers/runc/pull/1991

## March 6, 2019

### Attendees:
  - Vincent Batts
  - Phil Estes
  - Mike Brown
  - Vanessa Sochat
  - Eric Ernst
  - Atlas Kerr
  - Chris Hoge
  - Gilbert Song
  - Steve Lasker
  - Derek McGowan
  - Jimmy Zelinske
  - Eric Hotinger
  - Samuel Karp
  - Tianon
  - Josh Dolitsky

### Agenda items: 
  - [distribution-spec v1](https://github.com/opencontainers/distribution-spec/milestone/3)
  - [cgroup v2](https://github.com/opencontainers/runtime-spec/issues/1002)
  - Cleanup (heads up maintainers):
    - https://github.com/opencontainers/org/issues/3
    - https://github.com/opencontainers/runtime-spec/pull/1001
    - https://github.com/opencontainers/runc/pull/2002
    - https://github.com/opencontainers/org/pulls

#### Contribution Workflow

Discussed briefly adding a folder for proposals and meetings notes to the org repo, [issue created](https://github.com/opencontainers/org/issues/12)
and more discussion next week. 
 - [Original PR](https://github.com/opencontainers/org/pull/6) to add contributing docs to the org repo, and 
 - [Just adding Contributing Docs](https://github.com/opencontainers/org/pull/9) is the consolidated version to break apart the pull requests. 
 - [Web Preview](https://vsoch.github.io/org/) is the web preview for the pull request PR (I'll keep it updated with the add/contributing-docs PR)

#### Cgroup v2

Mostly a heads up regarding more imminent arrival of cgroup v2 in distributions. Ubuntu latest releases already providing unified mount. Fedora (2? : vbatts?) potentially switching with boot flag.

#### Distribution-spec

Discussion covering the open issues against the [v1.0.0-rc1 milestone in GitHub](https://github.com/opencontainers/distribution-spec/milestone/3). 

Specific discussion on removing references to Docker v2 schema 1 manifests (issue [#47](https://github.com/opencontainers/distribution-spec/issues/47)) and vendor-specific HTTP headers (issue [#26](https://github.com/opencontainers/distribution-spec/issues/26)).

Vincent added issue [#39](https://github.com/opencontainers/distribution-spec/pull/39) to the milestone: Dongsu's ocicert tests.

We need a proposal for the way forward on https://github.com/opencontainers/distribution-spec/issues/22
JimmiZ says that `_catalog` and search are tied together.
The clair model is registering with a registry, so new pushes to the registry trigger a webhook to call the scan.
SteveLas - correlating the listing and eventing together would be a good scenario to cover. Possibly cover the requirements of a catalog/listing API. Mike suggested starting this now, and seeing if we can land it before 1.0 ships.

[Slack Catalog Discussion](https://opencontainers.slack.com/messages/CGSAW6X0X/)

### Call notes (from IRC)

> 17:00:53          estesp | #startmeeting OCI Weekly Dev Call
> 17:00:53        collabot | Meeting started Wed Mar  6 22:00:53 2019 UTC.  The chair is estesp. Information about MeetBot at http://wiki.debian.org/MeetBot.
> 17:00:53        collabot | Useful Commands: #action #agreed #help #info #idea #link #topic.
> 17:00:53        collabot | The meeting name has been set to 'oci_weekly_dev_call'
> 17:07:53          estesp | #topic potentially have a better shared mechanism to collaborate on agenda + actions/notes
> 17:09:31          estesp | atlas: potential to use org repo to store content/weekly discussion
> 17:10:55          estesp | vanessa: shared doc during call lets people follow and focus
> 17:12:12          estesp | atlas: obvious pros/cons to various methods
> 17:13:19          estesp | vbatts: inline commenting in shared doc during call is good; but can be transcribed to markdown as summary for later (did I get that
>                          | right?)
> 17:13:59          estesp | atlas: try Google Docs next week (vanessa: or this week!)
> 17:15:31          estesp | lasker: how about hackmd.io? like shared Google docs, but saves in markdown
> 17:16:27          estesp | #link https://hackmd.io/El8Dd2xrTlCaCG59ns5cwg
> 17:18:37          estesp | #topic cgroup v2  
> 17:19:02          estesp | #link https://github.com/opencontainers/runtime-spec/issues/1002
> 17:19:59          estesp | vbatts: looking more imminent; Ubuntu already has unified mount; Fedora 2? possibly switching
> 17:24:48          estesp | #topic distribution spec v1
> 17:25:48          estesp | atlas: removing references to docker v2 schema 1 is mostly done
> 17:26:15          estesp | #link https://github.com/opencontainers/distribution-spec/milestone/3
> 17:26:52          estesp | atlas: vbatts: discussing vendor specific strings in headers
> 17:26:59          estesp | #link https://github.com/opencontainers/distribution-spec/issues/26
> 17:35:57          estesp | vbatts adding issue #39 to the milestone
> 17:36:01          estesp | #link https://github.com/opencontainers/distribution-spec/pull/39
> 17:37:43          estesp | #topic moving common content to the org project
> 17:38:01          estesp | vbatts: code of conduct and security disclosure are already moved thanks to Vanessa
> 17:38:46          estesp | #link https://github.com/opencontainers/org
> 17:40:43          estesp | vanessa: discussing the intro content PR and deploying it to a github pages site
> 17:46:23          estesp | #topic catalog/listing capabilities of registries
> 17:49:25          estesp | lasker, vbatts, atlas discussing potential for a proposal in this area
> 17:49:43          estesp | vbatts: need a proposal for a way forward on issue #22
> 17:49:48          estesp | #link https://github.com/opencontainers/distribution-spec/issues/22
> 17:59:31          estesp | #endmeeting
> 17:59:31        collabot | Meeting ended Wed Mar  6 22:59:31 2019 UTC.  Information about MeetBot at http://wiki.debian.org/MeetBot . (v 0.1.4)
> 17:59:31        collabot | Minutes:        http://ircbot.wl.linuxfoundation.org/meetings/opencontainers/2019/opencontainers.2019-03-06-22.00.html
> 17:59:3http1        collabot | Minutes (text): http://ircbot.wl.linuxfoundation.org/meetings/opencontainers/2019/opencontainers.2019-03-06-22.00.txt
> 17:59:31        collabot | Log:            ://ircbot.wl.linuxfoundation.org/meetings/opencontainers/2019/opencontainers.2019-03-06-22.00.log.html
> 
