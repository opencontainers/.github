# OCI Weekly Dev Meeting Notes Archive - April 2021 to March 2022

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

## December 9, 2021

**Recording**: (none)

### Attendees:
- Tianon
- Jason Hall (Red Hat)
- Steve Lasker (Microsoft)
- Samuel Karp (AWS)
- Mike Brown (IBM)
- Brandon Klein (SNL)
- _add yourself_

### Notes:
- No items - cancelling this week
- If folks have content for next week (Dec 16), we can meet. Or work over email and enjoy the holiday break


## December 2, 2021

**Recording**: https://youtu.be/pgUiD5QIVJU

### Attendees:
- Brandon Mitchell
- Jon Johnson
- Josh Dolitsky
- Steve Lasker
- Phil Estes
- Lachlan Evenson
- Mike Brown (IBM)
- Tianon
- Sajay Antony
- Ramkumar Chinchani (Cisco)

### Actionable Agenda Items:
- _add your items_

### Presentation/Discussion Agenda Items:
- [Sparse Index support](https://github.com/opencontainers/distribution-spec/pull/310) (Brandon)
- [Client handling of multiple matching index entries](https://github.com/opencontainers/image-spec/pull/880) (Brandon)
- [New OCI Conformance webpage](https://conformance.opencontainers.org/) (Josh)
- branching for the security release https://github.com/opencontainers/distribution-spec/pull/309 https://github.com/opencontainers/image-spec/pull/878 (vbatts)
- Conformance: should we push a `latest`
/ `main` tag for the image? (Josh)
  - Original issue: https://github.com/opencontainers/distribution-spec/issues/312
- Working group status?
- CI failures?
    - Still using quay here: https://github.com/opencontainers/image-spec/blob/083f635f2b04f7f340685a1e0c4393a0feec3679/.github/workflows/docs-and-linting.yml#L31

### Notes:

## No call on November 25

## November 18, 2021

**Recording:** : https://youtu.be/niRr9HjH4ac

### Attendees:
- Phil Estes
- Brandon Mitchell
- Mike Brown (IBM)
- Jason Hall (Red Hat)
- Tianon
- vbatts
- Jon Johnson
- Josh Dolitsky
- Rose (vmware)
- Brandon Klein
- Steve Lasker (Microsoft)
- Brian Goff (Microsoft)
- Samuel Karp
- Ramkumar Chinchani (Cisco)
- Sajay Antony (Microsoft)

### Actionable Agenda Items:
- _add your items_

### Presentation/Discussion Agenda Items:
- (vbatts) advisory discussion
- (josh) OCI Conformance updates
    - Putting together a merge posse ([mailing list convo](https://groups.google.com/a/opencontainers.org/g/dev/c/FqEy-BPgPBE/m/xDnl86cRAAAJ))
    - Removing the results page ([mailing list convo](https://groups.google.com/a/opencontainers.org/g/dev/c/b3dxfVay8ME/m/3j58_PESAAAJ))
    - Making new results page based on submissions
    - https://github.com/opencontainers/oci-conformance/pull/77
    - https://github.com/opencontainers/oci-conformance/blob/24df8c53adc15a21057f06d76ee5a524112d5c63/instructions.md#badgesmd-optional

## November 11, 2021

**Recording:** : https://youtu.be/n2F97u5-uX8

### Attendees:
- Vincent Batts
- Brandon Mitchell
- Nisha Kumar
- Jason Hall
- Samuel Karp
- Brandon Klein
- Sajay Antony
- Jon Johnson
- Steve Lasker
- Tianon

### Actionable Agenda Items:
- TODO(vb) determine the kick off for the vote proposal
- TODO(vb) group types of repos (spec, tech, gov, org?)

### Presentation/Discussion Agenda Items:
- (josh) Standardization on repo governance files / CI?
    - See https://bloodorangeio.github.io/oci-stats/
    - "6.a. The TOB is responsible for managing conflicts, violations of procedures or guidelines and any cross-project or high-level issues that cannot be resolved in the TDC for OCI Projects. The TOB shall also be responsible for adding, removing or reorganizing OCI Projects. The TOB shall not dictate or interfere with the day-to-day work of individual OCI Projects or their decisions."
    - "6.c. The TOB shall operate transparently with any discussions and mailing lists open to the community. The TOB may choose to set up a private discussion or mailing list if a situation warrants a private discussion (e.g. removing a TOB member, addressing a legal issue), but the general expectation is that the TOB’s discussions and decisions are open to the OCI Community. If a decision is made in private, the TOB must follow all quorum and voting requirements as normally required and shall be responsible for notifying the OCI Community of the decision and rationale. Any private meeting of the TOB shall also require a representative from The Linux Foundation to ensure this option is not being abused."
    - Source for site: https://github.com/bloodorangeio/oci-stats
- (josh) Can we get some volunteers for submitting OCI conformance?
    - For distribution-spec v1.0.0 ... I will help you! 
    - Here are [the instructions](https://github.com/opencontainers/oci-conformance/blob/main/instructions.md)
- (sajay) Discuss next steps for extensions PR. 

## November 4, 2021

**Recording:** : https://youtu.be/g7S1hl0HVts

### Attendees:
- Steve Lasker (Microsoft)
- Brandon Klein (SNL)
- Tianon
- Ramkumar Chinchani (Cisco)
- Jason Hall (Red Hat)
- Josh

### Actionable Agenda Items:
- _add your items_

### Presentation/Discussion Agenda Items:
-  Review and discuss about the [distribution extensions API design](https://hackmd.io/nSQoPlZsST-n2jyRJLPDng)
    -  Sample code: https://github.com/distribution/distribution/pull/3522/files

### Notes:

## October 28, 2021

**Recording:** https://youtu.be/rie3-fmet_8

### Attendees:
- Tianon
- Phil Estes (AWS)
- Brandon Mitchell
- Jason Hall (Red Hat)
- John Muth
- Samuel Karp (AWS)
- Brandon Klein (SNL)
- Sajay Antony (Microsoft)
- Vincent Batts
- Mike Brown (IBM)
- Ramkumar Chinchani (Cisco)
- Sargun Dhillon

### Actionable Agenda Items:
- _add your items_

### Presentation/Discussion Agenda Items:
- (vb) governance things

### Notes:
- bringing the reference Types to vote
- https://github.com/opencontainers/tob/blob/main/CHARTER.md
    - but should each repo have its own GOVERANCE
    - https://github.com/opencontainers/tob/blob/main/CHARTER.md#5-technical-developer-community
    - > c. The maintainers and contributors shall set the technical direction of the OCI Projects, with minimal interference by the Technical Oversight Board;
- (sajay) extension PoC
    - https://github.com/opencontainers/distribution-spec/pull/111
    - https://github.com/distribution/distribution/issues/3512
    - https://github.com/distribution/distribution/pull/3522

## October 21, 2021

**Recording:** https://www.youtube.com/watch?v=-tHfL7vH_J4

### Attendees:
- Brandon Mitchell
- Steve Lasker (Microsoft)
- Josh Dolitsky
- Jason Hall (Red Hat)
- Vincent Batts
- Sargun Dhillon
- Samuel Karp (AWS)
- Mike Brown (IBM)
- Tianon
- Phil Estes (AWS)
- Sajay Antony (Microsoft)

### Actionable Agenda Items:
- _add your items_

### Presentation/Discussion Agenda Items:
- Is OCI-Artifacts being archived? https://github.com/opencontainers/artifacts/pull/47 (Brandon)
- Next steps for #251 [Document Conditional Requests](https://github.com/opencontainers/distribution-spec/pull/251/) (Brandon)
- New release of distribution spec? (Sargun)
- Reference Types WG proposal updated: https://github.com/opencontainers/tob/issues/96 🎉 (Jason)
- Content-encoding: https://github.com/opencontainers/distribution-spec/issues/301
- KubeCon recap / conversations / interest? (Jason)

### Notes:
- opencontainers/artifacts repo - status of this repo seems confusing with efforts
    - Mike/Steve will make a PR to the root readme of artifacts to discuss the current repo enables existing released specs. With links to the WG and oras-artifacs work for newly proposed topics that we'd like to see merged into OCI. Done: https://github.com/opencontainers/artifacts#project-status
- opencontainers/distribution-spec#251
    - Needs a quick scoping of impact on popular usages (i.e. distribution/distribution + S3, where multiplate r/w to S3 can not gaurantee consistency)
    - Looking for distribution to provide an example implementation with S3 backing and scaled with multiple instances.
- distribution-spec release?
    - FYI: https://github.com/opencontainers/distribution-spec/compare/v1.0.0...main
    - https://github.com/opencontainers/runtime-spec/blob/master/RELEASES.md
    - Historicaly haven't done RC releases for small changes
    - No concept of a pre-releases so far
    - Should/could we treat main as a work in progress, for the next release? The root readme would state this, with links to the released specs.
    - https://github.com/opencontainers/oci-conformance/issues/76
- Reference Type WG
    - (estesp) basically it's time for a TOB vote
- content-encoding
    - general +1 from jasonH and vbatts
- what happens when sha256 breaks
    - this _will_ happen
    - what's the playbook
    - (vb) i think existing objects stay addressable. Regenerating the world, could be possible, but would break existing digest identities
    - (jasonH) so that we're not just doing this again when sha512 gets broken, we should consider extensibility here
    - (vb) .. like a multihash list? (thinking more about this, those additional hash calculations would likely happen _after_ the initial push of an image, and this may be a nice case for attaching a reference-type metadata and even an extention, to expose the additional hash:digest to find the _same_ object on a registry (e.g. sha256:deadbeef and sha512:cabbabbe are the same blob))
    - mixing hashes behaviour _should_ be ratified in the specs
    - reference: https://github.com/opencontainers/image-spec/blob/main/descriptor.md#digests

## October 7, 2021
**Recording:** https://www.youtube.com/watch?v=7dbl4VJCxII

### Attendees:
- Brandon Mitchell
- Nisha Kumar
- Rose Judge
- Vincent Batts
- Jason Hall
- Mike (IBM)
- Tianon
- Josh Dolitsky
- Ramkumar Chinchani (Cisco)
- ASP (joined at :30)

### Actionable Agenda Items:
- [Conflicting image index and image layout?](https://github.com/opencontainers/image-spec/issues/870) (Nisha)

### Presentation/Discussion Agenda Items:
- Extension proposal - https://github.com/opencontainers/distribution-spec/pull/111 (Sajay)
- Summarize conversation on DAG-CAS structure with references (Nisha/Brandon)
- Specs on the website! -https://github.com/opencontainers/opencontainers.org/pull/58 (Josh)

### Notes:



## September 30, 2021 

### OCI Summit Virtual and In-Person

### Notes:

Agenda and attendance in separate HackMD pad: 
https://hackmd.io/FkqLzCjITTqeP2WwrWnesg 


## September 29, 2021

**Recording:** https://www.youtube.com/watch?v=NFB08XSNx5A

### Attendees:
 - Tianon
 - Rose Judge
 - Brandon Mitchell
 - Jon Johnson
 - Nisha Kumar
 - Steve Lasker
 - Brandon Klein (SNL)

### Presentation/Discussion Agenda Items:
- General OCI meeting canceled due to OCI summit on 2021-09-30, however, a smaller group got together to continue the "purl" OCI identifier discussion


## September 22, 2021
**Recording:** https://www.youtube.com/watch?v=XY30PzcSgl8

### Attendees:
- Tianon
- Aidan Delaney
- Jason Hall (Red Hat)
- Steve Lasker (Microsoft)
- Brandon Mitchell
- Brandon Lum (IBM)
- Phil Estes (AWS)
- Josh Dolitsky
- Jon Johnson
- Rose Judge
- Brian Goff
- vbatts
- Mike Brown (IBM)
- Nisha Kumar
- Samuel Karp (AWS)
- Sargun
- Amye SP
- Ramkumar Chinchani (Cisco)
- Brandon Klein (SNL)
- _add yourself_

### Actionable Agenda Items:
- [image-spec maintainers maintenance](https://github.com/opencontainers/image-spec/issues/834#issuecomment-923064715) (Jason)
- Consensus for `oci-artifact` as purl package type. More details here: https://github.com/package-url/purl-spec/pull/123 (Rose)
- OCI Summit next week, Thurs Sept 30, register [here](https://events.linuxfoundation.org/open-source-summit-north-america/features/co-located-events/#open-containers-summit) (free!), agenda [here](https://hackmd.io/FkqLzCjITTqeP2WwrWnesg) (Jason)
- Note to cancel next week's call in favor of Thursday, Sept 30 OCI Summit (ASP)
- add topics!

### Presentation/Discussion Agenda Items:
- _add your items_

### Notes:
* There has been some movement on image-spec/issues/834 to update maintainers.  Is this sufficient?
    - More people are now involved since raising this issue, this will lead to new maintainers standing up
    - Current issue could be closed
    - Need to figure out why current maintainers didn't accept the current suggested additions
    - Can't approve new maintainers without involvement of absent maintainers -- blocked
    - Is there a maintainer ladder in the TOB?
        - loose definition -- leading discussion, PRs
    - Can we write down paths to maintainership?
        - eg: https://github.com/cncf/tag-security/blob/main/governance/tech-lead-proposal-process.md#technical-lead-nomination-requirements
* How do we have a hybrid in-person/virtual discussion
    - Current Zoom room
    - Speakerphone in the room
    - Need a discussion framework to enable hybrid participation
    - Whiteboard sessions need a camera pointed at the whiteboard
* `oci-artifact` purl type
    - Can't remove existing Docker type
    - Debate over `oci-artifact` in URI
        - The term artifacts has different meanings in OCI contexts
        - purl is a loose specification, URI needs to reliably locate the thing
    - A call will be scheduled to discuss this 

## September 15, 2021
**Recording:** https://www.youtube.com/watch?v=8djTrZnHwtk

### Attendees:
- Mike Brown (IBM)
- Steve Lasker (Microsoft)
- Jon Johnson
- Aidan Delaney
- Brandon Lum (IBM)
- Brandon Mitchell
- ASP
- Phil Estes (AWS)
- Ram Chinchani (Cisco)
- Tianon
- Josh Dolitsky

### Actionable Agenda Items:
- Topics/Agenda for OCI Summit (Thursday, September 30 | 9:00 AM – 5:00 PM)

### Presentation/Discussion Agenda Items:
- Discussion on Encryption Mediatype and references to other mediatypes and how to consume them (Brandon Lum)
  - Runtime Support
      - Default in Containerd
      - Default in cri-o 
  - Registry Support
      - [Quay OCI Support](https://issues.redhat.com/browse/PROJQUAY-1032)
      - Docker Distribution Support (by default)
  - Spec issues:
      - [Add mediatype for encrypted layers](https://github.com/opencontainers/artifacts/pull/15)
      - [Historical issue on image-spec](https://github.com/opencontainers/image-spec/pull/775)
  - Use-cases
      - [katacontainers confidential computing](https://github.com/kata-containers/kata-containers/issues/1332)
      - [IBMCloud enc. image run](https://www.ibm.com/cloud/blog/deploy-containers-from-encrypted-images-in-red-hat-openshift-on-ibm-cloud-clusters)

### Notes:

- Topics for the OCI Summit were solicted
    - [Please register](https://events.linuxfoundation.org/open-source-summit-north-america/features/co-located-events/#open-container-summit)
    - Structured or ad-hoc?
    - Structured may make more sense considering more virtual attendance
    - Pressing topics: 
        -  [Artifacts spec](https://github.com/oras-project/artifacts-spec/releases/tag/1.0.0-draft.1)
        -  OCI 2.0
        -  Confidential Computing
              - Should we have some sort of "keynote speaker" to give context what the space is, not just what certain projects/products are doing? It might help set the context on what projects are uniquely doing x, while multiples are doing the same, and how they might work together to fill the gaps.
        -  Use cases for OCI 
    -  Show and Tell
        -  What are people working on that we haven't discussed in awhile? 
    -  Issue cleanup + repo grooming
    - AI: Review new HackMD: https://hackmd.io/FkqLzCjITTqeP2WwrWnesg 
- PR submitted to add encrypted mime type suffix
    - Noted that there is some disagreement on the number of possible suffixes
    - Image spec only requires support for a fixed list of 4 media types on layers, typically should be ignored by registries, but spec is not clear on "MUST" between clients and registries
    - Possible state explosion between non-distributable layers and encryption mime type suffixes
    - Quay wants to distinguish between blobs based on media type
    - Idea to PR removal/deprecation of non-distributable layers from spec
    - It seems like there is a proposal in the IANA - https://tools.ietf.org/html/rfc8188 *IETF

## September 8, 2021
**Recording:** https://www.youtube.com/watch?v=2nIpNAaXO8A

### Attendees:
- Steve Lasker (Microsoft)
- Phil Estes (AWS)
- Brandon Lum (IBM)
- Aidan Delaney
- Mark Peek (VMware)
- Jason Hall (Red Hat)
- Tianon
- Jon Johnson
- Vanessa Sochat (LLNL)
- Brandon Mitchell
- Ramkumar Chinchani (Cisco)
- Mike Brown (IBM)
- Samuel Karp (AWS)
- Rose Judge (VMware)

### Actionable Agenda Items:
- _add your items_

### Presentation/Discussion Agenda Items:
- [Proposal]( https://hackmd.io/hZl1yeYyQC6duK-8qhtVPg) for adding `oci-artifact` to the [pURL specification](https://github.com/package-url/purl-spec/blob/master/PURL-SPECIFICATION.rst) (Nisha, Rose, Steve)

### Notes:

## September 1, 2021

Cancelled - no agenda items for the week

## August 25, 2021

Cancelled - no agenda items for the week

## August 18, 2021
**Recording:** https://www.youtube.com/watch?v=ikM91XicdMM

### Attendees:
- Brandon Klein (SNL)
- Steve Lasker (Microsoft)
- Brandon Mitchell
- Jon Johnson
- Vanessa Sochat (LLNL)
- Jason Hall (Red Hat)
- Mike Brown (IBM)
- Phil Estes (AWS)
- Michael Brown (AWS)
- Tianon
- Mark Peek (VMware)
- Sajay Antony (Microsoft)
- _add yourself_

### Actionable Agenda Items:
- Review https://github.com/opencontainers/image-spec/pull/826 (Jon)
  - no image-spec maintainers present :(

### Presentation/Discussion Agenda Items:
- Anyone know what's up with helm using registries? (Jon)
    - Seems like they want something from us?
    - https://github.com/helm/helm/issues/9188#issuecomment-866118833
    - https://github.com/opencontainers/artifacts/issues/23
- Registry support for different media types <https://github.com/moby/buildkit/issues/2251>

### Notes:
- [Helm questions on release of an artifact](https://github.com/opencontainers/artifacts/issues/23)
- [Registry analysis for which supports OCI Artifacts](https://github.com/moby/buildkit/issues/2251)
- Should there be separate repos under opencontainers for language specific implementations of each spec.

## August 11, 2021
**Recording:** https://www.youtube.com/watch?v=Q6DZKu4ZzoY

### Attendees:
- Nisha
- Jason Hall (Red Hat)
- Brandon Klein (SNL)
- Brandon Mitchell
- Steve Lasker (Microsoft)
- Samuel Karp (AWS)
- Vanessa Sochat (LLNL)
- Hank Donnay (Quay)
- Lachlan Evenson (Microsoft)
- Tianon
- Mark Peek (VMware)
- Jon
- Michael Brown (AWS)
- Ramkumar Chinchani (Cisco)

### Actionable Agenda Items:
- 

### Presentation/Discussion Agenda Items:
- https://github.com/opencontainers/image-spec/pull/826 (Jon)
    - should this proposal go through the new WG process being used for references?
    - does `data` make registries incapable of blocking/deleting blobs by `mediaType`?
- https://github.com/opencontainers/distribution-spec/pull/293 (Jason)

### Notes:

## August 4, 2021
**Recording:** https://www.youtube.com/watch?v=Oa3gbf0Ivo4

### Attendees:
- Brandon Mitchell
- Vanessa Sochat (LLNL)
- Nisha Kumar
- Aidan Delaney
- Ramkumar Chinchani (Cisco)
- Phil Estes (AWS)
- Tianon
- Jon Johnson
- Amye SP
- Samuel Karp (AWS)
- Mike Brown (IBM)
- Michael Brown (AWS)
- Jason Hall

### Actionable Agenda Items:
- [Define a minimum required manifest size](https://github.com/opencontainers/distribution-spec/issues/260)
- https://github.com/imjasonh/datatest testing existing registry support for [`data` field](https://github.com/opencontainers/image-spec/pull/826) -- many registries already support it (see manifest size limit recommendations 😬)

### Presentation/Discussion Agenda Items:
- _add your items_
- Open Container Initiative Summit at OSSNA - September 30th [ASP]
    - Do we want a CFP?
    - <https://events.linuxfoundation.org/open-source-summit-north-america/>
    - No, no no, we would like whiteboards instead
        - Virtual attendees expected 

### Notes:

* Current state of distribution-spec/issues/260 discussion is that the spec would establish a minimum bound on a suggested a maximum size
    - min size of 4Mb floated, should return a 413 for manifest that is too large
* Data field is supported by all tested implementations image-spec/pull/826
* TOB WG status [tob/pull/99](https://github.com/opencontainers/tob/pull/99) is 6 out of 9 LGTMs
    - may be some clarifications that still need to be provided
    - possibly in followup PRs
* What WGs could we spin off right now?
    - we can get things rolling now
    - [tob/issues/96](https://github.com/opencontainers/tob/issues/96) has a rough outline of how to propose a WG
* Jekyll templates will be followed up next week 

## July 28, 2021
**Recording:** https://www.youtube.com/watch?v=eqdKWVbEeMU

### Attendees:

- Vanessa Sochat (LLNL)
- Aidan Delaney
- Jason Hall (Red Hat)
- Brandon Mitchell
- Michael Brown (AWS)
- Brian Goff (MSFT)
- Tianon
- Adrian Mouat (Container Solutions)
- Phil Estes (AWS)
- Jon Johnson
- Mike Brown (IBM)
- Brandon Klein (SNL)

### Actionable Agenda Items:

- Next steps RFC template (@vsoch, I can only stay 20 minutes)
- other meeting times (Jason Hall)
  - Full results here: https://doodle.com/poll/mg8sbyzt2b4qdf6g (17 total voters)
  - The highest vote total was actually for an hour later on Wednesdays (12 votes), which would be 6am APAC / midnight EU
  - The earliest time (comparatively more EU/APAC friendly) with 10+ votes was Tuesday 11-12 EST (8am PST, 11pm APAC, 5pm EU) -- earlier than that had very few votes, presumably from west-coasters
  - The voteable slots were pretty US-centric to begin with, if someone in EU/APAC wants to lead the meeting in friendlier times and if there's support for it, I think we should consider it.


### Presentation/Discussion Agenda Items:

### Notes:

- WG PR has been approved, but has pending comments (https://github.com/opencontainers/tob/pull/99)

## July 21, 2021
**Recording:** https://www.youtube.com/watch?v=crg1k8LAkGA

### Attendees:
- Steve Lasker (Microsoft)
- Tianon
- Brandon Mitchell
- Lachlan Evenson (Microsoft)
- Bracken Dawson (IBM)
- Samuel Karp (AWS)
- vbatts
- Derek McGowan
- Mike Brown (IBM)
- Josh Dolitsky
- Mark Peek (VMware)
- Ramkumar Chinchani (Cisco)

### Actionable Agenda Items:
- _add your items_

### Presentation/Discussion Agenda Items:
- Next steps for working groups, and how to proceed with reference types (Steve)
    - https://github.com/opencontainers/tob/pull/99 is updated, please review (Amye)
    - 1) need the working group(s) charter closed (vote asap pls.)
    - 2) Some set of working groups being discussed regarding artifacts:
        - a) working group for splitting up oci image spec into generic CAS spec and image spec
        - b) working group for iterating #29 artifacts spec proposal.. (no dependency on a)
        - c) artifacts spec working group to make #29 concrete on top of CAS.. (depends on a) feed the use cases for the CAS spec etc.
- Next steps for RFC docs deployment

- _add your items_



- https://github.com/opencontainers/tob/issues/96
- https://github.com/opencontainers/tob/pull/99
- Next steps for the Artifacts work:
    - OCI will vote on TOB#99, then a modified version of #96 This will take a few days, possibly a few weeks
    - To avoid undue time constraints on rushing that process, an artifacts-spec repo will be created, with comments in the readme.md that this is intended to be donated to OCI as the working group process is defined..
    - This unblocks the pressing need to make collaborative progress in neutral governance location, while the working group process takes the proper steps.
    - The artifacts-spec, while outside of OCI will use mediaTypes and paths that don't conflict with OCI, so there's no concern of branding or forking. As long as we can resolve the working group and repo for tbd-artifacts-spec or some other tbd-cas-spec before Azure, Docker, AWS and others need to ship customer support, we can rename the strings to be OCI, avoiding future migration issues.

## July 14, 2021
**Recording:** https://www.youtube.com/watch?v=4n3XeGGQ1_k

### Attendees:
- Bracken Dawson (IBM)
- Tianon
- Brandon Klein (Sandia National Labs)
- Brandon Mitchell
- João Pereira (GitLab)
- Aidan Delaney
- Steve Lasker (Microsoft)
- Nisha Kumar (VMware)
- Vanessa Sochat (LLNL)
- Brian Goff (Microsoft)
- Derek McGowan
- Jon Johnson
- ASP
- _add yourself_

### Actionable Agenda Items:
- [Doodle](https://doodle.com/poll/mg8sbyzt2b4qdf6g) to collect possible new times for this meeting

### Presentation/Discussion Agenda Items:
- Continue discussion from 2021-07-07 on what is valid for an index entry (manifests only or allow blobs too) (Brandon)
- Next steps for working groups, and how to proceed with reference types (Steve)
    - https://github.com/opencontainers/tob/pull/99 is updated, please review (ASP)
- (if time) next steps for RFC docs deployment!
- _add your items_

### Notes:
- Doodle poll - please promote to anyone who might be interested to gather the votes.
    - Beleive alternatiing weeks are better than alternating 3 month blocks to avoid loosing people
- Deletion/Lifecycle management: Agreement to capture the different registry implementations. (Steve to start the discussion for where)
- Open an issue on distribution for defining "what is a manifest". (Steve)

## July 9, 2021

### Attendees:
- Vincent Batts
- Tianon
- Jon Johnson
- dims
- Steve Lasker
- Aidan Delaney
- Tejaswini Duggaraju (Microsoft)
- _add yourself_

### Actionable Agenda Items:
- image-spec grooming

### Notes:
- Maintainers got rights to the repo
- set up the github CODEOWNERS approval process
- removed pullapprove from the approval process
- deleted pullapprove and travis webhooks
- renamed `master` branch to `main`
    - users that see: `Your configuration specifies to merge with the ref 'refs/heads/master' from the remote, but no such ref was fetched.`
    - will need to run:
      ```shell=
      git branch -m master main
      git fetch origin
      git branch -u origin/main main
      git remote set-head origin -a
      ```
- https://github.com/opencontainers/image-spec/pull/863
- https://github.com/opencontainers/image-spec/pull/775#issuecomment-877311438
- annotation discussion
- `go.mod` semantics

Post call: continued to close, merge, or mark duplicate issues and PRs

## July 7, 2021
**Recording:** https://www.youtube.com/watch?v=GToyLd7u7ug

### Attendees:
- Vincent Batts
- Steve Lasker (Microsoft)
- Brandon Mitchell
- Tianon
- Samuel Karp (AWS)
- Josh Dolitsky
- ASP (OCI)
- Sajay Antony (Microsoft)

### Actionable Agenda Items:
- _add your items_

### Presentation/Discussion Agenda Items:
- _add your items_

### Notes:
- https://github.com/distribution/distribution/issues/3452
- https://github.com/opencontainers/image-spec/blob/master/image-index.md#image-index-property-descriptions 
    - https://github.com/opencontainers/image-spec/blob/master/image-layout.md#index-example has examples of non-OCI mediatypes listed
    - a differentiation between manifest and blob is that the API to upload is two different paths
    - TODO discuss: clarifying the wording of `manifests` is a list of descriptors; rather than pointing to the OCI image-manifest doc, instead a few points of what the nature of a "manifest" even is; and point to the distribution API difference
    - and clarify the "unknown to the implementation MUST be ignored" to be "MAY", and whether this is client-side ignored, or whether the server-side can reject, or garbage-collect, etc.

## June 30, 2021
**Recording:** https://www.youtube.com/watch?v=EYgPOh6yiII

### Attendees:
- Steve Lasker (Microsoft)
- Vincent Batts
- Vanessa Sochat (LLNL)
- Mike Brown (IBM)
- Aidan Delaney
- Ramkumar Chinchani (Cisco)
- Brandon Mitchell
- Jon Johnson
- Samuel Karp (AWS)
- Jonathan Boulle
- Mark Peek (VMware)
- Tianon (InfoSiftr)
- Stephen Day

### Actionable Agenda Items:
- _add your items_

### Presentation/Discussion Agenda Items:
- vsoch on RFC-like OCI spec formatting: https://vsoch.github.io/rfc-jekyll/
    - https://github.com/vsoch/rfc-jekyll
- vbatts - image-spec grooming
- jason hall: https://github.com/opencontainers/image-spec/pull/822
- jason hall: can this meeting be an hour earlier?

### Notes:

- TODO doodle to maybe move the call an hour or so earlier
- RFC layout looks great. General +1 from folks
    - we'll get a repo setup
    - vsoch mentioned versioning in the path
    - CODEOWNERS
    - And CNAME like specs.opencontainers.org/
- image-spec/pull/822
    - general agreement on the use-case
    - (stephenday) remember this can get complicated. Same as we've discussed in the past
    - can remove the ref component of image.base.ref.name (e.g. org.opencontainers.image.base.name)
    - This doesn't address the complexity of the graph (multi-stage builds; only choosing the _last_ `FROM`)
- potential issue with annotations, many users confuse them with labels and tooling doesn't exist in Docker to define annotations: https://github.com/opencontainers/image-spec/issues/833
- TODO work with amye/cra to remove pullapprove from image-spec, and enable the CODEOWNERS feature for 2 maintainers

## June 23, 2021 - NO [OFFICIAL] CALL
**Recording:** https://www.youtube.com/watch?v=IzDv95WGsno

### Attendees:
- Vincent Batts
- Jimmy Zelinskie
- Josh Dolitsky
- Mike Brown
- Brandon Klein (Sandia National Labs)

### Actionable Agenda Items:
- _add your items_

### Presentation/Discussion Agenda Items:
- _add your items_

### Notes:

Groomed distribution-spec PRs, issues, and began cleanup: Travis -> Github Actions; remove pullapprove; add CODE_OWNERS

## June 16, 2021
**Recording:** https://www.youtube.com/watch?v=mDYwMEg9CSo

### Attendees:
- Jon Johnson
- Brandon Klein (Sandia National Labs)
- Brandon Mitchell
- Tianon
- Nisha Kumar (VMware)
- Vanessa Sochat (Lawrence Livermore National Lab)
- Sargun Dhillon (Netflix)
- Michael Brown (AWS)
- Mike Brown (IBM)
- Adrian Mouat (Container Solutions)
- Sajay Antony (Microsoft)
- Phil Estes (AWS)
- Sven Dowideit (CSIRO)
- Derek McGowan
- Samuel Karp (AWS)

### Actionable Agenda Items:

### Presentation/Discussion Agenda Items:
 - Finish discussion around [Allow for automatic content discovery for cross-mounting blobs #275](https://github.com/opencontainers/distribution-spec/pull/275). Reference implementation has been provided.
 - (vb) image-spec issue/PR grooming

### Notes:


## June 9, 2021
**Recording:** https://www.youtube.com/watch?v=3a1ie3cOMb0

### Attendees:
- Jason Hall (Red Hat)
- Steve Lasker (Microsoft)
- Vanessa Sochat (Lawrence Livermore National Lab)
- Brandon Klein (Sandia National Labs)
- Aidan Delaney
- Phil Estes (AWS)
- Lachlan Evenson (Microsoft)
- Brandon Mitchell
- Michael Brown (AWS)
- Jon Johnson
- Ken Brooks (JPMC)
- Vincent Batts
- ASP (first half only)
- Samuel Karp (AWS)
- Josh Dolitsky
- Mike Brown (IBM)
- Stephen Walli (Microsoft)
- Sven Dowideit (CSIRO)
- Nisha Kumar (VMware)
- Tianon
- _add yourself_

### Actionable Agenda Items:
- vb - send an invite to dev@ for an image-spec grooming

### Presentation/Discussion Agenda Items:
- image-spec status (Dan Lorenc)
    - is it frozen? what constitutes a backwards compatible minor version change?
    - is https://github.com/opencontainers/image-spec/pull/828 worth pursuing?
- Status of all the manifest proposals? (Nisha)
    - What does the community need to take into account when proposing manifest changes?
    - https://github.com/opencontainers/artifacts/pull/29
    - https://github.com/opencontainers/artifacts/pull/37
    - https://github.com/opencontainers/image-spec/issues/827
    - https://github.com/opencontainers/image-spec/issues/822 🙏
    - Miro board link: https://miro.com/app/board/o9J_lAw_TsQ=/
        - Note: Miro requires you to create an account. I can instead share a screenshot if needed.
- Any further feedback on https://github.com/opencontainers/tob/pull/99
    - Yes, Phil Estes is still trapped in a house move and needs to review 
- OCI Summit? (Josh)

### Notes:
- breath fire into the image-spec, so that proposals, working-groups, or individual PRs can be confidently discussed without FUD
- ++ the diagram from Nisha. Perhaps we need a place/doc to track the high level proposals that are in play, where they're being discussed, and how they relate
    - vsochat - something like an RFC, which lends to tracking diagrams, and links to related RFC's
- josh - seeing the useful discussion in these weekly's, and then the hour is over, I think we need an event
    - vb - we have precedent of this, when we met at the IBM office in SFO and had long ddiscussions and whiteboarding, and decision making.
    - vb - and hopefully some place on the eastcoast, like Asheville NC, is a good spot for folks ;-)

## June 2, 2021 is CANCELLED 

### Attendees:
- _add yourself_

### Actionable Agenda Items:
- _add your items_

### Presentation/Discussion Agenda Items:
- _add your items_

### Notes:

## May 26, 2021
**Recording:** https://www.youtube.com/watch?v=yrsTAZ3ISv4

### Attendees:
- Steve Lasker (Microsoft)
- Brandon Mitchell
- ASP (OCI)
- Nisha Kumar (VMware)
- Vanessa Sochat (Lawrence Livermore National Lab)
- Brandon Klein (Sandia National Labs)
- Josh Dolitsky
- Aidan Delaney
- Shane Canon (Lawrence Berkeley National Lab/NERSC)
- Ramkumar Chinchani
- Samuel Karp (AWS)
- Bo Liu (Alibaba Cloud)
- Mike Brown (IBM)
- Derek McGowan
- Sven Dowideit (CSIRO)
- Tianon


### Actionable Agenda Items:
- _add your items_

### Presentation/Discussion Agenda Items:
- An HPC Working Group? (Vanessa)
- Status of all the manifest proposals? (Nisha)
    - https://github.com/opencontainers/artifacts/pull/29
    - https://github.com/opencontainers/artifacts/pull/37
    - https://github.com/opencontainers/image-spec/issues/827
- Feedback on the WG proposal?
### Notes:
- HPC Working Group
  - https://docs.google.com/document/d/1ZKMeEkgW_h8aDM-xwbDx9Iw7dMK6Bwe92qhjm9CFt4Q/edit
  - [WG proposal- TOB #99](https://github.com/opencontainers/tob/pull/99)
  - Discussing whether this falls under OCI or CNCF, recommend gathering the people first, and it will likely span both sides
  - TAG=Technical Advisory Group
- [WH directive](https://www.whitehouse.gov/briefing-room/presidential-actions/2021/05/12/executive-order-on-improving-the-nations-cybersecurity/)

## May 19, 2021
**Recording:** https://www.youtube.com/watch?v=8wmbYjvwnLk

### Attendees:
- Mike Brown (IBM)
- Brandon Klein (Sandia National Labs)
- Phil Estes (AWS)
- Brandon Mitchell
- Aidan Delaney
- Tianon
- Steve Lasker (Microsoft)
- ASP (OCI)
- Vanessa Sochat (Lawrence Livermore National Lab)
- Adrian Mouat (Container Solutions)
- Brian Goff (Microsoft)

### Actionable Agenda Items:

- [Jon] https://github.com/opencontainers/image-spec/pull/826
    - Review and/or actionable feedback
- [Jason; can't attend] https://github.com/opencontainers/image-spec/pull/822 to add base image annotations -- needs another approver please 🥺🙏

### Presentation/Discussion Agenda Items:
- _add your items_
- Show and Tell

### Notes:
- Phil - [mention of the TOB Working Group PR](https://github.com/opencontainers/tob/pull/99)

## May 12, 2021
**Recording:** https://www.youtube.com/watch?v=9IDkKIR3Odo

### Attendees:
- _add yourself_
- Larry Cable (Oracle)
- Steve Lasker (Microsoft)
- Brandon Klein (Sandia National Labs)
- Aidan Delaney
- Mark Peek (VMware)
- Tianon
- Mike Brown (IBM)
- Phil Estes (AWS)
- Samuel Karp (AWS)
- Adrian Mouat (Container Solutions)
- Bo Liu(Alibaba cloud)
- Brandon Mitchell

### Actionable Agenda Items:
- _add your items_
### Presentation/Discussion Agenda Items:
- _add your items_
- discuss [portable mechanism for processes within container to obtain their image and container ids #1105](https://github.com/opencontainers/runtime-spec/issues/1105) (Larry Cable (Oracle))


### Notes:
- Would be nice to have a generic metadata service like functionality for containers, mounting the container config (image id, container id, labels, etc) in the container as a tmpfs file (Brandon Mitchell).
- Higher level tooling like K8s has some functionality, but doesn't help when containers are run outside of K8s.
- Need to avoid any security concerns of exposing host data into the container (host name and ip, should not be exposed).
- <https://lwn.net/Articles/808399/>
- <https://lkml.org/lkml/2021/1/12/818>
- <https://github.com/containerd/containerd/blob/master/pkg/cri/server/container_status.go#L106-L137>

## May 5, 2021
**Recording:** https://www.youtube.com/watch?v=umJ-mCX8Qjk

### Attendees:
- Tianon
- Steve Lasker (Microsoft)
- Nisha Kumar
- Brandon Mitchell
- Brandon Klein (Sandia National Labs)
- Aidan Delaney
- Phil Estes (AWS)
- Mark Peek (VMware)
- Mike Brown (IBM)
- Josh Dolitsky
- Brian Goff (Microsoft)
- Jon Johnson
- Stephen Day
-  - _add yourself_
 
### Actionable Agenda Items:
- _add your items_

### Presentation / Discussion Agenda Items:
- [Deduplicate uploads](https://github.com/opencontainers/distribution-spec/issues/236) (Sargun)
- Cross-origin mounting, if we have time (Jon)


### Notes:
- Jon: just relax the cross-repo mounting language to make `from` an optional hint
    - Registries can optionally allow mounting from anywhere, if they require a `from`, they just return 202
    - If registries support non-`from` mounting, return a `201` and auto-mount the blob if it exists (otherwise 202)
    - Clients could drop HEAD requests and instead use `POST /v2/.../blobs/?mount=<digest>` (or do both)

## April 28, 2021 - NO CALL
Cancelled

## April 21, 2021 - NO CALL

Cancelled

## April 14, 2021
**Recording:** https://www.youtube.com/watch?v=koMTAythSK8

### Attendees:
- Chris Aniszczyk (LF)
- Vincent Batts
- Phil Estes (AWS)
- Steve Lasker (Microsoft)
- Brandon Klein (Sandia National Labs)
- Mark Peek (VMware)
- Tianon
- Josh Dolitsky
- Adrian Mouat (Container Solutions)
- Samuel Karp (AWS)
- Mike Brown (IBM)
- Sargun Dhillon (Netflix)

### Actionable Agenda Items:
- _add your items_

### Presentation/Discussion Agenda Items:
- Reminder: OCI IP Release Notice Policy (Chris)
    - https://opencontainers.org/release-notices/overview/
    - Note: for distribution spec v1.0
- Maintainer activity audit update (Chris/Amye)
    - https://github.com/opencontainers/tob/issues/95
- Next steps on maintainer voting (Chris/Amye)
    - image-spec voting: https://github.com/opencontainers/image-spec/issues/838
    - distribution-spec voting: https://github.com/opencontainers/distribution-spec/issues/265
- Working Groups/Streams (Phil) - [draft proposal](https://hackmd.io/WkNDyrYbRceswOICGxrHfA)
- New repo for CI images (Josh)
    - https://github.com/opencontainers/container-images

### Notes:
- What are backward-compatible changes?
    - Look at [kube](https://github.com/kubernetes/community/blob/master/contributors/devel/sig-architecture/api_changes.md) and [go](https://golang.org/doc/go1compat)?

## April 7, 2021 - NO CALL

- Cancelled