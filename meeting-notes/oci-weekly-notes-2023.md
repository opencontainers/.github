# OCI Weekly Dev Meeting Notes Archive - 2023

## December 21, 2023

**Recording**: https://youtu.be/4u5QR8njNqQ

### Attendees:
- Marcin Franczyk
- Brandon Mitchell
- Samuel Karp
- Sajay Antony
- Josh Dolitsky
- _add yourself_

### Note Taker:
- _add note taker_

### Actionable Agenda Items:
- TOB Election for 2024 is open
  - <https://github.com/opencontainers/tob/issues/134>
- Cancel meeting on the 28th.
- _add your items_

### Presentation/Discussion Agenda Items:
- _add your items_

### Notes:
- Discussed need for a PR when the subject is defined but artifactType is missing:
  - <https://github.com/opencontainers/distribution-spec/issues/458>
- _add your notes_

## December 14, 2023

**Recording**: https://youtu.be/RCpg_bGU8yE

### Attendees:
- Jason Hall
- Jon Johnson
- Brandon Mitchell
- Derek McGowan
- David Dooling
- John Kjell
- Joseph Ferguson
- Josh Dolitsky
- Sajay Antony
- Ramkumar Chinchani
- Toddy
- Tianon
- Michael Brown
- Brandon Ha
- _add yourself_

### Note Taker:
- _add note taker_

### Actionable Agenda Items:
- TOB Election for 2024 is open
  - <https://github.com/opencontainers/tob/issues/134>
- FreeBSD WG
  - <https://github.com/opencontainers/tob/pull/133>

### Presentation/Discussion Agenda Items:
- Status on "Allow registries to reject missing subject?"
  - <https://github.com/opencontainers/distribution-spec/issues/459>
- Removing scenario were referrers are accepted but not included in referrers API:
  - <https://github.com/opencontainers/distribution-spec/pull/491>
- OCI-Referrers header:
  - <https://github.com/opencontainers/distribution-spec/pull/463>
- Tag pagination:
  - <https://github.com/opencontainers/distribution-spec/pull/496>
- _add your items_

### Notes:
- "Allow registries to reject missing subject?"
  - Plan is to close the issue.
  - Will open a new PR for proposals of a 3rd way clients can push referrers.
  - The third option should automatically handle clients pushing with the fallback tag to avoid a split brain scenario.
  - Several are comfortable pushing out a 1.1 without the 3rd method of  pushing referrers, particularly if it is compatible with existing clients pushing referrers with the fallback tag.
- Other issues were quickly reviewed
  - General agreement on approving 491.
  - General agreement on OCI-Referrers header, but may want to add a way for clients to notify registries that they will want referrers.
  - Jon will update 496 from feedback.
- _add your notes_

## December 7, 2023

**Recording**: https://youtu.be/6UKdxVFRKqQ

### Attendees:
- Tianon
- Bjorn Neergaard
- Brandon Mitchell
- Michael Brown
- Marcin Franczyk
- David Dooling
- Toddy
- Ramkumar Chinchani
- James Sturtevant
- Jeff Carter
- Brandon Ha
- _add yourself_

### Note Taker:
- _add note taker_

### Actionable Agenda Items:
- Who's taking notes?
- _add your items_

### Presentation/Discussion Agenda Items:
- FreeBSD WG
  - <https://github.com/opencontainers/tob/pull/133>
- Status on "Allow registries to reject missing subject?"
  - <https://github.com/opencontainers/distribution-spec/issues/459>
- Removing scenario were referrers are accepted but not included in referrers API:
  - <https://github.com/opencontainers/distribution-spec/pull/491>
- OCI-Referrers header:
  - <https://github.com/opencontainers/distribution-spec/pull/463>
- Tag pagination:
  - <https://github.com/opencontainers/distribution-spec/pull/496>

### Notes:
- No progress on issues since key people are out.

## November 30, 2023

**Recording**: https://youtu.be/Ga7Azculsgs

### Attendees:
- Marcin Franczyk
- David Dooling
- James Sturtevant
- Toddy
- Josh Dolitsky
- Derek McGowan
- Ramkumar Chinchani
- Brandon Mitchell
- Michael Brown
- Mike Brown
- Jon Johnson
- Samuel Karp
- Brandon Ha
- Brian Goff
- Tianon

### Note Taker:
- _add note taker_

### Actionable Agenda Items:
- Who's taking notes?
- _add your items_

### Presentation/Discussion Agenda Items:
- standardization around compression params
  - <https://github.com/opencontainers/image-spec/issues/1145>
- Status on "Allow registries to reject missing subject?"
  - <https://github.com/opencontainers/distribution-spec/issues/459>
- Working Group template
  - <https://github.com/opencontainers/wg-template/pull/1>
- Fix OCI-Chunk-Min-Length header spec:
  - <https://github.com/opencontainers/distribution-spec/pull/481>
- Request to change image name allowed characters:
  - <https://github.com/opencontainers/distribution-spec/issues/466>
- Tag pagination:
  - <https://github.com/opencontainers/distribution-spec/pull/470>
  - What should the default / recommended limit be?
- Impact of a max chunk size limit on registries:
  - <https://github.com/opencontainers/distribution-spec/issues/485>
- If/when should distribution-spec add the blob streaming PATCH API used by Docker:
  - <https://distribution.github.io/distribution/spec/api/#stream-upload>
  - <https://github.com/opencontainers/distribution-spec/pull/404>
- OCI-Referrers header:
  - <https://github.com/opencontainers/distribution-spec/pull/463>
  - Is there a need for a present value, or should it be a link (to a CDN), or should we use the HTTP Link header for the present case?
- FreeBSD WG
  - https://github.com/opencontainers/tob/pull/133

### Notes:
- Reproducibility:
  - Not easy to solve, need the same tool building each time
- "reject missing subject"
  - Expect a working session from Derek
- Too late to change the "lower case image name" requirement
- Tag pagination:
  - Jon will open a PR for a breaking change to depend on the Link header
  - <https://github.com/opencontainers/distribution-spec/pull/496>
- There is some desire to standardize the "streaming" blob upload since it's well supported by registries (for moby)

### Agenda items deferred to a future meeting

- Removing scenario were referrers are accepted but not included in referrers API:
  - <https://github.com/opencontainers/distribution-spec/pull/491>

## November 23, 2023

*Canceled for US Thanksgiving holiday.*

## November 16, 2023

**Recording**: https://youtu.be/OyNQd2yPtN4

### Attendees:
- Wayne
- Mike Brown
- Brian Goff
- Joseph Ferguson
- Toddy
- Michael Brown
- John Kjell
- Bjorn Neergaard
- James Sturtevant
- Brandon Mitchell
- David Dooling
- Ramkumar Chinchani
- Josh
- Jon Johnson
- Sajay Antony
- Marcin Franczyk
- Jesse Butler
- _add yourself_

### Note Taker:
- _add note taker_

### Actionable Agenda Items:
- Skip next week's meeting?

### Presentation/Discussion Agenda Items:
- Defining artifacts
  - <https://github.com/opencontainers/image-spec/pull/1141>
  - Should mixed index be a documented/recommended method of distributing artifacts?
- Next steps for "should registries be allowed to reject manifests with non-existent subjects?"
  - <https://github.com/opencontainers/distribution-spec/issues/459>
  - <https://github.com/opencontainers/distribution-spec/issues/483>
  - <https://github.com/opencontainers/distribution-spec/issues/490>

### Agenda items deferred to a future meeting

- Fix OCI-Chunk-Min-Length header spec:
  - <https://github.com/opencontainers/distribution-spec/pull/481>
- Request to change image name allowed characters:
  - <https://github.com/opencontainers/distribution-spec/issues/466>
- Tag pagination:
  - <https://github.com/opencontainers/distribution-spec/pull/470>
  - What should the default / recommended limit be?
- Impact of a max chunk size limit on registries:
  - <https://github.com/opencontainers/distribution-spec/issues/485>
- If/when should distribution-spec add the blob streaming PATCH API used by Docker:
  - <https://distribution.github.io/distribution/spec/api/#stream-upload>
  - <https://github.com/opencontainers/distribution-spec/pull/404>
- OCI-Referrers header:
  - <https://github.com/opencontainers/distribution-spec/pull/463>
  - Is there a need for a present value, or should it be a link (to a CDN), or should we use the HTTP Link header for the present case?
- Removing scenario were referrers are accepted but not included in referrers API:
  - <https://github.com/opencontainers/distribution-spec/pull/491>
- Conformance: is there a digest in referrers response header?
  - <https://github.com/opencontainers/distribution-spec/pull/492>
- Conformance: test for annotation pull up:
  - <https://github.com/opencontainers/distribution-spec/pull/489>

### Notes:

From the chat:
00:04:06	Bjorn Neergaard:	https://github.com/opencontainers/image-spec/pull/1141
00:04:16	Brandon Mitchell:	https://hackmd.io/El8Dd2xrTlCaCG59ns5cwg?both
00:11:43	Jon Johnson:	unknown/unknown is noncompliant and it hurts my soul
00:15:13	Brian Goff (@cpuguy83):	Reacted to "unknown/unknown is n..." with 💯
00:15:20	Bjorn Neergaard:	Reacted to "unknown/unknown is n..." with 💯
00:15:58	Brandon Mitchell:	Reacted to "unknown/unknown is n..." with 💯
00:23:01	Ramkumar Chinchani:	GC is not part of any spec. Do we need to worry about that in the spec language?
00:23:58	Brandon Mitchell:	Is cosign / notation okay with tagging content pushed to a different repo than the referenced image? E.g. a detached signature (in a separate repo) is always tagged.
00:24:56	Brandon Mitchell:	GC concerns go away when you charge by the GB. :D
00:25:35	ToddySM:	Replying to "Is cosign / notation..."

I am uneasy about this approach. Right now we do not plan for this scenario
00:26:00	Brian Goff (@cpuguy83):	Reacted to "GC concerns go away ..." with 😂
00:26:04	Jeff Carter:	Reacted to "GC concerns go away ..." with 😂
00:26:13	Mike Brown:	Reacted to "GC concerns go away ..." with 🍕
00:26:31	ToddySM:	Replying to "Is cosign / notation..."

Not only from Notary Project point of view. Even ACR customers don’t want to have multiple endpoints
00:26:59	Sajay Antony:	Sorry.
00:27:20	Mike Brown:	Reacted to "unknown/unknown is n..." with 💯
00:27:24	Jeff Carter:	Maybe less so as a risk for any single registry, but more as an area where behavior is not well defined between different registries. If a goal with this spec is to provide predictable behavior for all of the use cases, it falls short
00:27:54	Sajay Antony:	We avoid GC in all aspects.
00:28:16	Ramkumar Chinchani:	per-user per-registry policy
00:28:37	Brian Goff (@cpuguy83):	What is a signature if its not attached to anything?
00:28:49	Ramkumar Chinchani:	cannot possibly be a universal prescription
00:28:52	Jesse Butler:	It may be a signature stored in a different repo or registry
00:29:21	Ramkumar Chinchani:	Always surprised with strange regulatory needs that arise
00:29:24	Jesse Butler:	Fwiw - what we have doesn’t work for that use case
00:29:50	ToddySM:	Reacted to "Maybe less so as a r..." with 👍
00:29:54	Ramkumar Chinchani:	Replying to "Always surprised wit..."

"keep this and that" separate from "others"
00:29:55	Sajay Antony:	Replying to "What is a signature …"
Basically it’s a way to store just these smaller contents for compliance for images or have a repo that only has supply chain artifacts is my read of these in attached artifacts.
00:30:37	ToddySM:	Replying to "Always surprised wit..."

Compartmentalization 😄
00:31:32	Brandon Mitchell:	I do have 491 to make it a formally recognized use case: https://github.com/opencontainers/distribution-spec/pull/491
00:31:45	Bjorn Neergaard:	I don’t think we need to go that far — it’s still MUST vs SHOULD
00:31:55	Bjorn Neergaard:	We’re discussing the use case because MUST means everyone HAS to support it
00:32:54	Brandon Mitchell:	There are registries that delete even tagged content. So GC is definitely registry defined.
00:33:19	ToddySM:	Replying to "There are registries..."

This is left to the customer to decide though.
00:33:28	Brian Goff (@cpuguy83):	👍
00:35:58	Brandon Mitchell:	https://github.com/opencontainers/wg-reference-types/blob/main/docs/proposals/PROPOSAL_F.md
00:35:59	Brian Goff (@cpuguy83):	Maybe something to consider because it was brought up: A registry can be spec compliant but not necessarily for everything for free accounts.
00:36:23	Sajay Antony:	Reacted to "Maybe something to c…" with 👍
00:38:32	Josh:	the cosign cross-registry thing does use tags btw
00:38:46	Brandon Mitchell:	Reacted to "the cosign cross-reg..." with 👍
00:39:43	Bjorn Neergaard:	Image 1.1 != Distribution 1.1
00:39:56	Bjorn Neergaard:	As has been posited by multiple people, you can implement one but not the other (either direction)
00:41:24	Brandon Mitchell:	What does it look like when a registry implements distribution 1.1 and image 1.0?
00:42:35	Josh:	maybe language in dist-spec is needed that it requires image-spec 1.1+. I'm not sure thats a good idea to allow them to be separate
00:43:17	Brandon Mitchell:	Cosign agrees it's a hack that they want to get away from :D
00:43:27	Mike Brown:	Reacted to "Cosign agrees it's a..." with 👍
00:43:50	Brandon Mitchell:	I want to delete the old content, but not every registry supports the delete API
00:45:36	Jesse Butler:	Ugh - that too 🙂
00:45:37	Brandon Mitchell:	A registry supporting image 1.1 doesn't give me much of anything. It shouldn't be parsing the content it doesn't recognize, so 1.0 and 1.1 should be the same to users.
00:45:59	Bjorn Neergaard:	Yeah; that’s what I’m trying to get at with the separability
00:46:04	Mike Brown:	if gives you more validation
00:47:53	Bjorn Neergaard:	The language was added in September: https://github.com/opencontainers/distribution-spec/pull/341
00:48:30	Bjorn Neergaard:	Sort of like foreign layers?
00:48:40	Bjorn Neergaard:	Err, non-distributable layers? Forgot what that feature was called.
00:49:19	Ramkumar Chinchani:	but you would have update that field every time situation flips for **all** references
00:49:37	Jesse Butler:	Every mutating utility needs a —force, right?
00:49:49	Bjorn Neergaard:	https://github.com/opencontainers/image-spec/blob/56fb7838abe52ee259e37ece4b314c08bd45997f/layer.md?plain=1#L327-L338
00:49:57	Mike Brown:	that does must accept mean..
00:51:10	Mike Brown:	one side .. it’s not part of the image.. “can’t be"
00:53:38	Bjorn Neergaard:	“winners and losers?”
00:57:48	Bjorn Neergaard:	My original thesis was that it was overly opinionated/imposed a disproportionate burden on registry implementors/constrained them without strong technical reasons to (so basically what Mike said)
00:58:23	Mike Brown:	tag as a point in time for doing the validation
00:59:44	Jesse Butler:	Without any relation to the data model, the spec could say subjects MUST exist
01:00:01	Jesse Butler:	I’m trying desperately to get away from the DAG 🙂
01:00:07	Josh:	^ "somewhere"
01:00:10	Bjorn Neergaard:	“MUST eventually exist”?
01:00:17	Mike Brown:	^^
01:00:22	Josh:	Reacted to "“MUST eventually ..." with 👍
01:00:26	Bjorn Neergaard:	That breaks the “separate referrers from content” use case though…
01:00:30	Mike Brown:	Reacted to "“MUST eventually exi..." with 👍
01:00:37	John Kjell:	Reacted to "“MUST eventually exi..." with ⏳
01:00:51	Jesse Butler:	Yes could be MUST eventually - but we veer into some implementation choices that we typically don’t inform in the spec (e.g. what does “eventually” mean)
01:00:52	Mike Brown:	“must eventually be validated”
01:01:08	Mike Brown:	allow for a remote validation
01:01:23	Bjorn Neergaard:	For the cross-registry case I guess you can argue that “I will validate at the heat death of the universe” is conformant…
01:01:24	Ramkumar Chinchani:	Replying to "“MUST eventually exi..."

also "MAY NOT eventually exist" in delete case
01:02:50	Josh:	i would be very THANKFUL if we could resolve this
01:02:53	ToddySM:	See you folks. Happy Thanksgiving 🙂

## November 7, 2023 - KubeCon US

**Recording**: https://youtu.be/T4C1paAoJSg

KubeCon Meeting Room: 
Tuesday, 11/7 from 2-4pm CST
McCormick Place in W195 on Level 1 

### Attendees: 
* Mike Brown (IBM)
* Michael Brown (AWS)
* Phil Estes 
* Josh 
* Jesse
* Akihiro Suda (NTT)
* Kohei Tokunaga (NTT)
* Brandon
* Bjorn
* Jeff Carter (Docker)
* ASP (part of the time)
* Derek McGowan (Docker)

### Agenda:

- Introductions
- Status from the specs
  - runtime 
      - https://github.com/opencontainers/runc/releases/tag/v1.1.10
      - https://github.com/opencontainers/runtime-spec/releases/tag/v1.1.0
      - idmap support in spec v1.1.0 was incomplete; being revised in https://github.com/opencontainers/runtime-spec/pull/1224
      - Hopefully spec v1.1.1 and runc v1.2.0 (and containerd v2.0.0) by the end of the year
      - Discussion to propagate image labels to runtime annotations; No need to modify {image,dist}-spec from the perspective of runtime-spec https://github.com/opencontainers/runtime-spec/pull/1197 https://github.com/opencontainers/runtime-spec/pull/1205
  - image
      - artifacts support through adding subject field (ref) to OCI Image and Index
  - distribution
      - in limbo see working session
- Status from WGs
  - Auth
      - looking at patterns, moby, containerd, oras...
  - Image Compatibility
      - tbd
- Artifact WG
  - Part of Application SIG
  - Looking at what features are needed by various package managers (OCI, npm, pip, debian, alpine, etc)
  - May have suggestions of features needed by OCI (search for repository, artifact details in tag listing)
- Planning for future WGs
  - https://github.com/opencontainers/tob/pull/114
- Working session milestone blockers for image and distribution 1.1 releases
  - https://github.com/opencontainers/image-spec/milestone/14
  - https://github.com/opencontainers/distribution-spec/milestone/6
  - https://github.com/opencontainers/distribution-spec/issues/459
  - https://github.com/opencontainers/distribution-spec/pull/487
  - https://github.com/opencontainers/distribution-spec/issues/483

## November 2, 2023

**Recording**: https://youtu.be/4RZZkego5dA

### Attendees:
- Marcin Franczyk
- Michael Brown
- Jon Johnson
- Joe Huang
- David Dooling
- Joseph Ferguson
- Bjorn Neergaard
- Derek McGowan
- Sajay Antony
- John Kjell
- Ramkumar Chinchani
- Jesse Butler
- Vincent Batts
- Jeff Carter
- Syed
- cpuguy
- Wayne
- Stephen Day

### Note Taker:
- _add note taker_

### Actionable Agenda Items:
- Reviews needed on content-type parameters: <https://github.com/opencontainers/distribution-spec/pull/469>
- Review needed on Go versions in CI: <https://github.com/opencontainers/image-spec/pull/1114>
- Review needed on Go toolchain=local: <https://github.com/opencontainers/image-spec/pull/1133>
- _add your items_

### Presentation/Discussion Agenda Items:
- Packaging Con can use more OCI representation: <https://packaging-con.org/>
- Agenda for KubeCon
  - Status from the specs
  - Status from WGs
  - Artifact WG
  - Planning for future WGs
  - Working session milestone blockers for image and distribution 1.1 releases
- Decision on "registries MUST allow subject": <https://github.com/opencontainers/distribution-spec/issues/483>
  - Distribution-spec proposal in <https://github.com/opencontainers/distribution-spec/issues/459>
  - Alternate proposal in <https://github.com/opencontainers/distribution-spec/issues/459#issuecomment-1791086326>
  - Conditional API support: <https://github.com/opencontainers/distribution-spec/pull/251>
- Remaining items were not discussed this week:
  - Definition of an artifact conceptually and in code (waiting for runtime feedback on mixed content index manifests): <https://github.com/opencontainers/image-spec/pull/1141>
  - Impact of a max chunk size limit on registries: <https://github.com/opencontainers/distribution-spec/issues/485>
  - If/when should distribution-spec add the blob streaming PATCH API used by Docker: <https://distribution.github.io/distribution/spec/api/#stream-upload>
    - <https://github.com/opencontainers/distribution-spec/pull/404>
- _add your items_

### Notes:
- _add your notes_

## October 26, 2023

**Recording**: https://youtu.be/d0sNI4gaWNg

### Attendees:
- Ramkumar Chinchani
- David Dooling
- wayne 
- joehuang
- Marcin Franczyk
- Mike Brown
- Jesse Butler
- Derek McGowan
- Jon Johnson 
- Brandon Klein
- Sajay Antony
- Joseph Ferguson
-  _add yourself_

### Note Taker:
- _add note taker_

### Actionable Agenda Items:
- Who's taking notes?
- _add your items_

### Presentation/Discussion Agenda Items:
- KubeCon planning
- Carry-over items?

### Notes:
- KubeCon planning
    - usually a day0 / community meeting
    - not all will be all days at conf/pre-conf
    - JB: follow up on Slack, pick up thread from 2 weeks back
    - suggest maybe later in day / miss conf agenda conflicts?
- Potential future issue from Wayne
    - no 'Max-Length' peer to OCI-Chunk-Min-Length
    - may consider adding a maximum length 
- Image compatibility WG PR is merged
    - WG is approved and now getting set up (governance, comms)

## October 19, 2023

**Recording**: https://youtu.be/xi4z_DovXyc

### Attendees:
- Wayne
- Joseph Ferguson
- Joe Huang
- Marcin Franczyk
- Bjorn Neergaard
- Brandon Mitchell
- Phil Estes
- Ramkumar Chinchani
- Toddy
- Michael Brown
- Samuel Karp
- Derek McGowan
- Sajay Antony
- Kristopher Francisco
- Syed
- Jesse Butler
- _add yourself_

### Note Taker:
- _add note taker_

### Actionable Agenda Items:
- Fix OCI-Chunk-Min-Length header definition: <https://github.com/opencontainers/distribution-spec/pull/481>
- _add your items_

### Presentation/Discussion Agenda Items:
- Can registries reject unknown subject digest:
  - <https://github.com/opencontainers/distribution-spec/issues/483>
  - <https://github.com/opencontainers/distribution-spec/issues/459>
- Should HEAD requests include content length: <https://github.com/opencontainers/distribution-spec/pull/482>
- Remaining items deferred to a future meeting
- WASM/Artifacts:
  - <https://github.com/opencontainers/image-spec/pull/1137>
  - <https://github.com/opencontainers/image-spec/pull/1141>
- Tag pagination recommended size: <https://github.com/opencontainers/distribution-spec/pull/470>

### Notes:
- _add your notes_

## October 12, 2023

**Recording**: https://youtu.be/hcMy1mgpBM8

### Attendees:
- Marcin Franczyk
- Joe Huang
- Brian Goff
- Joseph Ferguson
- Derek McGowan
- Jon Johnson
- Wayne
- Alexander Kanevskly
- Jeff Carter
- Mike Brown
- Ramkumar Chinchani
- Sajay Antony
- Bjorn Neergaard
- Jesse Butler
- Toddy
- Samuel Karp
- John Kjell
- _add yourself_

### Note Taker:
- _add note taker_

### Actionable Agenda Items:
- Who's taking notes?
- _add your items_

### Presentation/Discussion Agenda Items:
- KubeCon Meeting Room: Tuesday, Nov 7 11a-1p - Agenda?
- Image compatibility working group - vote
- Allowing registries to reject images without an associated subject manifest: <https://github.com/opencontainers/distribution-spec/issues/459>
- How to deal with image config above a reasonable size
- Defining "image": <https://github.com/opencontainers/image-spec/pull/1137>
- Check in on Image and Distribution 1.1
    - https://github.com/opencontainers/image-spec/milestone/14
    - https://github.com/opencontainers/distribution-spec/milestone/6

### Notes:
- _add your notes_


## September 28, 2023

**Recording**: https://youtu.be/PZPCV4MWZJ8

### Attendees:
- Bjorn Neergaard
- Toddy
- Marcin Franczyk
- Joe Huang
- Derek McGowan
- Joseph Ferguson
- Phil Estes
- Brandon Mitchell
- Sajay Antony
- _add yourself_

### Note Taker:
- _add note taker_

### Actionable Agenda Items:
- https://github.com/opencontainers/distribution-spec/pull/469
- https://github.com/opencontainers/image-spec/issues/1131
    - Bjorn will open a PR with suggested changes to the language
- _add your items_

### Presentation/Discussion Agenda Items:
- https://github.com/opencontainers/image-spec/issues/1131
- https://github.com/opencontainers/distribution-spec/pull/470

### Notes:
- _add your notes_

## September 21, 2023

**Recording**: https://youtu.be/svf8fJuSuL8

- Brandon Mitchell
- Bjorn Neergaard
- Marcin Franczyk
- Joe Huang
- Jesse Butler
- Jeff Carter
- Alexander Kanevskiy
- Mike Brown
- Michael Brown
- Ramkumar Chinchani
- Jayson Du
- Derek McGowan
- Joseph Ferguson


### Attendees:

### Note Taker:
- _add note taker_

### Actionable Agenda Items:
- Tag list pagination guidance/new error response

### Presentation/Discussion Agenda Items:
- Image Compatibility Working Group PR, next steps - https://github.com/opencontainers/tob/pull/128
- Tag listing pagination: <https://github.com/opencontainers/distribution-spec/issues/461>
  - Open a PR: suggest servers support at least 100 tags, may respond with an error on requests that exceed that, and may support Link header for pagination that clients may support
- PR needed for empty artifactType: <https://github.com/opencontainers/distribution-spec/issues/458>
- Parameters in content-type headers: <https://github.com/opencontainers/distribution-spec/issues/408>
  - Open a PR: servers SHOULD NOT include parameter, clients SHOULD ignore parameters when encountered

### Notes:
- _add your notes_

## September 14, 2023

**Recording**: https://youtu.be/iIXnvmssjTM

### Attendees:
- Brandon Mitchell
- Derek McGowan
- Bjorn Neergaard
- Marcin Franczyk
- Jesse Butler
- syed
- Ramkumar Chinchani
- Joseph Ferguson
- Vipin Mohan
- Mike Brown
- Sajay Antony
- Joe Huang
- Jayson Du

### Note Taker:
- _add note taker_

### Actionable Agenda Items:
- image spec rc5: <https://github.com/opencontainers/image-spec/pull/1109>
- `OCI-Referrers: absent` header: <https://github.com/opencontainers/distribution-spec/pull/463>
- _add your items_

### Presentation/Discussion Agenda Items:
- Can registries reject non-existent subjects: <https://github.com/opencontainers/distribution-spec/issues/459>
- Tag listing pagination: <https://github.com/opencontainers/distribution-spec/issues/461>
- PR needed for empty artifactType: <https://github.com/opencontainers/distribution-spec/issues/458>
- Parameters in content-type headers: <https://github.com/opencontainers/distribution-spec/issues/408>
- _add your items_

### Notes:
- _add your notes_

## September 7, 2023

**Recording**: https://youtu.be/_aKaY-8h__M

### Attendees:
- Mike Brown
- Brandon Mitchell
- Joe Huang
- Bjorn Neergaard
- Derek McGowan
- John Kjell
- Syed
- Ramkumar Chinchani
- Sajay
- Marcin Franczyk
- Jayson Du
- Joseph Ferguson
- _add yourself_

### Note Taker:
- _add note taker_

### Actionable Agenda Items:
- Conformance cleanup: <https://github.com/opencontainers/distribution-spec/pull/462>
- `OCI-Referrers: absent` header: <https://github.com/opencontainers/distribution-spec/pull/463>
- Fixing `last` parameter: <https://github.com/opencontainers/distribution-spec/pull/464>
- Supported Go versions: <https://github.com/opencontainers/image-spec/pull/1114>
- image-spec rc5: <https://github.com/opencontainers/image-spec/pull/1109>
- _add your items_

### Presentation/Discussion Agenda Items:
- Can registries reject non-existent subjects: <https://github.com/opencontainers/distribution-spec/issues/459>
- Tag listing pagination: <https://github.com/opencontainers/distribution-spec/issues/461>
- Reference spec: <https://github.com/opencontainers/tob/pull/114>
- _add your items_

### Notes:
- Most agenda items were skipped, we focused on "Can registries reject non-existent subjects: <https://github.com/opencontainers/distribution-spec/issues/459>"
- _add your notes_

## August 31, 2023

**Recording**: https://youtu.be/efAqVMlOvYw

### Attendees:
- Brandon Mitchell
- Aaron Friel
- Jon Johnson
- Bjorn Neergaard
- Victor Lu
- Ramkumar Chinchani
- John Kjell
- Joe Huang
- Marcin Franczyk
- Joseph Ferguson
- Syed
- Sajay Antony
- Joe Huang
- Mike Brown

### Note Taker:
- _add note taker_

### Actionable Agenda Items:
- Who's taking notes?
- _add your items_

### Presentation/Discussion Agenda Items:
- Discuss Image spec release or RC for v1.1.0 https://github.com/opencontainers/image-spec/pull/1109 [sajay]
- Discuss Distribution spec - https://github.com/opencontainers/distribution-spec/issues/458 
- Tag list pagination [syed](/hR3THNBxTEqpEo4OLGb_yg)
- Can registries reject a missing subject: <https://github.com/opencontainers/distribution-spec/issues/459>
- - _add your items_

### Notes:
- _add your notes_


## August 24, 2023

**Recording**: https://youtu.be/A_thQgOntCg

### Attendees:
- Marcin Franczyk
- Joe Huang
- Brandon Mitchell
- Greg Wallace
- John Kjell
- Brandon Klein
- Brandon Ha
- Brian Goff
- Michael Brown (AWS)
- Bjorn Neergaard
- Ramkumar Chinchani
- Joseph Ferguson
- _add yourself_

### Note Taker:
- _add note taker_

### Actionable Agenda Items:
- Who's taking notes?
- _add your items_

### Presentation/Discussion Agenda Items:
- Image Compatibility Spec - Marcin Franczyk, Joe Huang
    - https://docs.google.com/presentation/d/1F9GnCm2sULuyTJ5BEFZlL8Qjab81DK7g9Oy6qBfe5Qs/edit?usp=sharing
    - <https://docs.google.com/document/d/1lzwh8DGMu5vXXHwJmnewYIMffkcOEvH8owX4UYjRcw0/edit#heading=h.fcxt9vheg92c>
- <https://github.com/opencontainers/distribution-spec/issues/459>

### Notes:
- _add your notes_

## August 17, 2023

**Recording**: https://youtu.be/KsqcC4AfCbc

### Attendees:
- Derek McGowan
- Bjorn Nergaard
- Greg Wallace
- Ed Maste
- Joseph Ferguson
- Sajay Antony
- Amye Scavarda Perrin
- Brandon Mitchell
- Mike Brown (IBM)
- Ramkumar Chinchani
- Jon Johnson
- Brian Goff
- _add yourself_

### Note Taker:
- _add note taker_

### Actionable Agenda Items:
- Who's taking notes?
- _add your items_

### Presentation/Discussion Agenda Items:
- Merry Updates Time:
    - https://github.com/opencontainers/opencontainers.org/blob/main/content/release-notices/overview.md could use your releases!
    - We should add this to the release checklist otherwise it will continually be out of date
    - <https://github.com/opencontainers/specs.opencontainers.org/issues/3>
        - Coming attraction: space at KubeCon 
- What happens with an index that has a subject but no artifactType?
  - <https://github.com/opencontainers/image-spec/issues/1106>
  - <https://github.com/opencontainers/distribution-spec/issues/458>
  - Decided to make the artifactType field in distribution-spec optional
- Are parameters allowed on the content-type header?
  - <https://github.com/opencontainers/distribution-spec/issues/456>
  - <https://github.com/opencontainers/distribution-spec/issues/408>
  - Decided to not allow it in our spec but recommend clients try to handle it if seen
- Should we add support for an OCI-Referrers header on manifest pull?
  - <https://github.com/opencontainers/distribution-spec/issues/454>
  - Support the absent header, add link header support
- How should we handle old references to archived projects?
  - <https://github.com/opencontainers/image-spec/issues/1096>
- Conformance issues related to MUST language on subject existing
  - <https://github.com/opencontainers/distribution-spec/pull/341> (discuss from old PR)
  - <https://youtu.be/9k2QbsrbkY0?t=587> (previous discussion)

### Notes:
- _add your notes_

## August 10, 2023

**Recording**: https://youtu.be/rQOqdaUKXg8

### Attendees:
- Brandon Mitchell
- Brian Goff
- Ben Cotton
- John Kjell
- Aaron Friel
- Ramkumar Chinchani
- Samuel Karp
- Joseph Ferguson
- Bjorn Neergaard
- Joe Huang
- _add yourself_

### Note Taker:
- _add note taker_

### Actionable Agenda Items:
- Who's taking notes?
- _add your items_

### Presentation/Discussion Agenda Items:
- Artifact type guidance:
  - <https://github.com/opencontainers/image-spec/pull/1101>
  - <https://github.com/opencontainers/image-spec/pull/1100>
- Release status
  - Those looking for a 6 week window are planing for next week
  - Brandon raised concerns that registry operators, with the exception of Zot, have not given feedback on the conformance test
- _add your items_

### Notes:
- _add your notes_

## August 3, 2023

**Recording**: https://youtu.be/dCQBeWhYqqM

### Attendees:
- Brandon Mitchell
- Toddy
- Joseph Ferguson
- Ramkumar Chinchani
- _add yourself_

### Note Taker:
- _add note taker_

### Actionable Agenda Items:
- Who's taking notes?
- _add your items_

### Presentation/Discussion Agenda Items:
- _add your items_

### Notes:
- _add your notes_
- <https://github.com/opencontainers/distribution-spec/issues/454>

## July 27, 2023

**Recording**: https://youtu.be/LdFuG9FpHuY

### Attendees:
- Brandon Mitchell
- Bjorn Neergaard
- Brian Goff
- Tianon
- Ramkumar Chinchani
- Nathana
- Brandon Ha
- Sajay Antony
- Nathan Anderson
- Jesse Butler
- Mike Brown  (I)
- syed
- _add yourself_

### Note Taker:
- _add note taker_

### Actionable Agenda Items:
- Who's taking notes?
- _add your items_

### Presentation/Discussion Agenda Items:
- Scheduling auth working group: <https://doodle.com/meeting/participate/id/b4LvGr2b>
  - Planning on 1ET/10PT Tuesdays
- State of 1.1.0 implementations for image/distribution specs: <https://github.com/opencontainers/image-spec/issues/1093>
- Referrers response header needed defining: <https://github.com/opencontainers/distribution-spec/pull/452>
- _add your items_

### Notes:
- Auth working group can meet on Tuesday(30 mins past  time as the OCI call on Thursday) 10:30 PST 5:30 GMT 
- _add your notes_

## July 20, 2023

**Recording**: https://youtu.be/H5g_ZpaRc20

### Attendees:
- Ramkumar Chinchani (Cisco,zot)
- Brandon Mitchell
- Mike Brown
- Phil Estes
- Brian Goff
- Tianon
- Michael Brown
- John Kjell
- ToddySM
- _add yourself_

### Note Taker:
- _add note taker_

### Actionable Agenda Items:
- Who's taking notes?
- _add your items_

### Presentation/Discussion Agenda Items:
- (auth) Working group doodle - https://doodle.com/meeting/participate/id/b4LvGr2b
- Continue to wait 4 weeks for [this](https://github.com/opencontainers/image-spec/issues/1093) ...
    - ...but what if we didn't?
        - "the duration of the six-week time frame is subject to adjustment"
            - ![](https://hackmd.io/_uploads/HkN-GRLcn.png) ??? 🤷


- _add your items_

### Notes:
- _add your notes_

## July 13, 2023

**Recording**: https://youtu.be/NqUM9XslkU8

### Attendees:
- Brandon Mitchell
- Phil Estes
- Toddy
- Tianon Gravi
- Jon Johnson
- Josh Dolitsky
- Ramkumar Chinchani
- Sajay Antoy
- Michael Brown
- Mike Brown
- Bjorn Neergaard
- _add yourself_

### Note Taker:
- _add note taker_

### Actionable Agenda Items:
- Who's taking notes?
- _add your items_

### Presentation/Discussion Agenda Items:
- https://github.com/opencontainers/image-spec/milestone/14
- Conformance GitHub action (Josh)
- Planning for auth working group
- _add your items_

### Notes:
- Sent out a [doodle poll](https://doodle.com/meeting/participate/id/b4LvGr2b/vote) for Auth working group. [sajay]
- _add your notes_


## July 6, 2023

**Recording**: https://youtu.be/jMO3zIPJ-qg

### Attendees:
- Josh Dolitsky
- Brandon Mitchell
- Ramkumar Chinchani (zot/Cisco)
- Mike Brown (IBM)
- Tianon Gravi
- Brandon Klein
- _add yourself_

### Note Taker:
- _add note taker_

### Actionable Agenda Items:
- Who's taking notes?
- _add your items_

### Presentation/Discussion Agenda Items:
- image-spec [v1.1.0-rc4](https://github.com/opencontainers/image-spec/releases/tag/v1.1.0-rc4) has been out for a week and the [v1.1.0 milestone](https://github.com/opencontainers/image-spec/milestone/14) has no items. Time for v1.1.0 release? (Josh)
  - <https://github.com/opencontainers/image-spec/pull/1082>
  - <https://github.com/opencontainers/image-spec/pull/1085>
  - <https://github.com/opencontainers/image-spec/pull/1087>
  - <https://github.com/opencontainers/image-spec/pull/1090>
- distribution-spec v1.1.0-rc3 rejected - here are the open items (Josh):
  - New PR: <https://github.com/opencontainers/distribution-spec/pull/440>
- _add your items_

### Notes:
- _add your notes_

## June 29, 2023

**Recording**: https://youtu.be/5vLbK4HClk8

### Attendees:
- Brandon Mitchell
- Mike Brown (IBM)
- Toddy
- Jesse Butler
- Brandon Ha
- Josh Dolitsky
- Bjorn Neergaard
- Tianon Gravi
- John Kjell
- Sajay Antony
- _add yourself_

### Note Taker:
- _add note taker_

### Actionable Agenda Items:
- Who's taking notes?
- _add your items_

### Presentation/Discussion Agenda Items:
- runtime-spec v1.1.0
  - mailing list: https://groups.google.com/a/opencontainers.org/g/dev/c/nzk4OnQvxlI
  - github pr: https://github.com/opencontainers/runtime-spec/pull/1213
- image-spec v1.1.0-rc4
  - mailing list: https://groups.google.com/a/opencontainers.org/g/dev/c/gPgzESGb7xs
  - github pr: https://github.com/opencontainers/image-spec/pull/1080
- distribution-spec v1.1.0-rc3
  - mailing list: https://groups.google.com/a/opencontainers.org/g/dev/c/BQk9AKEAdUk
  - github pr: https://github.com/opencontainers/distribution-spec/pull/433
- Do we have tools (registries and clients) implementing the latest distribution and image spec? (Brandon)
- containerd shims and the interface to runtime-spec
- authn/authz:
  - <https://github.com/opencontainers/tob/pull/119>
- _add your items_

### Notes:
- _add your notes_

## June 22, 2023

**Recording**: https://youtu.be/BTa_x1n6hsQ

### Attendees:
- Brandon Mitchell
- Andrew Block
- Jason Hall
- Roger Peppe
- Tianon Gravi
- Bjorn Neergaard
- Ramkumar Chinchani
- Sajay Antony
- Jon Johnson
- Jesse Butler
- Josh Dolitsky
- Aaron Friel
- Brandon Klein
- _add yourself_

### Note Taker:
- _add note taker_

### Actionable Agenda Items:
- Who's taking notes?
- _add your items_

### Presentation/Discussion Agenda Items:
- Preparing Image spec for release RC4
    - [image-index: add artifactType to specs and schema ](https://github.com/opencontainers/image-spec/pull/1077)
    - [specs-go: remove artifact prefixed annotations #1078](https://github.com/opencontainers/image-spec/pull/1078)
    - [Alignment/Consolidation of Predefined Annotations to Support Artifact Types #980](https://github.com/opencontainers/image-spec/issues/980)
- OCI v1.1 (image+dist) milestones outstanding items (Josh)
    - dist: https://github.com/opencontainers/distribution-spec/milestone/6
        - https://github.com/opencontainers/distribution-spec/pull/325
    - image: https://github.com/opencontainers/image-spec/milestone/14
        - https://github.com/opencontainers/image-spec/issues/980
- Enabling stale-bot on OCI issues/PRs [Jason]
- FYI: Runtime-spec is planning a 1.1 release soon

### Notes:
- _add your notes_


## June 15, 2023

**Recording**: https://youtu.be/RHO5WKEnlu4

### Attendees:
- vbatts
- Brandon Mitchell
- Ramkumar Chinchani
- Toddy
- Victor Lu
- Brian Goff
- Bjorn Neergaard
- Tianon
- Sajay
- Mike Brown (IBM)
- _add yourself_

### Note Taker:
- _add note taker_

### Actionable Agenda Items:
- Who's taking notes?
- PR review on https://github.com/opencontainers/image-spec/pull/1066
  - Friel is unfortunately absent, other obligation today. Would appreciate a review :)
- OCI Distribution Spec conformance tests
    - There are many open PRs, can we get a yay/nay on these?
    - https://github.com/opencontainers/distribution-spec/milestone/6
    - https://github.com/opencontainers/distribution-spec/pull/423
        - https://github.com/opencontainers/distribution-spec/pull/423#pullrequestreview-1482097246
    - https://github.com/opencontainers/image-spec/pull/1020
    - https://github.com/opencontainers/image-spec/pull/1066
    - https://github.com/opencontainers/image-spec/issues/1076
    - https://github.com/opencontainers/image-spec/pull/1030

### Presentation/Discussion Agenda Items:
- _add your items_

### Notes:
- _add your notes_

## June 8, 2023

**Recording**: https://youtu.be/2Fip7rd8Zos

### Attendees:
- Brandon Mitchell
- Aaron Friel
- Sajay Antony
- Ramkumar Chinchani
- Brandon Klein
- Jon Johnson
- Tianon Gravi
- Mike Brown (IBM)
- _add yourself_

### Note Taker:
- _add note taker_

### Actionable Agenda Items:
- Who's taking notes?
- Reviews needed on empty descriptor: <https://github.com/opencontainers/image-spec/pull/1068>
- _add your items_

### Presentation/Discussion Agenda Items:
- Should there be toml support in image-spec? <https://github.com/opencontainers/image-spec/pull/1074>
  - It doesn't impact existing uses of the spec and is needed for Go implementations to avoid copying between separately maintained types.
- Should conformance generate warnings? <https://github.com/opencontainers/distribution-spec/pull/421>
  - Yes, for items that are not "MUST". Feedback to developer that doesn't need to be seen by end users.
- _add your items_

### Notes:
- _add your notes_

## June 1, 2023

**Recording**: https://youtu.be/YCkCi_sJe5o

### Attendees:
- Brandon Mitchell
- Brian Goff
- Ramkumar Chinchani
- Aaron Friel
- ToddySM
- Sajay Antony
- David Justice
- Jon Johnson
- Bjorn Neergaard
- Brandon Klein
- Michael Brown
- Tianon Gravi
- _add yourself_

### Note Taker:
- _add note taker_

### Actionable Agenda Items:
- Who's taking notes?
- _add your items_

### Presentation/Discussion Agenda Items:
- image-spec: renaming the "scratch" descriptor ("filler" ? "inert" ?) [Brandon or Tianon]
    - https://github.com/opencontainers/image-spec/issues/1067
    - https://github.com/opencontainers/image-spec/pull/1068
- image-spec: Adding artifactType to Image Index https://github.com/opencontainers/image-spec/pull/1066
- image-spec: No activity on https://github.com/opencontainers/image-spec/pull/1030
- _add your items_

### Notes:
- _add your notes_

## May 25, 2023

**Recording**: https://youtu.be/IEjCFOZdavk

### Attendees:
- ToddySM
- Brandon Mitchell
- Aaron Friel
- Brian Goff
- Derek McGowan
- Jon Johnson
- Mike Brown
- Phil Estes
- Tianon Gravi
- Brandon Klein
- Victor Lu
- Sajay Antony (chat only)

### Note Taker:
- _add note taker_

### Actionable Agenda Items:
- Who's taking notes?
- distribution-spec needs an approver for `+dev`: <https://github.com/opencontainers/distribution-spec/pull/417>
- Add artifactType to index: <https://github.com/opencontainers/image-spec/pull/1066>
- _add your items_

### Presentation/Discussion Agenda Items:
- Unblocking discussion on <https://github.com/opencontainers/image-spec/pull/1030>?
  Previous call discussed moving this to distribution spec; but there was concern about registry support. How can we unblock? 
- Garbage collection in registries (ToddySM)

### Notes:

## May 18, 2023

**Recording**: https://youtu.be/qjSOsm85C6c

### Attendees:
- Brandon Mitchell 
- Phil Estes
- Toddy SM
- Brian Goff
- Tianon Gravi
- Mike Brownn (IBM)
- Sajay ANtony
- Aaron Freil
- Derek McGowan
- Ramkumar Chinchani
- _add yourself_

### Note Taker:
- _add note taker_

### Actionable Agenda Items:
- Who's taking notes?
- Using `+dev` in version: <https://github.com/opencontainers/image-spec/pull/1050>, <https://github.com/opencontainers/runtime-spec/pull/1198>
- Scratch blob content: <https://github.com/opencontainers/image-spec/pull/1064>
- _add your items_

### Presentation/Discussion Agenda Items:
- Risks when copying annotations from image to runtime: <https://github.com/opencontainers/image-spec/pull/1061>
- `org.opencontainers.image.source.subpath`: <https://github.com/opencontainers/image-spec/pull/1062>
- FYI - Tommorrow is the first CNCF Artifact WG Meeting
  From Slack: 
> Hi TAG! The TAG will host a preliminary meeting of the proposed Artifacts WG tomorrow Friday May 19 to finish the group's charter and start work towards its goals. More info on the proposed group and its mission is in this issue and the draft charter.
> If you'd like to contribute to simplifying packaging, delivery and deployment of both configuration and binary content please join the group! Slack channel here: #wg-artifacts.
> Info for tomorrow's meeting:
> Event page (RSVP for an invite): https://community.cncf.io/events/details/cncf-tag-app-delivery-presents-wg-artifacts-project-meeting/
> Date/Time: Friday May 19 @ 1600 UTC (https://www.timeanddate.com/worldclock/converter.html?iso=20230519T160000&p1=1440&p2=64&p3=1960&p4=tz_aet)
> Zoom URL: https://zoom.us/j/7276783015?pwd=R0RJMkRzQ1ZjcmE0WERGcTJTOEVyUT09
> Notes URL: https://docs.google.com/document/d/1E7iKPOuyA1jxPe8vDG8aPd8jtnCEbpDpCifXDvDCnA0/edit
> Charter URL: https://docs.google.com/document/d/1w_lo2RZDKeEzQg4DMV-9Tq4ir_znONj_ypJ27CUfMgY/
> Slack: https://cloud-native.slack.com/archives/C04UQDWS4M7
- Can we target date for OCI 1.1 GA? (ToddySM)

### Notes:
From the chat:
- Gitlab
    - https://github.com/moby/buildkit/pull/3610#issuecomment-1453858526
    - https://gitlab.com/gitlab-org/container-registry/-/issues/967
- granted, we're basically _always_ in an "request for comment" period, but what about a public notice of RFC that is open for say 60 days, with something about raising blockers.

## May 11, 2023

**Recording**: https://youtu.be/8ASCmKinQaQ

### Attendees:
- Brian Goff (MSFT)
- Josh Dolitsky (Chainguard)
- Ramkumar Chinchani
- Michael Brown
- Mike Brown
- Victor Lu
- Tianon Gravi
- Brandon Klein
- Sajay Antony

### Note Taker:
- _add note taker_

### Actionable Agenda Items:
- Who's taking notes?
- _add your items_

### Presentation/Discussion Agenda Items:
- Wasm (Brian)

### Notes:
- (horrifyingly oversimplified notes by Tianon)
- Brian: can we store "wasi" modules in the config object for the runtime to install?
- Tianon: yes*
  - spec says unknown fields should be ignored (so you don't need our "permission")
  - wasi is big moving target, so it would be useful to have more implementation proof that the proposal is "sufficient" before we codify it in the spec (and thus try to avoid spec churn)

From Chat:
- https://github.com/opencontainers/image-spec/pull/1055/files

## May 4, 2023

**Recording**: https://youtu.be/Fto6y9QSWgg

### Attendees:
- Brandon Mitchell
- Aaron Friel
- Brandon (Klein?)
- John Kjell
- Michael Brown
- Sajay Antony
- ToddySM
- Tianon Gravi
- Ramkumar Chinchani
- Mike Brown (IBM)
- Brian Goff
- _add yourself_

### Note Taker:
- _add note taker_

### Actionable Agenda Items:
- Who's taking notes?
- _add your items_

### Presentation/Discussion Agenda Items:
- Use `+dev` instead of `-dev`: <https://github.com/opencontainers/image-spec/pull/1050>
- Clarify when errors are allowed: <https://github.com/opencontainers/image-spec/pull/1030>
- `Content-Type` syntax: <https://github.com/opencontainers/distribution-spec/issues/408>
- Allow 307 responses: <https://github.com/opencontainers/distribution-spec/issues/397>
- `Content-Length` omitted on patch requests: <https://github.com/opencontainers/distribution-spec/pull/404>
- Registry vs repository terminology: <https://github.com/opencontainers/distribution-spec/pull/325>
- _add your items_

### Notes:
From the chat:
00:12:25	Sajay Antony:	+1 to More Brandons
00:26:57	Ramkumar Chinchani:	allowlist/denylist could be a registry-specific policy, every deployment will have an opinion
00:34:21	Aaron Friel:	encoding my artifact type by using the casing bits of spongebob case as a sidechannel
00:35:02	Ramkumar Chinchani:	Another example of HTTP rfcs conflicting with dist-spec … "Range" is one other
00:37:09	Aaron Friel:	In accordance with the RFC this is also valid:

Content-Type: application/vnd.oci.image.index.v1+json (Generated by Friel)
00:41:13	Aaron Friel:	@Tianon looking forward to your media type experiments and seeing which runtimes break on comments and parameters
00:41:14	Sajay Antony:	I like differing to the RFC as a disambiguation.
00:43:10	Tianon Gravi:	I'm far too tired for that 😅
00:43:29	Tianon Gravi:	it's definitely not defined as allowed in "mediaType" fields, so this would only be for "Content-Type" I think
00:43:40	Aaron Friel:	Reacted to "it's definitely not ..." with 👍
00:45:38	Tianon Gravi:	PUT https://index.docker.io/v2/tianon/test/manifests/sPoNgEbOb: MANIFEST_INVALID: manifest invalid; if present, mediaType in manifest should be 'application/vnd.oci.image.manifest.v1+json' not 'aPpLiCaTiOn/vNd.oCi.iMaGe.mAnIfEsT.V1+jSoN'
00:46:03	Sajay Antony:	Reacted to "PUT https://index.do…" with 😂
00:47:01	Tianon Gravi:	https://explore.ggcr.dev/?image=tianon/test:sPoNgEbOb
00:55:53	Ramkumar Chinchani:	also multi-tenant access control
00:57:08	John Kjell:	400-499 😂

## April 27, 2023

**Recording**: https://youtu.be/33V8H3a_3aA

### Attendees:
- Ramkumar Chinchani
- Josh Dolitsky
- Brandon Klein
- Brandon Mitchell
- Brian Goff
- Jason Hall
- John Kjell
- Jon Johnson
- Leroy
- Mike Brown (ibm)
- Tianon Gravi
- Lachlan Evenson
- Samuel Karp
- Aaron Friel
- Jeanine Burke
- _add yourself_

### Note Taker:
- _add note taker_

### Actionable Agenda Items:
- Who's taking notes?
- Tag image-spec 1.1.0-rc.3 <https://github.com/opencontainers/image-spec/pull/1049> - https://github.com/opencontainers/image-spec/releases/tag/v1.1.0-rc.3 in pre release
- Tag distribution-spec 1.1.0-rc.2 <https://github.com/opencontainers/distribution-spec/pull/403> - https://github.com/opencontainers/distribution-spec/releases/tag/v1.1.0-rc.2 in pre release
- Push to next week PR1030  <https://github.com/opencontainers/image-spec/pull/1030>
- wasi is back, now with p: https://github.com/opencontainers/image-spec/issues/1053
    - Jason Hall will open a PR to capture output of discussion
    - https://github.com/opencontainers/image-spec/pull/1055
- Discuss language to require implementations not to have an allowlist of media types
    - Aaron will revise the PR based on today's discussion
- _add your items_

### Presentation/Discussion Agenda Items:
- Image-spec 1.1.0 milestone: <https://github.com/opencontainers/image-spec/milestone/14>
- Distribution-spec 1.1.0 milestone: <https://github.com/opencontainers/distribution-spec/milestone/6>
- _add your items_

### Notes:
From the chat:
00:08:10	John Kjell:	Proper sorting enabled for when we get to rc.10 😂
00:13:02	Josh Dolitsky:	:drake-no:
00:16:13	Brandon Mitchell:	Semver++
00:16:42	Jason Hall:	TIL https://semver.org/spec/v2.0.0-rc.2.html
00:17:22	Brandon Mitchell:	We need tianon
00:17:40	Samuel Karp:	Time for a governance change to support github?
00:18:11	Josh Dolitsky:	jon, you could have just said we have quorum and nobody would have challenged
00:19:04	Samuel Karp:	me neither...
00:19:33	Josh Dolitsky:	youll hear from the lawyers
00:19:40	Brandon Mitchell:	The commit to tag is the one before the dev
00:19:53	Jason Hall:	lol are there GG maintainers?
00:20:00	Brian Goff:	So was reader ❤️
00:20:35	Josh Dolitsky:	The HTML/PDF artifacts have been uploaded here: https://github.com/opencontainers/distribution-spec/releases/tag/v1.1.0-rc.2
00:20:41	Josh Dolitsky:	skipped the malware this time
00:20:43	Mike Brown:	Reacted to "The HTML/PDF artifac..." with 👍
00:22:04	Samuel Karp:	Reacted to "So was reader ❤️" with 😂
00:22:39	Jason Hall:	wow josh is a lot better at this
00:23:09	Josh Dolitsky:	we need brandon back on the bike
00:23:24	Jon Johnson:	v1.1.0-rc.3'
00:23:25	Jon Johnson:	v1.1.0-rc.3
00:24:17	Jon Johnson:	https://github.com/opencontainers/image-spec/releases/tag/v1.1.0-rc.3
00:25:00	Jason Hall:	let's fork semver
00:25:07	Jon Johnson:	slimver
00:25:08	Aaron Friel:	wow what a take to join the call to
00:25:25	Aaron Friel:	What are we currently discussing?
00:27:18	Brandon Mitchell:	Wsaaaaaaaaaaaaaaaammmmm
00:27:29	Josh Dolitsky:	dont text and drive plz
00:27:51	Brandon Mitchell:	Reacted to "dont text and drive ..." with 😂
00:31:45	Brandon Mitchell:	Every registry today has a manifest allow list
00:34:43	Brandon Mitchell:	There's a difference between the media type and config media type


## April 20, 2023

Canceled for KubeCon EU

## April 19, 2023
### In person meeting at KubeCon EU

Open Container Initiative Meeting
Date: Wednesday, April 19
Time: 2:30pm - 5:00pm (5:30am PT / 8:30am ET)
Room: D203-204

https://hackmd.io/31EBLRysR8OQLZyH82LDdg

## April 13, 2023

**Recording**: https://youtu.be/Bx-urZXikMk

### Attendees:
- Brandon Mitchell
- Ramkumar Chinchani
- Jon Johnson
- Josh Dolitsky
- Tianon Gravi
- Victor Lu
- Derek McGowan
- Syed Ahmed
- Michael Brown
- Sajay Antony
- Mike Brown (IBM)
- _add yourself_

### Note Taker:
- _add note taker_

### Actionable Agenda Items:
- Who's taking notes?
- PRs needing review for next release:
  - Nits and shifting layer requirements: <https://github.com/opencontainers/image-spec/pull/1042>
  - Add artifactType to image manifest: <https://github.com/opencontainers/image-spec/pull/1043>
  - Define artifactType usage in referrers API response: <https://github.com/opencontainers/distribution-spec/pull/395>
- Distribution spec 1.1 release? (Josh)
  - <https://github.com/opencontainers/distribution-spec/milestone/6>
- _add your items_

### Presentation/Discussion Agenda Items:
- _add your items_

### Notes:

From chat:
00:10:57	Josh Dolitsky:	in the spec:
It MUST match the following regular expression:

^[0-9]+-[0-9]+$
00:12:41	Tianon Gravi:	fwiw, I've seen non-container-related HTTP implementations make this same mistake with Range headers (as a datapoint of it being semi-common, despite the HTTP spec)
00:14:27	Tianon Gravi:	something something "strict in what you send, generous in what you accept" (probably the reason this has happened in so many places in the first place)
00:19:16	Josh Dolitsky:	Ok, this is is ready for green clicky https://github.com/opencontainers/distribution-spec/pull/401

@jon @derek @brandon
00:21:16	Tianon Gravi:	https://github.com/opencontainers/image-spec/pull/1023
00:23:52	Sajay Antony:	https://github.com/opencontainers/image-spec/pull/1023#issuecomment-1428455309
00:31:35	Josh Dolitsky:	need to drop 👋
00:34:08	Ramkumar Chinchani:	LGTM
00:39:11	Tianon Gravi:	the only merge conflict appears to be from the other PR we merged today 😄
00:39:47	Tianon Gravi:	"artefact manifest"
00:40:27	Sajay Antony:	Reacted to ""artefact manifest"" with 😂
00:40:32	Mike Brown:	aRtifact
00:40:44	Brandon Mitchell:	add 😂
00:40:45	Michael Brown:	ærtifact
00:42:01	Tianon Gravi:	https://github.com/opencontainers/image-spec/compare/85f34e9bc20cc8d1e75dbc3c2c2d4059a26a7ae9..63b8bd02f5b5a2ce464a9a8ea6df049c326ce20f is the link GitHub provides
00:42:11	Tianon Gravi:	you click on the "force-pushed" part of the text
00:42:41	Tianon Gravi:	I _really_ wish GitHub would do something better there for things that include both a rebase _and_ other changes 🙃
00:43:28	Sajay Antony:	Reacted to "I _really_ wish GitH..." with 👍🏼
00:44:54	Sajay Antony:	Can we merge - https://github.com/opencontainers/distribution-spec/pull/395/files
00:47:58	Tianon Gravi:	maybe we can add https://github.com/opencontainers/image-spec/pull/1020 to the list to discuss?  before I hit approve on it and put Brandon even further in a corner 😄
00:57:15	Tianon Gravi:	why don't GitHub's reactji have 😭 yet 😂
01:01:35	Sajay Antony:	Index of signatures for multi-arch.
01:05:07	Sajay Antony:	If artifact type was there in index. CNAB folks discussion would have been really easy.
01:06:09	Jon Johnson:	Reacted to "If artifact type was..." with 👍

## April 6, 2023

**Recording**: https://youtu.be/I6EgMx-rdBE

### Attendees:
- _add yourself_
- Scott Rigby (can attend 2nd half of the meeting)
- Ramkumar Chinchani
- Mike Brown (IBM)
- Aaron Friel
- Toddy Mladenov
- Sajay Antony
- Vincent Batts
- Scott Rigby
- Jason Hall
- Andrew Block
- Tianon Gravi
- Jon Johnson
- Derek McGowan
- Brian Goff
- Steve Lasker
- Michael Brown
- John Kjell
- 

### Note Taker:
- _add note taker_

### Actionable Agenda Items:
- Who's taking notes?
- _add your items_

### Presentation/Discussion Agenda Items:
- _add your items_
- [Scott Rigby] I would like to discuss the best ways(s) for cross-polination with CNCF around OCI artifacts. There is a proposed CNCF Working Group on improving OCI Artifacts for cloud native App Delivery (possibly using extensions, mostly likely implemented as a sub-project of ORAS, but definitely including end user improvements such as search and discovery). Please see this GitHub issue: https://github.com/cncf/tag-app-delivery/issues/
  - Goal: how to search for artifacts
- Adding artifactType to image manifest: https://github.com/opencontainers/image-spec/pull/1043
- Using artifactType in referrers response: https://github.com/opencontainers/distribution-spec/pull/395
- Tianon is now a maintainer: https://github.com/opencontainers/image-spec/pull/1044

### Notes:

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
