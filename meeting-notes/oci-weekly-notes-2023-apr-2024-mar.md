# OCI Weekly Dev Meeting Notes Archive - April 2023 to March 2024

## March 28, 2024

**Recording**: https://youtu.be/kmpbLsC4C_o

### Attendees:
- Brandon Mitchell
- Tianon
- Ramkumar Chinchani
- Phil Estes
- Brian Goff
- Toddy
- Sajay Antony
- Mike Brown
- _add yourself_

### Actionable Agenda Items:
- Who's taking notes?
- _add your items_

### Presentation/Discussion Agenda Items:
- Reminder about Container Plumbing Days 2024 (Open Source Summit NA adjacent event, April 15, 2024) - topics for table discussions (Phil)
- Blog post for 1.1 releases (Brandon): <https://github.com/opencontainers/opencontainers.org/pull/152>
- image-spec:
  - Clarify syntax for `artifactType` and `mediaType` fields in manifests (Brandon): <https://github.com/sigstore/cosign/pull/3622>
  - Platform variants, ready to merge? (Brandon): <https://github.com/opencontainers/image-spec/pull/1172>
      - Mike todo.. connect with IBM Z team to add s390x and Z os variants
  - gradle-oci implementation needs reviews: <https://github.com/opencontainers/image-spec/pull/1156>
  - Go versions needs reviews: <https://github.com/opencontainers/image-spec/pull/1170>
  - jonboulle emeritus vote: <https://github.com/opencontainers/image-spec/pull/1179>
- distribution-spec:
  - port separator, okay to close?: <https://github.com/opencontainers/distribution-spec/pull/498>
  - TOC ordering, review needed: <https://github.com/opencontainers/distribution-spec/pull/471>
  - release process, review needed: <https://github.com/opencontainers/distribution-spec/pull/460>
  - tag pagination, does the recommended limit need to be dropped, and should a suggestion for clients to use the link header be added? (Brandon): <https://github.com/opencontainers/distribution-spec/pull/470>

### Notes:
- {Phil} Please look into attending [Container Plumbing Days in Seattle](https://events.linuxfoundation.org/container-plumbing-days/) next month on April 15th. Ticket price $100 for the one day event. Please send topics for the 2 OCI-specific 45-minute discussion slots at the end of the day's schedule. Feel free to start a thread in #general on OCI Slack if you want to discuss topics or ping me. 

Zoom chat:

00:09:11        Phil Estes:     https://events.linuxfoundation.org/container-plumbing-days/program/schedule/
00:14:28        Sajay Antony:   I image the blog to be a summary and have folks to go to the spec? If there is a clarification needed it would be better to address in the spec or have an issue to track it.
00:15:38        Brandon Mitchell:       https://github.com/sigstore/cosign/pull/3622
00:29:51        Brandon Mitchell:       https://github.com/tonistiigi/go-archvariant
00:30:03        Brandon Mitchell:       https://tip.golang.org/wiki/MinimumRequirements#microarchitecture-support
00:33:18        Brandon Mitchell:       https://github.com/opencontainers/image-spec/pull/1172
00:35:14        Phil Estes:     Tianon, anyone in the world can fill out this form and maybe get a login to the z system at Marist College! :) :) https://linuxone.cloud.marist.edu/#/register?flag=VM
00:36:32        Brandon Mitchell:       https://github.com/opencontainers/image-spec/pull/1156
00:37:40        Ramkumar Chinchani:     best if it comes directly from "gradle" community if there is one
00:38:44        Phil Estes:     Solomon shared a super old photo from his mom’s basement in Paris at KubeCon during his keynote! There really was a “Docker was started in my mom’s basement” moment!
00:40:34        Tianon (he/him):        Changes/Optimized Binaries for the AMD64 Architecture - Fedora Project Wiki might have been the thing I was thinking of earlier (which was ultimately rejected)
00:42:31        Tianon (he/him):        ooh, mwhudson with Optimising Ubuntu performance on amd64 architecture | Ubuntu 🙌

## March 22, 2024 - KubeCon EU

**Recording**: https://youtu.be/u1jeqfmX2BA

KubeCon EU Onsite details:
  - Room: E04 
  - Date: Friday 22 March 
  - Time: 14:00 - 16:00 Meeting (CEST) 6am Pacific / 9am Eastern 
  - Name: Open Container Initiative Meeting
  - Convert to your timezone: <https://dateful.com/time-zone-converter?t=2pm&d=2024-03-22&tz2=Central-European-Time-CET>

### Attendees:
- Brandon Mitchell
- Phil Estes
- Akihiro Suda
- Akhil Mohan
- Alexander Kanevskiy
- Marcin Franczyk
- Toru Komatsu
- Peter Hunt
- Victor Lu
- Giuseppe Scrivano
- Mike Brown
- _add yourself_

### Actionable Agenda Items:
- Who's taking notes?
- _add your items_

### Presentation/Discussion Agenda Items:
- Blog post for image/dist 1.1.0 releases <https://github.com/opencontainers/opencontainers.org/pull/152>
- vTPM specification and support PR - https://github.com/opencontainers/runc/pull/1591
- Next in person event: <https://events.linuxfoundation.org/container-plumbing-days>
- _add your items_

### Notes:
- Runtime discussion on an OCI notation for a group of containers (e.g. a Pod)
  - Group multiple containers
  - Share namespaces
  - Control startup order (sidecars)
  - Could annotations be used?
- crio: would containerd consider alternatives to ttrpc/grpc
- WG Image Compatibility
  - Two different problems, runtime image selection, and node selection / cluster provisioning for schedulers
  - Schedulers may want the k8s pod spec or docker compose file
  - Schedulers today are not aware of the image config, they don't pull that content from the registry when deciding where to run the image
- _add your notes_

## March 21, 2024

Meeting canceled for KubeCon EU. Onsite event on the 22nd with remote participation.

## March 14, 2024

**Recording**: https://youtu.be/jBHDN2_2JHg

### Attendees:
- Bjorn Neergaard
- Brian Goff
- Josh Dolitsky
- Tianon
- Brandon Mitchell
- Michael Brown
- Jeff Carter
- Ramkumar Chinchani
- Jon Johnson
- _add yourself_

### Note Taker:
- _add note taker_

### Actionable Agenda Items:
- Cancel March 21 meeting for KubeCon
- Agenda needed for March 22 meeting at Kubecon
- Open Container Initative at KubeCon now on the OCI calendar: 
  Room: E04 
  Date: Friday 22 March 
  Time: 14:00 - 16:00 Meeting (CEST) 6am Pacific/8am Eastern 
  Name: Open Container Initiative Meeting
- _add your items_

### Presentation/Discussion Agenda Items:
- Conformance tests leaking authentication details in logs
  - <https://github.com/opencontainers/distribution-spec/pull/523>
- Blog post for image and distribution 1.1.0 release
- Tag pagination next steps
  - <https://github.com/opencontainers/distribution-spec/issues/461>
  - <https://github.com/opencontainers/distribution-spec/pull/496>
  - <https://github.com/opencontainers/distribution-spec/pull/470>
- Features requested for a future tag listing API
  - Listing untagged manifests by digest
  - Listing content by annotation and artifact type
  - Extensible JSON format to allow statistics (pull count)
  - Tag history: what digests has a tag previously had, and what tags has a digest ever had
- _add your items_

### Notes:
- _add your notes_

## March 7, 2024

**Recording**: https://youtu.be/qbzi8trVHk4

### Attendees:
- Bjorn Neergaard
- Michael Brown
- Tianon
- Brandon Mitchell
- Ramkumar Chinchani
- Brian Goff
- Jon Johnson
- Brandon Klein
- Stephen Day
- Sajay Antony
- Amye
- Mike Brown
- _add yourself_

### Presentation/Discussion Agenda Items:

- Open Container Initative at KubeCon now on the OCI calendar: 
  Room: E04 
  Date: Friday 22 March 
  Time: 14:00 - 16:00 Meeting (CEST) 6am Pacific/8am Eastern 
  Name: Open Container Initiative Meeting
  Same zoom as always 
- Notation switching to use the referrers API: <https://github.com/notaryproject/notation/issues/892>
- Should the config digest be unique: <https://github.com/opencontainers/image-spec/pull/1173>
- Should the spec clarify runnable vs artifacts: <https://github.com/opencontainers/image-spec/pull/1141>

Zoom chat:

00:05:34        Brian Goff (@cpuguy83): Are you back at Docker?
00:05:44        Stephen Day:    Replying to "Are you back at Dock..." I am!
00:05:50        Brian Goff (@cpuguy83): Replying to "Are you back at Dock..." Wow, congrats!
00:08:00        Tianon (he/him):        hard relate, jon
00:09:27        Bjorn Neergaard:        distribution/distribution? not last I checked
00:11:28        Sajay Antony:   Is there a work item on distribution @Bjorn Neergaard?
00:11:53        Tianon (he/him):        Proposal: References support · Issue #3716 · distribution/distribution (github.com)
00:12:08        Sajay Antony:           We are waiting for the stable release to be cut. The whole reference effort by OCI has been plagued with broken ideas and endless discussions. There is still one contentious point that needs be resolved.
00:13:01        Bjorn Neergaard:        aha: https://github.com/distribution/distribution/pull/3834
00:14:16        Brandon Mitchell:       One hair on fire event at a time. :D
00:14:36        Bjorn Neergaard:        https://containerplumbing.org/
00:18:15        Brandon Mitchell:       https://github.com/notaryproject/notation/issues/892
00:18:55        Amye Scavarda Perrin:   Bjorn, I dropped a note over to the events team that’s on that event. I suspect it’s someone not LF running that page because we also have https://events.linuxfoundation.org/container-plumbing-days/program/schedule/
00:19:26        Bjorn Neergaard:        RH might still own that page? It hasn’t been updated for $CURRENT_DATE unlike events.linuxfoundation.org (e.g. registration, CfP) for sure
^ always an ongoing concerninchani:     https://xkcd.com/927/
00:19:42        Sajay Antony:   The tag schema is the only thing that works out in the open.
00:19:50        Amye Scavarda Perrin:   Reacted to "https://xkcd.com/927..." with 😄
00:20:01        Amye Scavarda Perrin:   Replying to "RH might still own t..." Probably, I’ll go darken Josh’s door
00:22:08        Bjorn Neergaard:        Replying to "Bjorn, I dropped a n..." Hmm
00:22:15        Bjorn Neergaard:        Replying to "Bjorn, I dropped a n..." OCI Meeting (Topics to be Announced) on the agenda
00:23:47        Ramkumar Chinchani:     Next "big" items to tackle?
00:24:02        Stephen Day:    I’ll be at CPD
00:24:55        Brandon Mitchell:       https://github.com/opencontainers/image-spec/pull/1173
"container runnable" != "wasm runnable" "runnable" implies there is a "runtime"
00:29:22        Ramkumar Chinchani:     set intersection(container, wasm, etc) = "love OCI's content-addressable packaging and distribution so I don't have to invent a new one"?
00:30:10        Brandon Mitchell:       James Sturtevant
00:30:17        Bjorn Neergaard:        aha, thank you!
00:31:30        Brandon Mitchell:       The WASM config from last week's discussion: https://docs.google.com/document/d/1bZLjDpcG22PruvSUxGH-DNL906GEV0fYIbHQH7eNzqs/edit#heading=h.viatyeiazr3p
00:32:41        Bjorn Neergaard:        That’s what it says
00:32:48        Bjorn Neergaard:        `application/vnd.oci.image.config.v1+json`
00:34:15        Tianon (he/him):        the manifest digest is that element of "unique hash that joins layers", right?  if we update my PR, I think we should update it to discourage _new_ runtimes from applying the same broken meaning to this config digest
00:35:47        Tianon (he/him):        Replying to "the manifest digest ..." for example, in Moby, the containerd integration is removing this and preferring the appropriate manifest digests instead, which are the actual content-addressable element that combines all the things correctly
00:36:12        Bjorn Neergaard:        Replying to "the manifest digest ..." I don’t know enough about containers/storage these days to say if this is an issue there, but it might be unless they refactored that bit
00:37:25        Stephen Day:    Replying to "the manifest digest ..." There’s an old blog post from Tonis that explains this. https://github.com/opencontainers/image-spec/issues/482 might help here. Short answer: it uniquely identifies the resulting filesystem, without the container configuration. The snapshotted in containerd may make this not a problem.
00:43:13        Stephen Day:    https://github.com/opencontainers/image-spec/blob/main/config.md#imageid
00:44:43        Bjorn Neergaard:        Oh no, relying on me to try to define “runnable” to everyone’s satisfaction 😂
00:45:49        Mike Brown:     thx.. ok is there ;)
00:46:19        Bjorn Neergaard:        https://github.com/kubernetes/cri-api/blob/30022f215cd7c176a48d567186d153476fc46f7b/pkg/apis/runtime/v1/api.proto#L784-L798
00:47:23        Stephen Day:    There are cases where a config exists but the manifest does not
00:47:30        Brandon Mitchell:       Fix all the things! :D
00:48:32        Bjorn Neergaard:        Not in moby
00:48:36        Bjorn Neergaard:        everything needs a manifest
00:50:13        Mike Brown:     :-O
00:51:51        Mike Brown:     https://github.com/opencontainers/image-spec/pull/1141#discussion_r1508321727
00:53:23        Ramkumar Chinchani:     we already have cosign signatures
00:54:38        Brandon Mitchell:       cosign is in a separate manifest, not in the same multi-platform index.


## February 29, 2024

**Recording**: https://youtu.be/6O29ouM_inA

### Attendees:
- Tianon
- Brandon Mitchell
- Derek McGowan
- Phil Estes
- Ramkumar Chinchani
- Brandon Klein
- Amye
- Brian Goff
- James Sturtevant
- Jon Johnson
- Sajay Antony
- Michael Brown
- Mike Brown (IBM)
- Bjorn Neergaard
- Stephen Day
- _add yourself_

### Note Taker:
- _add note taker_

### Actionable Agenda Items:
- Who's taking notes?
- _add your items_

### Presentation/Discussion Agenda Items:
- WASM is defining a custom config, separate media type
  - <https://docs.google.com/document/d/1bZLjDpcG22PruvSUxGH-DNL906GEV0fYIbHQH7eNzqs/edit>
  - Is the `rootFS` field used by registries or other tools that would parse the config json
  - Are there other fields that registries and tools parsing arbitrary json would want (this is not an OCI config schema or media type)
  - Is there a need for this to be unique? (e.g. docker image ID)
- Extending platform: <https://github.com/opencontainers/image-spec/pull/1172>
- _add your items_

### Notes:
- Container Plumbing Day: https://containerplumbing.org/
  - LF-managed event on Monday, April 15, 2024 in Seattle, WA
  - Schedule will be announced in a few days; will include 2 45-minute OCI "meetings"
  - (Phil) would love topic ideas/what to give as titles for these 2 blocks
  - (Phil) hoping to make it interesting to draw attendance from broader CPD attendees and not just traditional OCI participants
  - (Phil) would like to have discussion tables with topics inside each of these 45 minute blocks so people have options based on interests; please share ideas

Zoom chat:

00:09:01        Tianon (he/him):        hard to say folks who aren't part of the OCI should come when folks who _are_ don't either, Phil 👀😂❤️ (this is entirely in jest; it's good to see you here Phil 🙂)
00:09:16        Amye Scavarda Perrin:   (If you’re not here please raise your hand)
00:11:38        Tianon (he/him):        all the good comments
00:11:51        Phil Estes:     And I would be on video (and even turned it on) but realized my lid is closed using external monitor :) oops
00:11:58        Phil Estes:     Amazon office so no webcam here :)
00:14:17        Brian Goff (@cpuguy83): They want rootfs AND wasm components as distinct things, IIRC.
00:16:51        Ramkumar Chinchani:     why not align this with "artifacts"? except it is "runnable"?
00:18:20        Tianon (he/him):        found it! https://github.com/opencontainers/image-spec/blob/v1.1.0/config.md#imageid
00:19:30        Tianon (he/him):        we should probably update the guidance somewhere to clarify that it's recommended for "runnable images" to make sure their config blob is ~unique, even if they're not usin
g our config schema
00:21:47        Sajay Antony:   Replying to "we should probably u…" Does this conflict with Empty config?
00:21:51        Phil Estes:     For those who showed up later, I made a call for ideas for the OCI discussion/meeting slots at Container Plumbing Days in April associated with Open Source Summit NA in Seattle (w
eek of April 15th); I added more detail to the notes for those that missed my monologue :) https://hackmd.io/El8Dd2xrTlCaCG59ns5cwg
00:22:18        Sajay Antony:   Replying to "we should probably u…" Or are we qualifying for runnable?
00:23:14        Ramkumar Chinchani:     Replying to "we should probably u..." artifactType=some-runnable-X? and do whatever you want
00:23:46        Ramkumar Chinchani:     Reacted to "For those who showed..." with 👍
00:28:06        Phil Estes:     Not to mention the ongoing discussions in the image compat WG :) :)
00:29:05        Bjorn Neergaard:        oh, goodie, are we talking about the debian arm architecture names? 😄
00:32:37        Bjorn Neergaard:        The feature in glibc to which I referring is called HWCAPS
00:32:37        Bjorn Neergaard:        https://www.phoronix.com/news/Glibc-2.33-Coming-HWCAPS
00:32:40        Phil Estes:     TIL: you can say ABI as “abbey”
00:32:57        Amye Scavarda Perrin:   lol
00:33:05        Tianon (he/him):        I'll start saying "jit" instead of "git" to compensate
00:33:16        Tianon (he/him):        "yavascript"
00:35:24        Phil Estes:     Ppc64le is an IBM decision that it was too hard to keep sending people to upstream projects to get stuff to be big-endian compatible (submitting PRs, etc), so since the chip can boot in either mode, they have basically migrated the whole PPC64 world to “le” and made distro/OSS support easier. I don’t think you will ever find anyone trying to boot in big endian anymore
00:35:57        Tianon (he/him):        tonistiigi/go-archvariant (github.com)
00:36:14        Stephen Day:    Where is the calendar invite for this meeting?
00:36:49        Bjorn Neergaard:        I had to work with MIPSBE when I was doing network devices… And I had the same uBoot tree that had to boot and handle packets both in BE and LE mode… But that’s a pretty s
pecific niche 😄
00:37:32        Tianon (he/him):        made a "strawman" PR about ImageID based on our discussion: https://github.com/opencontainers/image-spec/pull/1173
00:37:34        Bjorn Neergaard:        https://calendar.google.com/calendar/ical/linuxfoundation.org_i0sado0i37eknar51vsu8md5hg%40group.calendar.google.com/public/basic.ics
00:37:43        Phil Estes:     I need to drop :-]
00:37:58        Tianon (he/him):        👋bye Phil s390x Estes!!
00:38:02        Tianon (he/him):        you'll always be s390x in my heart
00:38:03        Brandon Mitchell:       https://hackmd.io/060HKC3DTV-NzzewNQbHCg
00:38:16        Phil Estes:     Ha Tianon! I haven’t logged into a mainframe for … years :) :)
00:38:25        Tianon (he/him):        noooo, my ears are plugged
00:39:48        Amye Scavarda Perrin:   https://tockify.com/cncf.public.events/monthly may be helpful to you
00:39:53        James Sturtevant:       (search for wasm on https://www.cncf.io/calendar/)
00:40:42        Amye Scavarda Perrin:   https://tockify.com/cncf.public.events/detail/698/1710255600000
00:42:13        Brandon Klein:  Is this still valid? https://opencontainers.org/community/overview/#open-meetings
00:43:03        Mike Brown:     https://github.com/opencontainers/.github?tab=readme-ov-file#meetings
00:44:01        Brandon Mitchell:       This may be the OCI calendar link: https://calendar.google.com/calendar/embed?src=linuxfoundation.org_i0sado0i37eknar51vsu8md5hg%40group.calendar.google.com&ctz=America%2FNew_York

## February 22, 2024

**Recording**: https://youtu.be/Yl8eekrUhuI

### Attendees:
- Tianon
- Brandon Mitchell
- Jesse Butler
- Marcin Franczyk
- Michael Brown
- Brandon Ha
- Syed Ahmed
- Mike Brown
- Brian Goff
- _add yourself_

### Note Taker:
- _add note taker_

### Actionable Agenda Items:
- Who's taking notes?
- _add your items_

### Presentation/Discussion Agenda Items:
- Blog post for image and distribution spec releases needed
- Add Ram as a maintainer: <https://github.com/opencontainers/distribution-spec/pull/516>
- Referrers response in an OCI Layout: <https://github.com/opencontainers/image-spec/pull/1171>
- _add your items_

### Notes:
- _add your notes_

## February 15, 2024

**Recording**: https://youtu.be/BOCN72bfnXM

### Attendees:
- Brandon Mitchell
- Tianon
- Josh Dolitsky
- Derek McGowan
- Michael Brown
- Brian Goff
- Greg Wallace
- Jeff Carter
- Sajay Antony
- Jesse Butler
- Stephen Day
- Ramkumar Chinchani
- Mike Brown
- _add yourself_

### Note Taker:
- _add note taker_

### Actionable Agenda Items:
- image-spec 1.1.0 release:
  - https://github.com/opencontainers/image-spec/pull/1161
- distribution-spec 1.1.0 vote:
  - https://github.com/opencontainers/distribution-spec/pull/507
- _ Add your item here_

### Presentation/Discussion Agenda Items:
- Greg W. has volunteered to help document/coordinate the FreeBSD runtime extension WG. Any tips, or process I should follow?
  - coordinate with Sam

### Notes:
- _add your notes_

## February 8, 2024

**Recording**: https://youtu.be/eoWdtdD1mZc

### Attendees:
- Ramkumar Chinchani
- Brandon Mitchell
- Sajay Antony
- Marcin Franczyk
- Jeff Carter
- Jesse Butler
- Tianon
- Ramkumar Chinchani
- Brandon Caton
- Brandon Klein
- Brian Goff
- Toddy
- _add yourself_

### Note Taker:
- _add note taker_

### Actionable Agenda Items:
- image-spec 1.1.0 and distribution-spec 1.1.0 GA votes
  - https://github.com/opencontainers/image-spec/pull/1161
  - https://github.com/opencontainers/distribution-spec/pull/507
- _add your items_

### Presentation/Discussion Agenda Items:
- _add your items_

### Notes:
- Image compatibility requirements: <https://github.com/opencontainers/wg-image-compatibility/blob/main/docs/REQUIREMENTS.md>
- Discussion on a search interface
- _add your notes_

## February 1, 2024

**Recording**: https://youtu.be/ECyKp0Ry0K4

### Attendees:
- Brandon Mitchell
- Tianon
- Sajay Antony
- Brandon Caton
- Ramkumar Chinchani
- Josh Dolitsky
- Giuseppe Scrivano
- Syed Ahmed
- Mike Brown (IBM)
- _add yourself_

### Note Taker:
- _add note taker_

### Actionable Agenda Items:
- Who's taking notes?
- _add your items_

### Presentation/Discussion Agenda Items:
- runc CVE: <https://github.com/opencontainers/runc/security/advisories/GHSA-xr7r-f8xq-vfvv>
- TOB Chair Election: <https://github.com/opencontainers/tob/issues/143#issuecomment-1918191387>
- image-spec 1.1.0 and distribution-spec 1.1.0 GA releases
    - https://github.com/opencontainers/image-spec/pull/1161
    - https://github.com/opencontainers/distribution-spec/pull/507
- Annotation for referrers in a Layout
- _add your items_

### Notes:
- _add your notes_

## January 25, 2024

**Recording**: https://youtu.be/lBjh-22pfuQ

### Attendees:
- Mike Brown (IBM)
- Brandon Mitchell
- Tianon
- Vincent Batts
- Sajay Antony
- Jesse Butler
- Toddy
- Brandon Caton
- Ramkumar Chinchani
- Michael Brown
- Syed Ahmed
- _add yourself_

### Note Taker:
- _add note taker_

### Actionable Agenda Items:
- Who's taking notes?
- _add your items_

### Presentation/Discussion Agenda Items:
- distribution-spec 1.1.0-rc4: <https://github.com/opencontainers/distribution-spec/pull/502>
    - review outstanding items / maintainer comments (e.g. [from mikebrow](<https://github.com/opencontainers/distribution-spec/pull/502#pullrequestreview-1825007960>))
        - Discussing/working jon/mike/sajay 
- We have space at KubeCon Paris - Friday afternoon from 2pm to 4pm so as to be slightly friendly to other timezones. 
    - Agenda items for that? 
- _add your items_

### Notes:

Zoom chat:

00:04:05	Jesse Butler:	Huh weird. I cannot turn on video or unmute.
00:04:18	Jesse Butler:	So odd!
00:04:35	Jesse Butler:	I know there’s tons of settings on the server - and they change them weirdly
00:27:21	Sajay Antony:	Its more about the semantic about "NOT EXIST" basically it might not be pushed to the registry.
00:27:47	Vincent Batts:	Maybe even just ensuring error types including "object doesn't exist"
00:28:28	Sajay Antony:	WE have a similar error that Jon pointed out - MAY return MANIFEST_NOT_FOUND.
00:28:56	Sajay Antony:	But if return the error then we losen up the MUST ACCEPT construct.
00:31:39	Brandon Mitchell:	"This value defines a loose relationship to a separate DAG, used by the referrers API"
00:31:58	Jesse Butler:	Reacted to ""This value defines ..." with 👍
00:32:54	Michael Brown:	I like it
00:34:45	Ramkumar Chinchani:	Garbage collection is not a convergent conversation
00:34:52	Brandon Mitchell:	Reacted to "Garbage collection i..." with 👍
00:35:29	Michael Brown:	Nobody’s burnt out now
00:36:15	Vincent Batts:	Reacted to Nobody’s burnt out n... with "😱"
00:36:16	Tianon (he/him):	that's why we have so many maintainers on this call, right? 🙈
00:36:40	Jesse Butler:	Reacted to "that's why we have s..." with 😃
00:36:47	Sajay Antony:	Brandon, do you want to make the PR for one minor change. Its a minor clarification. The remaining clarification of verification can be in 1.2.
00:46:26	Brandon Mitchell:	"A registry MUST accept an otherwise valid manifest with a subject field that references a manifest that does not exist _in the repository_"
00:46:38	Jesse Butler:	Reacted to ""A registry MUST acc..." with 👍
00:47:09	Jesse Butler:	Might even start with “To support the weak reference relationship of referrers, …” or similar?
00:47:47	Jesse Butler:	“The DAG” which DAG lol
00:48:39	Tianon (he/him):	Replying to "“The DAG” which DAG ..."

"dag nabbit"
00:48:55	Sajay Antony:	I'm not too keen on  calling out the DAG  in 1.1
00:49:05	Sajay Antony:	But won't object.
00:49:15	Jesse Butler:	Reacted to "I'm not too keen on ..." with ❤️
00:51:51	Tianon (he/him):	and the content is explicitly content addressable, so changing it is not great
00:52:04	Tianon (he/him):	(that's new content at that point)
00:52:45	Brandon Mitchell:	"registry must initially accept"
00:53:41	Sajay Antony:	The magic one second delay.
00:53:59	Michael Brown:	😱
00:54:30	Ramkumar Chinchani:	Reacted to I'm not too keen on ... with "❤️"
00:54:48	Michael Brown:	If we release this, I’ll join Brandon in saying that Sajay is my favorite registry operator too.
00:54:49	Tianon (he/him):	200 OK straight to /dev/null
00:55:45	Brandon Mitchell:	I'm tempted to write that /dev/null registry now
00:56:20	Brandon Mitchell:	Reacted to "200 OK straight to /..." with 😀
00:58:04	Tianon (he/him):	Replying to "I'm tempted to write..."

I can vouch for https://pkg.go.dev/cuelabs.dev/go/oci/ociregistry being really ergonomic and easy if you're serious 🙂
00:58:51	Tianon (he/him):	Replying to "I'm tempted to write..."

(source code in https://github.com/cue-labs/oci/tree/main/ociregistry - their vanity imports confuse godoc for some reason)

## January 18, 2024

**Recording**: https://youtu.be/2UyUEBCxH0A

### Attendees:
- Tianon
- Brandon Mitchell
- Josh Dolitsky
- Marcin Franczyk
- Sajay Antony
- Ramkumar Chinchani
- Brandon Caton
- Jesse Butler
- _add yourself_

### Note Taker:
- _add note taker_

### Actionable Agenda Items:
- Who's taking notes?
- _add your items_

### Presentation/Discussion Agenda Items:
- image-spec 1.1.0-rc6: <https://github.com/opencontainers/image-spec/pull/1157>
- distribution-spec 1.1.0-rc4: <https://github.com/opencontainers/distribution-spec/pull/502>
- WG-Auth discussion on multiple auth headers: <https://github.com/opencontainers/wg-auth/issues/12>
  - Concerns from RFC: <https://datatracker.ietf.org/doc/html/rfc2617#page-23>
- WG status
  - wg-image-compatibility
  - wg-auth
  - wg-freebsd
- _add your items_

### Notes:
- Releases were generated:
  - <https://github.com/opencontainers/image-spec/releases/tag/v1.1.0-rc6>
  - <https://github.com/opencontainers/distribution-spec/releases/tag/v1.1.0-rc4>
- _add your notes_

## January 11, 2024

**Recording**: https://youtu.be/jl3pXLpDYuU

### Attendees:
- Tianon
- Brandon Mitchell
- Mike Brown (IBM)
- Ramkumar Chinchani
- Brian Goff
- Jesse Butler
- Michael Brown
- James
- Josh Dolitsky
- _add yourself_

### Note Taker:
- _add note taker_

### Actionable Agenda Items:
- TOB election happening, last call for nominations
- _add your items_

### Presentation/Discussion Agenda Items:
- Considering moving missing subject issue to a 1.2 milestone
  - <https://github.com/opencontainers/distribution-spec/issues/459>
- Referrers response to missing manifests, okay to merge?
  - <https://github.com/opencontainers/distribution-spec/pull/491>
  - Mike will open an issue for more granular conformance tests
- OCI-Referrers header, reviews needed
  - <https://github.com/opencontainers/distribution-spec/pull/463>
  - Postpone to 1.2
- Milestone decision for pagination changes
  - <https://github.com/opencontainers/distribution-spec/pull/496>
  - Set as 1.2, it's breaking from 1.0, no advantage including it in 1.1
- Conformance test for blob deletes, review needed
  - <https://github.com/opencontainers/distribution-spec/pull/499>
  - Mike will review
- Milestone looks ready for a new RC once we merge PRs
  - <https://github.com/opencontainers/distribution-spec/milestone/6>
  - Josh is pushing PR for distribution-spec
  - Brandon will work on PR for image-spec
- Josh proposed adding another distribution-spec maintainer
- _add your items_

### Notes:
- _add your notes_

## January 4, 2024

**Recording**: https://youtu.be/W9e8sjPPVlA

### Attendees:
- Brandon Mitchell
- Toddy
- Tianon
- Brandon Ha
- Josh
- Brian Goff
- Marcin Franczyk
- Sajay Antony
- Jon Johnson
- Michael Brown
- James Sturtevant
- Hazem Aldrawsheh
- _add yourself_

### Note Taker:
- _add note taker_

### Actionable Agenda Items:
- Who's taking notes?
- _add your items_

### Presentation/Discussion Agenda Items:
- Remaining tasks for image/distribution 1.1
  - https://github.com/opencontainers/image-spec/milestone/14
  - https://github.com/opencontainers/distribution-spec/milestone/6
- _add your items_

### Notes:
- _add your notes_

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
