# OCI Weekly Dev Meeting Notes Archive - April 2024 to March 2025

## March 27, 2025

**Recording**: https://youtu.be/AKbZPkAzwLU

### Attendees:

- Jory Burson
- Tianon
- Brandon Mitchell
- Samuel Karp
- Sajay Antony
- Brian Goff
- Syed Ahmed
- Jeff Carter

### Actionable Agenda Items:

- Ready for review:
  - Fixing image-spec badge: <https://github.com/opencontainers/image-spec/pull/1251>
- Container Plumbing Days CFP is open, promotions encouraged: <https://groups.google.com/a/opencontainers.org/g/dev/c/lWLddPSeyRU/m/w1KTQ-hLBAAJ>
- KubeCon EU in-person meeting Tuesday, April 1, 10am-11am BST @ Level 1, ICC Prince Regent Room 1

### Presentation/Discussion Agenda Items:

- Should we include non-OCI media types in the spec: <https://github.com/opencontainers/image-spec/pull/1191>

### Notes:

Notes from the zoom chat:

00:10:54	Sajay Antony:	Sorry folks been out of the country for the last 2 weeks so just catching up.
00:12:43	Jory Burson (LF):	KubeCon EU meeting has been added to the cal for April 1
00:12:49	Tianon (he/him):	mounting untrusted filesystems directly into the kernel 🥳  <homer-hides-in-the-hedge.gif>
00:18:50	Sajay Antony:	Thanks all.

## March 20, 2025

**Recording**: https://youtu.be/XojSHq6L0mI

### Attendees:

- Jory Burson
- Tianon
- Brandon Mitchell
- Ramkumar Chinchani
- Brian Goff
- Syed Ahmed

### Actionable Agenda Items:

- Ready for review:
  - Fixing image-spec badge: <https://github.com/opencontainers/image-spec/pull/1251>
- Container Plumbing Days Update
  - Help promote CFP!
  - Boost on LinkedIn / Twitter

### Presentation/Discussion Agenda Items:

- image-spec bumping dependencies: <https://github.com/opencontainers/image-spec/pull/1253>
  - Concerns on bumping the Go version for this considering how much it has been imported.
- distribution-spec conformance dependencies: <https://github.com/opencontainers/distribution-spec/pull/571>
  - Since this is only in conformance, we can likely bump the Go version to get this to build.

### Notes:

Notes from the zoom chat:

00:12:43	Brian Goff (@cpuguy83):	Oh I came at just the right time.
00:14:03	Brian Goff (@cpuguy83):	I have a rant about this every go release.
00:14:11	Tianon (he/him):	the longer I use Go, the more heavily https://fasterthanli.me/articles/i-want-off-mr-golangs-wild-ride resonates with me
00:14:25	Ramkumar Chinchani:	if we disagree with their approach, we should write our own language&compiler
00:16:23	Jory Burson (LF):	Preach. Tianon!

## March 13, 2025

**Recording**: https://youtu.be/bOq246XSSq8

### Attendees:

- Brandon Mitchell
- Tianon
- Miloslav Trmac
- Brian Goff
- Derek McGowan
- Jon Johnson
- Jory Burson
- Samuel Karp
- Jeff Carter

### Actionable Agenda Items:

- Ready for review:
  - Canonical JSON: <https://github.com/opencontainers/image-spec/pull/1249>
    - Merged
  - Fixing image-spec badge: <https://github.com/opencontainers/image-spec/pull/1251>

### Presentation/Discussion Agenda Items:

- Annotation for an "instance" in a source repo: <https://github.com/opencontainers/image-spec/issues/1046>
  - Disagreement on whether this should be part of the source url, a path, a unique instance per image built, or a 3rd party annotation.
- Async delete: <https://github.com/opencontainers/distribution-spec/issues/570>
  - Agreement that 202 means async and implementations may not immediately delete the manifest, PR needed, no volunteers.
  - Jon would like a structured error message when a manifest delete is blocked for data integrity, listing the other digests referencing the content being deleted
- Jory has details for Container Plumbing Days CFP up <https://events.linuxfoundation.org/container-plumbing-days/program/cfp/>
- In-person meeting at KubeCon EU, 10 AM Tuesday April 1

### Notes:

Notes from the zoom chat:

00:29:55	Tianon (he/him):	"As implied by the 202 status code, deletion may happen asynchronously."
00:30:25	Tianon (he/him):	Replying to ""As implied by the 2..." sorry, MAY
00:35:23	Jory Burson (LF):	Tuesday, 1 April, from 10:00-12:00
00:36:37	Jeff Carter:	there is a "I'm a teapot" code, maybe there should be a "i'm a wizard" code
00:36:41	Brian Goff (@cpuguy83):	Because http/2 requires wizardry.
00:40:53	Jeff Carter:	how is the json formatted?
00:42:23	Samuel Karp:	need to drop, thanks
00:42:41	Tianon (he/him):	Replying to "how is the json form..." in the canonical way (as opposed to canonical json)
00:54:22	Tianon (he/him):	I'll blow away those 10 thousand manifests to the tune of the famous disturbed song too

## March 6, 2025

**Recording**: https://youtu.be/pVBydQhEP2E

### Attendees:

- Brandon Mitchell
- Tianon
- Harry Randazzo
- Ramkumar Chinchani
- Brian Goff
- Philip Laine
- Samuel Karp

### Actionable Agenda Items:

none

### Presentation/Discussion Agenda Items:

- Canonical JSON in image-spec: <https://github.com/opencontainers/image-spec/pull/1249>
  - No objections and no other maintainers around to review this week
- In-person meeting at KubeCon EU?
  - Follow up with <operations@opencontainers.org>

### Notes:

From the zoom chat:

00:03:05	Tianon (he/him):	Harry starting right into a landmine 😀
00:03:49	Tianon (he/him):	https://github.com/opencontainers/image-spec/blob/v1.1.1/annotations.md#pre-defined-annotation-keys:~:text=org.opencontainers.image.ref.name
00:08:26	Ramkumar Chinchani:	This SHOULD be a fully qualified reference name, without any assumed default registry. (e.g., registry.example.com/my-org/my-image:tag instead of my-org/my-image:tag). only for base.name?
00:10:49	Tianon (he/him):	@Brian Goff (@cpuguy83) gonna pipe up for his Microsoft friends that he wants UTF-16 instead 😂
00:11:08	Tianon (he/him):	Replying to "@Brian Goff (@cpuguy..." the untold horrors of the Windows ecosystem
00:11:32	Brian Goff (@cpuguy83):	And we're not there 🙂
00:12:18	Harry Randazzo:	Gotta drop early, I'll come next week with more landmines 😅
00:13:50	Brian Goff (@cpuguy83):	Replying to "@Brian Goff (@cpuguy..." 16 is better than 8 right?
00:14:21	Brian Goff (@cpuguy83):	Quick someone say something controversial

## February 27, 2025

**Recording**: https://youtu.be/NWn9I09lx2k

### Attendees:

- Tianon
- Brandon Mitchell
- Brian Goff
- Jeff Carter
- Syed Ahmed
- Sajay Antony
- Harry Randazzo
- W. Trevor King
- Ramkumar Chinchani

### Actionable Agenda Items:

- Vote:
  - image-spec v1.1.1: <https://github.com/opencontainers/image-spec/pull/1247>
  - runtime-spec v1.2.1: <https://github.com/opencontainers/runtime-spec/pull/1278>
- Review needed:
  - Registering blake3 algorithm: <https://github.com/opencontainers/image-spec/pull/1240>

### Presentation/Discussion Agenda Items:

- Including uncompressed layer size in descriptors: <https://github.com/opencontainers/image-spec/issues/1246>
  - Many agree transport level compression is an ideal state.
  - Some concern on supporting range requests.
  - OCI Layout may need to be updated to support compression extensions on blob files to effectively have transport level compression on blobs in a Layout.
- Blob HEAD vs GET: <https://github.com/opencontainers/distribution-spec/issues/569>
  - No objection, this bug violated both HTTP and distribution specs

### Notes:

Notes from the zoom chat:

00:05:34	Brian Goff (@cpuguy83):	Kelvin or bust.
00:09:48	Tianon (he/him):	https://github.com/docker-library/official-images/issues/17720#issuecomment-2450200677
00:13:40	Brian Goff (@cpuguy83):	Much easier to add the field... that said transport layer compression is ideal.
00:15:11	Brian Goff (@cpuguy83):	Oh no, Sajay is gone.
00:15:18	Brian Goff (@cpuguy83):	Oh nevermind,
00:15:25	Brian Goff (@cpuguy83):	UI disappeared.
00:15:34	Sajay Antony:	I'm just staying silent on this one @Brian.
00:16:22	Brian Goff (@cpuguy83):	Good news, Go is going to add content negotiation to the stdlib.
00:17:00	Tianon (he/him):	Replying to "Good news, Go is goi..." https://github.com/golang/go/issues/19307 for folks unfamiliar with that discussion
00:18:10	Sajay Antony:	Server side CPU and compression offloading will really have to evaluated is my guess.
00:18:47	Ramkumar Chinchani:	i am also hearing transcoding?
00:19:28	Brandon Mitchell:	https://github.com/opencontainers/image-spec/blob/main/image-layout.md
00:19:38	Sajay Antony:	Image downloading 5-10GB models onto 100s of VMs.
00:19:54	Sajay Antony:	"Imagine"
00:27:01	Tianon (he/him):	KILL DIFFID
00:27:07	Jeff Carter:	We’ve started to see 150 gb models recently
00:29:42	Brian Goff (@cpuguy83):	Not compressing layers fixes a lot of issues at the runtime side.
00:30:39	W. Trevor King:	I have to drop for another meeting; fun times :)
00:36:39	Tianon (he/him):	Replying to "Not compressing laye..." yeah, for sure -- compression is what makes mounting tarballs hairy (making a map of the files in the tar is trivial otherwise)
00:38:04	Ramkumar Chinchani:	main concern is ... is there enough information at all places (servers and clients) where gzip(gunzip(gzip(blob)) = gzip(blob) etc
00:38:21	Sajay Antony:	Hoops we have to jump through @Brian - containerd/accelerated-container-image: A production-ready remote container image format (overlaybd) and snapshotter based on block-device.
00:41:30	Brandon Mitchell:	Hat tip to Ram for directly asking the question I was too polite to ask. :D
00:49:08	Brian Goff (@cpuguy83):	Definitely my assumption as well.
00:53:07	Brian Goff (@cpuguy83):	I guess in this case the registry would only really be able to store this using the lowest common denominator compression... assuming it wouldn't want to store the same compressed data in 2 (or more) different formats.
00:53:37	Brian Goff (@cpuguy83):	Which makes zstd a no-go here.
00:56:20	Brian Goff (@cpuguy83):	Oh that's a great point, @Tianon (he/him)
00:57:03	Ramkumar Chinchani:	network is cheap/free is a myth - i keep getting ratelimited everywhere there are other cheap/free myths about CPU and memory

## February 20, 2025

**Recording**: https://youtu.be/wlIuxqH818k

### Attendees:

- Jory Burson
- Tianon
- W Trevor King
- Sajay Antony
- Brandon Mitchell
- Josh Dolitsky
- Brian Goff
- Harry Randazzo
- Ramkumar Chanchani
- Samuel Karp
- Mike Brown

### Actionable Agenda Items:

- Review needed:
  - Referrers tag schema: <https://github.com/opencontainers/distribution-spec/pull/563>
  - Registering blake3 algorithm: <https://github.com/opencontainers/image-spec/pull/1240>

### Presentation/Discussion Agenda Items:

- (Josh) Add optional tagType query param to tags list endpoint
    - https://github.com/opencontainers/distribution-spec/pull/568
    - Regex another possibility, but feels messy
- Reformating distribution-spec: <https://github.com/opencontainers/distribution-spec/issues/566>
- Refactoring conformance tests: <https://github.com/opencontainers/distribution-spec/pull/543#issuecomment-2666202571>

### Notes:

Notes from the zoom chat:

00:03:04	Sajay Antony:	Good to see you Josh.
00:06:49	Brian Goff (@cpuguy83):	<shudderas as I look at my Teams window>
00:07:30	Brandon Mitchell:	The browser app is the only way I share a screen in zoom now.
00:19:28	Tianon (he/him):	https://oci.dag.dev/?repo=tomcat 😅  (more advanced filtering would be awesome IMO, but I don't have high confidence that it's realistic to expect registries to implement it)
00:19:49	Sajay Antony:	There are older issues for improved tag listing
00:19:49	Sajay Antony:	 - [RFP] replace catalog API functionality · Issue #22 · opencontainers/distribution-spec
00:19:49	Sajay Antony:	Lexial discussion - Proposal: Allow listing tags in reverse lexical order · Issue #545 · opencontainers/distribution-spec
00:19:49	Sajay Antony:	There have been a lot of request for better tag listing/searching
00:22:26	Tianon (he/him):	image index 👀
00:23:34	Sajay Antony:	John had pointed to GCR manifest/list endpoint in one of those issues and also - docs: initial commit for search extension by rchincha · Pull Request #504 · opencontainers/distribution-spec
00:25:47	Tianon (he/him):	see https://oci.dag.dev/?repo=gcr.io/go-containerregistry/crane for the data GCR provides in practice
00:26:06	Tianon (he/him):	Replying to "see https://oci.dag...." "timeCreatedMs": "-6795364578871", this is adorable though
00:29:36	Tianon (he/him):	https://github.com/opencontainers/distribution-spec/issues/443 + https://github.com/opencontainers/distribution-spec/issues/446
00:31:21	Ramkumar Chinchani:	https://github.com/opencontainers/wg-auth
00:33:56	Ramkumar Chinchani:	Replying to "https://github.com/o..." auth not in the spec is messed up
00:35:37	W. Trevor King:	I think it's worth trying to find things that can improve the conformance tests in a bunch of tiny pivots, instead of trying to address all the sticky points in one big pivot.  Yes, there will be lots of bits that stay sticky until eventually all the issues get polished out, but you aren't hamstrung in the meantime
00:36:53	Sajay Antony:	@Ramkumar Chinchani does zot support 512 manifests?
00:39:32	Ramkumar Chinchani:	Replying to "@Ramkumar Chinchani ..." Yes it does. We moved away from hardcoded digest algos a while ago.
00:41:04	Ramkumar Chinchani:	Replying to "@Ramkumar Chinchani ..." But as always, trust but verify.
00:41:33	Sajay Antony:	NTD for another call folks. Hard to skip that one.
00:43:53	W. Trevor King:	I'm also not Quay, but was poking around re: referrer API pessimisim and found https://www.redhat.com/en/blog/announcing-open-container-initiativereferrers-api-quayio-step-towards-enhanced-security-and-compliance from December
00:44:07	Samuel Karp:	Which redirect?
00:45:33	Samuel Karp:	https://opencontainers.org/about/governance

## February 13, 2025

**Recording**: https://youtu.be/XukRCe16WEU

### Attendees:

- Brandon Mitchell
- Tianon
- Kyle Crane
- Abhishek Jha
- Sajay Antony
- Jory Burson
- Ramkumar Chinchani
- Michael Brown
- Shama Kashyap

### Actionable Agenda Items:

- Review needed:
  - Governance redirect: <https://github.com/opencontainers/opencontainers.org/pull/158>
  - TOB in readme: <https://github.com/opencontainers/tob/pull/146>
  - TOB on website: <https://github.com/opencontainers/opencontainers.org/pull/160>
  - Referrers tag schema: <https://github.com/opencontainers/distribution-spec/pull/563>

### Presentation/Discussion Agenda Items:

- Opentofu is adding OCI artifact support: <https://github.com/opentofu/opentofu/pull/2163>
- Registering blake3 in image-spec: <https://github.com/opencontainers/image-spec/pull/1240>
- Header / identifier for OCI scanners: <https://github.com/opencontainers/distribution-spec/issues/564>
- Reformating distribution-spec: <https://github.com/opencontainers/distribution-spec/issues/566>

### Notes:

Notes from the zoom chat:

00:08:51	Brandon Mitchell:	https://github.com/C2SP/C2SP/blob/main/BLAKE3.md
00:09:40	Jory Burson (LF):	Merging https://github.com/opencontainers/tob/pull/146
00:24:40	Tianon (he/him):	"Go-http-client" shaking my fist at Go
00:28:16	Sajay Antony:	I like the idea of an intent honestly.
00:29:15	Jory Burson (LF):	Brb - need to take a quick call
00:32:21	Tianon (he/him):	retention policies and a truly content-addressable store are concepts that are somewhat at odds, and that is part of why this is a hard conversation we keep having 😄
00:32:53	Sajay Antony:	@Michael @shama - do you folks see scanners being able to produce this header.
00:32:57	Tianon (he/him):	Replying to "retention policies a..." ie, can't have meaningful content-addressable storage if the content you're trying to address goes away 😅
00:37:03	Sajay Antony:	That compounded usecase is what I am concerned about.
00:41:52	Kyle Crane:	I am new to the community.
00:42:03	Sajay Antony:	Good discussion and seems like I got involved in  his and missed an overlapping meeting. NTD folks.
00:42:20	Sajay Antony:	*this -> scanner
00:42:30	Tianon (he/him):	Replying to "I am new to the comm..." at the risk of being a little bit weird, I really love your name and hope you're familiar with https://github.com/google/go-containerregistry/tree/main/cmd/crane  😄❤️
00:45:44	Kyle Crane:	Replying to "I am new to the comm..." Full disclosure, I am working on https://www.signal.fyi/ . Here to make sure I am building in alignment with community best practice. This is the normal name reference I get: https://dyinglight.fandom.com/wiki/Kyle_Crane
00:53:33	Jory Burson (LF):	I came back!
00:56:00	Jory Burson (LF):	DAG-nabbit!

## February 6, 2025

**Recording**: https://youtu.be/tEyIaHmtVlI

### Attendees:

- Mike Brown
- Tianon
- Sajay Antony
- Brandon Mitchell
- Jory Burson
- Ramkumar Chinchani
- Mrunal Patel
- Michael Brown
- W. Trevor King

### Actionable Agenda Items:

- TOB Chair nomination window closing tomorrow: <https://github.com/opencontainers/tob/issues/147>

### Presentation/Discussion Agenda Items:

- Referrers tag schema with alternate hash algorithms:
  - <https://github.com/opencontainers/distribution-spec/pull/563>
  - Algorithms do not have a length limit and may contain separators, both of which can break a tag: <https://github.com/opencontainers/image-spec/blob/main/descriptor.md#digests>
  - Should we limit referrers tag schema to only registered algorithms?
- Should blake3 be registered in image-spec before adding to go-digest?
  - <https://github.com/opencontainers/go-digest/pull/66>
- Ecosystem
  - Docker adding support for mounting images as volumes: <https://github.com/moby/moby/pull/48798>
  - Podman adding support for OCI artifacts: <https://blog.podman.io/2025/01/podman-introduces-support-for-oci-artifacts/>

### Notes:

Notes from the zoom chat:

00:10:44	Brandon Mitchell:	https://github.com/opencontainers/distribution-spec/blob/7872490e9d4943b20f11e21475bc13fd2e02b7d8/spec.md#L164-L166
00:11:48	Ramkumar Chinchani:	Maybe some alg-names are special keywords and become an exception
00:12:01	Sajay Antony:	Do we know why are they using the tag schema?
00:12:43	Tianon (he/him):	a fun example of different ways these length limits become load-bearing in sometimes unexpected ways: https://github.com/goharbor/harbor/issues/15067
00:14:13	Mike Brown:	https://github.com/opencontainers/distribution-spec/pull/256
00:17:06	Jory Burson (LF):	Imma get a Blake3 hat for this call
00:18:48	Tianon (he/him):	Replying to "Imma get a Blake3 ha..." if you actually do so, you should reach out to Jon because he's definitely a hat guy and would probably love this
00:22:36	Brandon Mitchell:	https://github.com/opencontainers/image-spec/blob/fbb4662eb53b80bd38f7597406cf1211317768f0/descriptor.md#L156-L162
00:25:57	Tianon (he/him):	"finding holes in stuff [we] never even considered" is wking's historic OCI legacy 🙂
00:26:30	Sajay Antony:	What client/registry is this facing a problem with?
00:28:02	Tianon (he/him):	Replying to "What client/registry..." given Mrunal is back too, I'm guessing this is FIPS-related (where Uncle Sam has decided that SHA-512 is "post-quantum safe" even though it just moves the goalpost further out) 👀
00:36:21	Ramkumar Chinchani:	Replying to "What client/registry..." isn't all crypto like that?
00:37:56	Tianon (he/him):	Replying to "What client/registry..." sure, but if the goal is explicitly the combination of FIPS compliance and post-quantum, I think there might be other hashing algorithms we should consider as well/instead
00:38:14	Tianon (he/him):	Replying to "What client/registry..." ie, if we have to break a lot of stuff to get SHA-512 working, let's do that work for something more interesting instead
00:41:50	Tianon (he/him):	Replying to "What client/registry..." I talked to a few folks (who I unfortunately couldn't convince to join this call) about post-quantum hashing who have a lot more experience with it than I do (which doesn't take much but it's something), and their honest recommendation was that blake3 is probably worth considering over SHA-512, but with the important caveat that it's not FIPS-approved
00:43:56	Mrunal Patel:	Replying to "What client/registry..." I think it would be best to make it configurable so both aspects are covered. 1. Being compliant with FIPS  2. Using the most secure / best crypto export recommended algorithm that FIPS hasn't caught up to yet.
00:45:37	Tianon (he/him):	Replying to "What client/registry..." the "fractal of complexity" option, yep, I dig it 😁 (that's in-line with how the formats are designed for sure, and I imagine is part of why in-toto's "descriptor" analogue has digests be a list instead of a single value)
00:52:17	Tianon (he/him):	https://github.com/CloudNativeAI/model-spec/blob/main/docs/spec.md fwiw, someone's been listening and these are tar-based 🙂
00:53:30	Brandon Mitchell:	Replying to "https://github.com/C..." I chimed in on that one when they wanted to make it an Artifact without tars.
00:55:10	Tianon (he/him):	https://github.com/moby/moby/pull/48798 merged yesterday 👀

## January 30, 2025

**Recording**: <https://youtu.be/cu5qD5I0T7Q>

### Attendees:

- Brandon Mitchell
- Ramkumar Chinchani
- Tianon
- Jory Burson
- Mrunal Patel
- Mike Brown
- Syed Ahmed
- Samuel Karp

### Actionable Agenda Items:

- Website update needs approval: <https://github.com/opencontainers/opencontainers.org/pull/157>
  - Jory has a notice going out for members, 30 days ends March 1

### Presentation/Discussion Agenda Items:

- distribution-spec v1.1.1 released: <https://github.com/opencontainers/distribution-spec/releases/tag/v1.1.1>
- TOB election needs to be run for chair:
  - <https://github.com/opencontainers/tob/pull/146>
  - Chair election from last year: <https://github.com/opencontainers/tob/issues/143>
  - Chair election for 2025: <https://github.com/opencontainers/tob/issues/147>
  - New board members can send a bio to Brandon for the website
- (Mrunal) sha 512 support in distribution spec for PQC
  - <https://github.com/opencontainers/distribution-spec/issues/494>
  - <https://github.com/opencontainers/distribution-spec/pull/543/files>
- <https://github.com/kubernetes-sigs/node-feature-discovery/releases/tag/v0.17.0>

### Notes:

Notes from zoom chat:

00:02:39	Brandon Mitchell:	https://opencontainers.org/about/tob/
00:13:39	Samuel Karp:	I'm guessing I missed this; is there a short summary of the motivation for sha512 over sha256?
00:14:43	Ramkumar Chinchani:	We have been discussing BLAKE3 for performance reasons https://crypto.stackexchange.com/questions/88585/post-quantum-security-of-the-blake-family
00:15:13	Samuel Karp:	Yeah, performance reasons for BLAKE3 make sense, but both sha256 and sha512 are from the SHA-2 family.
00:16:11	Ramkumar Chinchani:	In general, the theme is a future of mixed crypto is near, possibly very near
00:16:17	Syed Ahmed:	It’s a suggestion from CNSA
00:16:56	Syed Ahmed:	https://media.defense.gov/2022/Sep/07/2003071836/-1/-1/0/CSI_CNSA_2.0_FAQ_.PDF
00:17:42	Jory Burson (LF):	(TOB election, in case someone wants to nominate cough Sam cough
00:17:47	Jory Burson (LF):	https://github.com/opencontainers/tob/issues/147
00:18:06	Mike Brown:	PAUL SCHWEIGERT  paulschw@us.ibm.com  ibm research working on quantum safe algs.. or at least would have the links
00:18:33	Mrunal Patel:	Thanks Mike!
00:19:32	Tianon (he/him):	Replying to "https://media.defens..." my reading of this is "if you're using SHA, make sure it's 384 or 512", not "you should use SHA-512", but maybe I've missed something 😅
00:20:52	Syed Ahmed:	Replying to "https://media.defens..." No, that’s what I read as well. looks like we have the option of 384/512
00:29:12	Mike Brown:	https://github.com/opencontainers/image-spec/blob/main/descriptor.md#digests
00:29:28	Mrunal Patel:	Thanks!
00:30:19	Mike Brown:	“Registered algorithms: While the algorithm component of the digest string allows the use of a variety of cryptographic algorithms, compliant implementations SHOULD use SHA-256.”
00:35:53	Ramkumar Chinchani:	https://zotregistry.dev/ zot should also support this imo out of the box
00:36:07	Brandon Mitchell:	https://github.com/olareg/olareg
00:36:22	Mrunal Patel:	Thanks for the links!
00:36:26	Mike Brown:	https://github.com/opencontainers/go-digest
00:36:48	Brandon Mitchell:	https://github.com/regclient/regclient
00:36:57	Brandon Mitchell:	"regctl image mod"
00:48:13	Jory Burson (LF):	@Brandon Mitchell I’ve readied the member notice for the release, any questions before that goes out
00:48:35	Brandon Mitchell:	Replying to "@Brandon Mitchell I’..." None from me, ship it
00:49:18	Jory Burson (LF):	Replying to "@Brandon Mitchell I’..." 30 day period ends on March 1, FYI
00:57:26	Brandon Mitchell:	https://github.com/kubernetes-sigs/node-feature-discovery/releases/tag/v0.17.0
01:02:19	Ramkumar Chinchani:	ntd

## January 23, 2025

**Recording**: https://youtu.be/bWmUfnFMmjY

### Attendees:

- Tianon
- Mike Brown
- Ramkumar Chinchani
- Brian Goff
- Brandon Mitchell
- Derek McGowan
- Jory Burson
- Michael Brown
- Samuel Karp

### Actionable Agenda Items:

None

### Presentation/Discussion Agenda Items:

- distribution-spec needs releases for `actions.yml` to avoid breaking everyone's CI:
  - <https://github.com/opencontainers/distribution-spec/pull/560>
  - <https://github.blog/changelog/2024-04-16-deprecation-notice-v3-of-the-artifact-actions/>
  - <https://github.com/opencontainers/distribution-spec/pull/561>
- Jory is looking for committee members for Container Plumbing Days at OSS EU
  - Mike and Brandon volunteered
- Request to cut an image-spec release:
  - External projects want to cleanup their dependencies <https://github.com/opencontainers/image-spec/pull/1189>
- Erofs in containerd: <https://github.com/containerd/containerd/pull/10705>
  - discussed how image selection could work when erofs is seen by older runtimes

### Notes:

Notes from the zoom chat:

00:04:12	Ramkumar Chinchani:	https://github.com/containerd/containerd/pull/10705 just fyi, if folks not already aware
00:07:45	Brandon Mitchell:	https://github.com/opencontainers/image-spec/releases/tag/v1.0.2
00:11:19	Jory Burson (LF):	That explains it, I was hanging out in the wrong zoom 🤦‍♀️
00:18:22	Tianon (he/him):	pretty sure the major.minor.patch terminology predates semver 😅
00:25:20	Derek McGowan:	Co-located with which event?
00:33:08	Samuel Karp:	I won't be able to attend Amsterdam
00:35:47	Mike Brown:	container plumbing days / mini summit for oci.. spin it with some AI related projects how does oci enable ___
00:37:07	Tianon (he/him):	"miner patch"
00:41:28	Mike Brown:	optimize process for handling oci media types… more than “convert"
00:42:49	Mike Brown:	“only one mount is required for each container image instead of one mount per layer "
00:42:54	Mike Brown:	interesting ^^
00:43:29	Samuel Karp:	the container mountns only sees one mount that is the rootfs, but we do have more mounts outside the container mountns
00:45:22	Brandon Mitchell:	https://github.com/opencontainers/wg-image-compatibility/tree/main/docs/proposals
00:47:45	Brandon Mitchell:	https://github.com/opencontainers/image-spec/blob/main/image-index.md
00:50:28	Mike Brown:	https://github.com/opencontainers/image-spec/blob/main/specs-go/v1/descriptor.go#L52-L72
00:50:44	Brandon Mitchell:	https://github.com/regclient/regclient/pull/775
00:52:28	Mike Brown:	ah missed you guys were talking about some new prefer… vs first of a specific match to a set of platform fields
00:52:56	Mike Brown:	thought we were going with the later.. for k8s like scenarios
00:56:55	Derek McGowan:	https://github.com/containerd/platforms/pull/20
00:58:43	Brian Goff:	buildkit...
00:58:51	Brandon Mitchell:	My prefer string is ugly https://github.com/regclient/regclient/pull/775/files#diff-fa22c7f98e5449042e7dd1aba9e5cfdfec3e706dad98dbf18f9bec0a65039087R134-R138
01:01:20	Mike Brown:	standards .. he who merges first..
01:01:20	Jory Burson (LF):	I have to drop, talk to you folks soon!
01:02:56	Mike Brown:	where I get nervous is trying to “partial” match or match one way before using a field and a different way after updating a tool
01:05:40	Samuel Karp:	have to drop now

## January 16, 2025

**Recording**: https://youtu.be/SrYt6Y2GnX0

### Attendees:

- Brandon Mitchell
- Jory Burson
- Sajay Antony
- Joseph Ferguson
- Ramkumar Chinchani

Regrets:

- Mike Brown (can't attend today containerd summit)

### Actionable Agenda Items:

None

### Presentation/Discussion Agenda Items:

- Jory still needs one TM board member to vote for budget
- Planning for container plumbing days / August mini-summit
- go-digest dropped sha384: <https://github.com/opencontainers/go-digest/pull/97>
  - Discussing blake3 and mixed content
- os.features syntax: <https://github.com/opencontainers/image-spec/issues/1237>
- Should Gradle implementation be added: <https://github.com/opencontainers/image-spec/pull/1156>
- Should layers like estargz be defined by the spec: <https://github.com/opencontainers/image-spec/pull/877>
  - Don't want to standardize stuff documented outside of OCI, but it would be good to document the OCI media types, annotations, and validation process.
- Should we update release steps to update specs web page: <https://github.com/opencontainers/specs.opencontainers.org/pull/7>
  - No objection to sending a PR for release steps, few know this page exists.
- Canonical JSON could use more opinions: <https://github.com/opencontainers/image-spec/issues/1226>
  - Ram would like to see Go implementations output canonical JSON

### Notes:

Notes from the zoom chat:

00:16:46	Brandon Mitchell:	Golang discussion on Blake3: https://github.com/golang/go/issues/36632
00:17:30	Brandon Mitchell:	Also at https://github.com/golang/go/issues/32447
00:26:33	Sajay Antony:	I see the love for Blake3 and want to front load all the conversations with the Security folks.
00:27:05	Sajay Antony:	NTD>
00:37:16	Ramkumar Chinchani:	https://specs.opencontainers.org/
00:37:21	Ramkumar Chinchani:	^ this is a real thing?

## January 9, 2025

**Recording**: https://youtu.be/FwppRjliSb0

### Attendees:

- Tianon
- Brian Goff
- Brandon Klein
- Brandon Mitchell
- Sajay Antony
- Mike Brown
- Jory Burson
- Samuel Karp

### Actionable Agenda Items:

- Ready for review
  - <https://github.com/opencontainers/image-spec/pull/1225>
  - <https://github.com/opencontainers/image-spec/pull/1227>
  - <https://github.com/opencontainers/image-spec/pull/1228>
  - <https://github.com/opencontainers/image-spec/pull/1229>
  - <https://github.com/opencontainers/image-spec/pull/1230>

### Presentation/Discussion Agenda Items:

- Annotation for artwork: <https://github.com/opencontainers/image-spec/issues/1231>
- Trailing spec vs trailing implementations: <https://github.com/opencontainers/distribution-spec/issues/485>

### Notes:

Notes from zoom chat:

00:04:34	Tianon (he/him):	ouch
00:04:40	Tianon (he/him):	I'm losing feeling in my toes just thinking about that
00:05:40	Tianon (he/him):	I used to live in a place that gets snow, and now I live in Las Vegas, and that's very much not a coincidence
00:10:23	Brian Goff:	referrers 🙂
00:13:16	Tianon (he/him):	plop a new entry in the index; platform: { os: "metadata", architecture: "logo" }
00:13:25	Tianon (he/him):	Replying to "plop a new entry in ..." (for the avoidance of doubt, this is mostly trolling Brandon)
00:17:20	Brandon Mitchell:	https://oci.dag.dev/
00:18:02	Tianon (he/him):	Replying to "https://oci.dag.dev/..." OSS, too: https://github.com/jonjohnsonjr/dagdotdev
00:18:11	Tianon (he/him):	Replying to "https://oci.dag.dev/..." (so you can run your own instance and access private data, if you need to)
00:19:18	Tianon (he/him):	make the registry accept otherwise-invalid tags like xxx:_metadata to store repo-level data 👀
00:22:38	Sajay Antony:	Replying to "make the registry ac..." Yep we agreed on some tag like that to have teams push their repo metadata to have the front end expose the content on the UX.
00:24:37	Mike Brown:	sure would be nice if someone open sourced their registry api
00:25:05	Tianon (he/him):	Replying to "sure would be nice i..." https://pkg.go.dev/cuelabs.dev/go/oci/ociregistry
00:26:17	Sajay Antony:	Docker Blue .... 😂
00:26:23	Brandon Mitchell:	https://github.com/opencontainers/distribution-spec/issues/485
00:26:30	Brian Goff:	Is the API for Hub even published?
00:26:53	Jory Burson (LF):	That’s the funniest thing I’ve heard in a long while
00:27:35	Tianon (he/him):	Replying to "That’s the funniest ..." gonna quit tech and become a comedian ❤️
00:29:53	Jory Burson (LF):	I will have to drop at the half hour but my update is that I don’t have any updates today! The Trademark Board is missing a vote or two to finish ratifying OCI’s budget. But that’s it!
00:34:17	Samuel Karp:	https://github.com/opencontainers/tob#members
00:39:58	Tianon (he/him):	I don't know anyone with an affinity for old software (cough https://github.com/tianon/oci-schema1  cough)
00:42:31	Brian Goff:	That's some jq
00:46:16	Brandon Mitchell:	https://github.com/opencontainers/distribution-spec/pull/391
00:47:51	Samuel Karp:	Mute?
00:49:52	Sajay Antony:	zoom is messing me with. compounded with remote machine.
00:50:38	Brandon Mitchell:	https://github.com/opencontainers/image-spec/pull/1225
00:50:40	Sajay Antony:	I'll take a look at 1225.

## January 2, 2025

Canceled for holidays

## December 26, 2024

Canceled for holidays

## December 19, 2024

**Recording**: https://youtu.be/sjSFqoQTElw

### Attendees:

- Brandon Mitchell
- Jory Burson
- Ramkumar Chinchani
- Brian Goff
- Samuel Karp

### Actionable Agenda Items:

- Ready for review
  - <https://github.com/opencontainers/image-spec/pull/1225>
  - <https://github.com/opencontainers/image-spec/pull/1227>
  - <https://github.com/opencontainers/image-spec/pull/1228>
  - <https://github.com/opencontainers/image-spec/pull/1229>

### Presentation/Discussion Agenda Items:

- Security announce addition, is this the public or maintainer mailing list?
  - <https://groups.google.com/a/opencontainers.org/g/tob/c/VaFB-VeL5ko>
  - Jory: this is likely an embargo list, not public, and not the internal maintainer list
- Replacing Container Plumbing Days event with OSSummit event:
  - EU event already scheduled: <https://events.linuxfoundation.org/container-plumbing-days/>
  - Adjacent to OSSummit EU: <https://events.linuxfoundation.org/open-source-summit-europe/>
  - Proposal for Thursday or Friday half day event: <https://events.linuxfoundation.org/open-source-summit-north-america/program/schedule-at-a-glance/>
  - CFP, prepared maintainer talks, BOF, or some other format?
  - Jory: Managed by OSSummit organizers, CFPs reviewed by trademark board members, and open to others.
- Canonical JSON:
  - <https://github.com/opencontainers/image-spec/issues/1226>
- Next two meetings canceled for holidays

### Notes:

From the zoom chat:

00:19:20	Brian Goff:	If it was Seattle... I was probably there, but I don't recall.
00:19:36	Brian Goff:	Replying to "If it was Seattle......" So helpful 🙂
00:19:37	Ramkumar Chinchani:	fat fingers!
00:19:52	Ramkumar Chinchani:	just going over the agenda items
00:21:24	Brandon Mitchell:	https://containerplumbing.org/videos
00:24:12	Brian Goff:	I would love to go, but life says probably otherwise.
00:41:58	Brandon Mitchell:	https://datatracker.ietf.org/doc/html/rfc6919
00:42:03	Brian Goff:	Love Levitz

## December 12, 2024

**Recording**: https://youtu.be/CUyH319O9hM

### Attendees:

- Brandon Mitchell
- Michael Brown
- Tianon
- Ramkumar Chinchani
- Jory Burson
- Brian Goff
- Mike Brown
- Sajay Antony

### Actionable Agenda Items:

- Ready for review
  - <https://github.com/opencontainers/oci-conformance/pull/124>
  - <https://github.com/opencontainers/distribution-spec/pull/556>
    - Mike: LGTM merged..

### Presentation/Discussion Agenda Items:

- Ram's demo of Stacker with a new layer type (TBD?)
  - Looking at soci, squashfs, and erofs
  - Building image with Stacker: <https://github.com/project-stacker/stacker>
  - Mounting layers with Atomfs: <https://github.com/project-machine/atomfs>
- Should distribution-spec be changed to require registries rescan every manifest when adding referrers support?
  - Reference: <https://github.com/moby/buildkit/pull/5573>
- Mixing digest algorithms, should spec be updated with clarification?
  - <https://github.com/opencontainers/image-spec/issues/874>
- Policy for supporting Go releases
  - <https://github.com/opencontainers/image-spec/issues/899>
- runc v1.2.3 released: <https://github.com/opencontainers/runc/releases/tag/v1.2.3>

### Notes:

- Planning to cancel the Dec 26 and Jan 2 meetings.

From the zoom chat:

00:07:49	Sajay Antony:	Yes I remember we agreed on the using the digest tag. But then its guidance only.
00:12:50	Sajay Antony:	There is in general a lot of new content given all the security push.
00:14:06	Brian Goff:	Graphic
00:15:14	Sajay Antony:	I'd vote for removing the fallback tag in 2.0 and leave the world to settle for the next 6 months+
00:17:47	Sajay Antony:	Zoom doing its thing
00:20:37	Sajay Antony:	Ah .. build on a base image is interesting.
00:30:21	Jory Burson (LF):	I have to drop at the half hour but wanted to share a few Back of House updates for you all:
1) the trademark board is currently voting on the 2025 budget 🎉
2) related to above, they are keeping an allocation of $25k for software development work - to the extent that we want to make progress on the conformance site this year that budget remains
3) (will follow up on this in chat, too) - the Container Plumbing event that we sponsored last year was over budget, and Chris would like to see us use our budget do host an OCI “mini-summit” instead (cheaper) at OSSNA
00:31:49	Jory Burson (LF):	and last but not least, would you all like to do a blog post summarizing the outcome of the election
00:32:37	Jory Burson (LF):	Slack me! and See you all next week 🎉
00:40:18	Sajay Antony:	Really cool stuff @Ramkumar Chinchani.
00:40:43	Sajay Antony:	NTD. Stayed longer than I should.
00:42:43	Ramkumar Chinchani:	https://www.cyphar.com/blog/post/20190121-ociv2-images-i-tar
00:45:59	Brandon Mitchell:	https://events.linuxfoundation.org/open-source-summit-north-america/
00:46:59	Tianon (he/him):	maybe worth talking about holiday time?  FWIW, I'll be out of office for the rest of the year, so I'll see y'all in Jan 👀

## December 5, 2024

**Recording**: https://youtu.be/o918_rZ5I_A

### Attendees:

- Tianon
- Brandon Mitchell
- Jon Johnson
- Peter Treese
- Erin Barratt
- Brian Goff
- Syed Ahmed

### Actionable Agenda Items:

- Review needed:
  - Hard link limitations: <https://github.com/opencontainers/image-spec/pull/1211>

### Presentation/Discussion Agenda Items:

- KEP-4639 is resulting in groups creating invalid OCI Images with OCI Artifact functionality
  - <https://github.com/CloudNativeAI/model-spec/blob/main/docs/spec.md>
  - <https://github.com/opencontainers/image-spec/blob/main/manifest.md#guidelines-for-artifact-usage>
  - <https://github.com/kubernetes/enhancements/issues/4639>
- TOB Election results: <https://github.com/opencontainers/tob/issues/145#issuecomment-2515665252>

### Notes:

From the zoom chat:

00:01:05        Peter Treese:   Hello from Baltimore
00:03:13        Brandon Mitchell:       https://hackmd.io/El8Dd2xrTlCaCG59ns5cwg?both#
00:03:23        Brandon Mitchell:       I know our paths have crossed a few times in the past
00:05:45        Brandon Mitchell:       https://github.com/CloudNativeAI/model-spec/blob/main/docs/spec.md
00:08:54        Brandon Mitchell:       https://github.com/opencontainers/image-spec/pull/1197
00:09:22        Brian Goff:     If they aren't tar-shaped then it'll be pear-shaped.
00:11:15        Brian Goff:     "Straight forward" depending on what standard you are using 🙂
00:17:14        Brandon Mitchell:       https://github.com/opencontainers/image-spec/pull/1141
00:23:35        Brian Goff:     omg it's been so long.
00:25:21        Brian Goff:     Feels good to break the rules.
00:35:03        Brian Goff:     Compatability
00:35:41        Brian Goff:     As Tianon mentioned earlier, OCI is more or less, what Docker defined 11 years ago.
00:36:47        Brian Goff:     Replying to "As Tianon mentioned ..." Not to diminish effort that's been put into OCI, but everything has had to center around the original Docker implementations.
00:39:41        Brian Goff:     Replying to "As Tianon mentioned ..." And to add, stuff in OCI tends to bubble up from work done in the runtimes/community rather than handed down from the spec.
00:40:11        Peter Treese:   Thank guys.  bye
00:50:59        Brian Goff:     Parallel pulls/processing.

## November 28, 2024

Canceled, US holiday.

## November 21, 2024

**Recording**: https://youtu.be/nrYorcaWNqE

### Attendees:

- Brandon Mitchell
- Mike Brown
- Tianon Gravi
- Samuel Karp
- Michael Brown
- Brian Goff
- Sajay Antony
- Ramkumar Chinchani

### Actionable Agenda Items:

- No items

### Presentation/Discussion Agenda Items:

- Should the namespace specified in the registry proxy be usable in other APIs?
  - <https://github.com/opencontainers/distribution-spec/pull/66>
  - Tag listing, referrers, or pushing content to a push-through proxy?
  - How to reference content with a namespace (should there be a syntax to pull content directly from a proxy with a specific namespace)?
  - Can this be extended to an OCI Layout reference that stores content from multiple repositories in a single Layout directory?
- Skipping next week for US Thanksgiving
- Ram wants to demo some new functionality in Stacker with a new layer type next meeting
  - Looking at soci, squashfs, and erofs
  - Frontend: <https://github.com/project-stacker/stacker>
  - Backend: <https://github.com/project-machine/atomfs>

### Notes:

Notes from the zoom chat:

00:06:19	Brandon Mitchell:	https://github.com/opentofu/libregistry/tree/oci/registryprotocols/ociclient
00:10:46	Sajay Antony:	basically pass in the upstream information?
00:12:16	Sajay Antony:	Could you share information on the NS parameter?
00:16:34	Sajay Antony:	If this is in scope or distribution, I'm trying to understand how a registry operator would use this? [Creating a pull through cache rule in Amazon ECR - Amazon ECR](https://docs.aws.amazon.com/AmazonECR/latest/userguide/pull-through-cache-creating-rule.html)
00:21:21	Mike Brown:	https://github.com/opencontainers/distribution-spec/issues/12
00:26:13	Brandon Mitchell:	ocidir://path/dir#upstream_repo:tag
00:29:29	Brandon Mitchell:	docker pull proxy.example.org#docker.io/proj/image:tag
00:30:59	Sajay Antony:	I'm curious if the goal is the expand the distribution spec to be a proxy as well?
00:36:39	Sajay Antony:	Its quite a bit of wiring up. I think enabling a proxy for your clusters is a common theme.
00:37:06	Sajay Antony:	NTD for the not so fun conflict I have. 
Miss this group more 🙂
00:37:27	Mike Brown:	said another way we are already proxying and need to formalize and secure it between client/registry
00:37:45	Mike Brown:	and client/proxy cases
00:43:00	Ramkumar Chinchani:	sorry, back from the dentist, left side still numb
00:48:11	Brian Goff:	Also need to be able to experiment.
00:49:31	Brandon Mitchell:	"Implementations MAY implement SHA-512 digest verification for use in descriptors." is the ultimate incompatibility feature in OCI today. :D
00:50:16	Ramkumar Chinchani:	https://github.com/project-stacker/stacker
00:50:29	Ramkumar Chinchani:	https://github.com/project-machine/atomfs
00:51:17	Brian Goff:	Everyone hates writing json but only some people hate writing yaml.
00:51:44	Brian Goff:	(tongue in cheek)
00:52:53	Brandon Mitchell:	woot, OCI Layouts! 😀

## November 14, 2024

Canceled for KubeCon meeting.

## November 12, 2024 - KubeCon US

**Recording**: https://youtu.be/iYPf7hyDR5U

- Time: Tuesday, Nov 12th, 2:30 - 4:30pm MST
- Location: Salt Palace Convention Center | Level 2 | 253AB
- Remote zoom (same as weekly): https://zoom.us/j/6449415895?pwd=S2tJVGVra0dYdlZCRjJwdXdPdGRQQT09

### Attendees:

- Brandon Mitchell
- Samuel Karp
- Mike Brown
- Akihiro Suda
- Antonio Ojea
- Toru Komatsu
- Phil Estes
- Alexander D. Kanevskiy
- Byonggon Chun
- Antti Kervinen

### Actionable Agenda Items:

- TOB nominations are open: <https://github.com/opencontainers/tob/issues/145>
  - Any maintainer may nominate, nominees do not need to be a maintainer.

### Presentation/Discussion Agenda Items:

- Adding a cgroup repo: <https://github.com/opencontainers/tob/pull/144>
  - Vote has passed, and repo will be created.
- (aojea) Linux network devices: <https://github.com/opencontainers/runtime-spec/pull/1271>
  - runtime-spec is focused on containers, but networking in K8s is at a pod level
  - OCI is currently focused on container concerns, Pods are a higher level concern of K8s
  - Proposing a primitive for netdev creation in a namespace, not prescribing behavior of higher-level layers like containerd/crio or Kubernetes
  - Mike would like an OCI specification for a set of containers (that would map to shims for pod spec support)
- distribution-spec conformance tests
  - Also suggested that we create an image-spec that validates an OCI Layout (and optionally provide a tool that exports from a registry to an OCI Layout)
- Inject MaskedPath without using k8s security context
- What is the schedule for releasing new specs
- OCI Volumes in K8s

## November 7, 2024

**Recording**: <https://youtu.be/I7U0YbJafXQ>

### Attendees:

- Brandon Mitchell
- Tianon
- Syed Ahmed
- Ramkumar Chinchani
- Sajay Antony
- Samuel Karp
- Brian Goff
- Jory Burson
- Michael Brown

### Actionable Agenda Items:

- image-spec reviews needed:
  - Hard links in union filesystems: <https://github.com/opencontainers/image-spec/pull/1211>
  - Ignore uname/gname: <https://github.com/opencontainers/image-spec/pull/1212>

### Presentation/Discussion Agenda Items:

- containerd released v2.0.0: <https://github.com/containerd/containerd/releases/tag/v2.0.0>
- Proposal for cgroup repo forked off from runc: <https://github.com/opencontainers/tob/pull/144>
  - runc source: <https://github.com/opencontainers/runc/tree/main/libcontainer/cgroups>
- Platform in image manifest: <https://github.com/opencontainers/image-spec/issues/1216>

### Notes:

Notes from the zoom chat:

00:04:56	Brandon Mitchell:	https://github.com/opencontainers/tob/pull/144
00:06:19	Ramkumar Chinchani:	Replying to "https://github.com/o..." Cgroups lib but limited to golang?
00:09:39	Brandon Mitchell:	https://github.com/opencontainers/image-spec/issues/1216
00:09:41	Sajay Antony:	the uid changes, i forgot to submit my review. before.
00:20:17	Jory Burson (LF):	containerd - shall we highlight that anywere
00:21:36	Brian Goff:	GPT loves to write docs.
00:23:11	Brandon Mitchell:	(Oh, and Sajay too, derp)
00:24:53	Brandon Mitchell:	https://github.com/opencontainers/tob/issues/118
00:25:20	Samuel Karp:	CIVS usually
00:30:05	Tianon (he/him):	gonna get gregkh back in here one way or another! 😂
00:30:45	Sajay Antony:	This group has been super supportive.
00:37:34	Sajay Antony:	Sorry folks need to drop. Have to be in another call.
00:37:36	Ramkumar Chinchani:	NTD

## October 31, 2024

**Recording**: https://youtu.be/dqWUxX3fKvI

### Attendees:

- Brandon Mitchell
- Brandon Klein
- Jory Burson
- Ramkumar Chinchani
- Sajay Antony
- Tianon Gravi

### Actionable Agenda Items:

- image-spec reviews needed:
  - Remove master references: <https://github.com/opencontainers/image-spec/pull/1207>
  - Pin versions on release: <https://github.com/opencontainers/image-spec/pull/1208>
  - Hard links in union filesystems: <https://github.com/opencontainers/image-spec/pull/1211>
  - Ignore uname/gname: <https://github.com/opencontainers/image-spec/pull/1212>

### Presentation/Discussion Agenda Items:

- Platform in image manifest: <https://github.com/opencontainers/image-spec/issues/1216>
- Digest verification requirements: <https://github.com/opencontainers/distribution-spec/pull/556>
- Redirects/CDN in dist-spec? : <https://github.com/opencontainers/distribution-spec/issues/299>

### Notes:

Notes from the zoom chat:

00:05:51        Tianon (he/him):        https://github.com/kolyshkin
00:06:01        Brandon Mitchell:       https://github.com/opencontainers/runc/issues/4114
00:10:59        Tianon (he/him):        https://jqlang.github.io/jq/manual/v1.6/
00:11:11        Tianon (he/him):        https://jqlang.github.io/jq/
00:11:44        Tianon (he/him):        https://github.com/tianon/debian-bin/blob/7a94f900c5c6974b8c5f6b201034d1b09ae266df/jq/dpkg-version.jq
00:14:26        Brandon Mitchell:       https://github.com/opencontainers/image-spec/issues/1216
00:17:09        Ramkumar Chinchani:     Replying to "https://github.com/o..." don't we want to stay away from "Config" wrt artifacts?
00:23:17        Ramkumar Chinchani:     Replying to "https://github.com/o..." lesser of two bad choices?
00:26:22        Ramkumar Chinchani:     Replying to "https://github.com/o..." non-runnable artifacts
00:28:50        Sajay Antony:   NTD to drop for cat herding. Will join back if that get's over faster 🙂
00:43:54        Tianon (he/him):        https://github.com/distribution/distribution/blob/c427f845035d28faab65a9218407293bd917e7d5/docs/content/about/configuration.md#redirect

## October 24, 2024

**Recording**: https://youtu.be/5W9qXmhWTR4

### Attendees:

- Tianon
- Brandon Mitchell
- Jory Burson
- Derek McGowan
- Sajay Antony
- Ramkumar Chinchani
- Brian Goff

### Actionable Agenda Items:

- image-spec reviews needed:
  - Remove master references: <https://github.com/opencontainers/image-spec/pull/1207>
  - Pin versions on release: <https://github.com/opencontainers/image-spec/pull/1208>
- distribution-spec reviews needed:
  - Verify digests: <https://github.com/opencontainers/distribution-spec/pull/556>

### Presentation/Discussion Agenda Items:

- runc
  - v1.2.0 released: <https://github.com/opencontainers/runc/releases/tag/v1.2.0>
- image-spec:
  - EOS/Deprecation annotation: <https://github.com/opencontainers/image-spec/pull/903>
  - os-release annotations: <https://github.com/opencontainers/image-spec/issues/1152>
  - uname/gname: <https://github.com/opencontainers/image-spec/issues/1210>
  - hard links across layers: <https://github.com/opencontainers/image-spec/issues/1204>
- *Remaining items deferred to a later meeting*
- distribution-spec:
  - Conformance tests: <https://github.com/opencontainers/distribution-spec/issues/548>
- TOB:
  - image-tools archive: <https://github.com/opencontainers/image-tools>
  - recommendations for repositories: <https://groups.google.com/a/opencontainers.org/g/tob/c/OFimwVDK0Fs>

### Notes:

Notes from the zoom chat:

00:19:26        Tianon (he/him):        arguably, every image is EOL the minute it's created, right?  they can't be updated 🤔
00:19:54        Tianon (he/him):        Replying to "arguably, every imag..." "supported" is probably more accurately a feature of tags - ie, "this tag will likely be updated in the future for bug fixes, security updates, etc"
00:25:05        Sajay Antony:   Replying to "arguably, every imag..." This is also why we didn't invest too much effort into standardizing this.
00:28:41        Brandon Mitchell:       Someone is about to break Tianon's world model: https://ttl.sh/
00:36:25        Sajay Antony:   NTD. Folks.
00:36:29        Sajay Antony:   Sorry.
00:38:52        Tianon (he/him):        https://github.com/jonjohnsonjr/tarp
00:40:48        Tianon (he/him):        Replying to "https://github.com/j..." yeah this reports empty for these layers too, wild; I wonder where it stores the ownership data 🤔
00:44:54        Tianon (he/him):        https://github.com/git/git/blob/fd3785337beb285ed7fd67ce6fc3d3bed2097b40/archive-tar.c#L229-L232
00:57:00        Brandon Mitchell:       https://github.com/opencontainers/image-spec/blob/main/layer.md#hardlinks
00:58:45        Tianon (he/him):        I tried to replicate with `<<<$'FROM bash\nRUN echo hi > foo.txt\nRUN ln foo.txt bar.txt'` and the end result makes bar.txt a copy of foo.txt, not a hard link
00:59:02        Tianon (he/him):        Replying to "I tried to replicate..." (confirming our expectations)
00:59:11        Brian Goff:     Nope

## October 17, 2024

**Recording**: https://youtu.be/NQflxFMrwqI

### Attendees:

- Brandon Mitchell
- Philip Laine
- Tianon
- Ramkumar Chinchani
- Brian Goff
- Sajay Antony
- Mike Brown

### Actionable Agenda Items:

- None

### Presentation/Discussion Agenda Items:

- Registry proxying: <https://github.com/opencontainers/distribution-spec/pull/66>
- TOB votes and open discussions:
  - archive image-tools: <https://groups.google.com/a/opencontainers.org/g/tob/c/PPFdx36D9u0>
  - code of conduct: <https://groups.google.com/a/opencontainers.org/g/tob/c/KAzq5Fnzg5Y>
    - <https://github.com/opencontainers/.github/pull/61>
  - defining repo standards: <https://groups.google.com/a/opencontainers.org/g/tob/c/OFimwVDK0Fs>
- Remove references to master in image-spec: <https://github.com/opencontainers/image-spec/pull/1207>
- Update image-spec release to pin external spec versions: <https://github.com/opencontainers/image-spec/pull/1208>
- EOS/Deprecation annotation discussions:
  - <https://github.com/opencontainers/image-spec/pull/903>
  - <https://github.com/opencontainers/image-spec/issues/1152>
- Mike: K8s mounting artifacts as volume
  - they plan to add artifact support next
- Clients should verify requested digest: <https://github.com/opencontainers/distribution-spec/pull/556>
- Content ideas for KubeCon meeting?

### Notes:

From the zoom chat:

00:05:41        Philip Laine:   https://github.com/opencontainers/distribution-spec/pull/66
00:08:26        Brandon Mitchell:       The slack join link is here: https://opencontainers.org/community/overview/
00:36:46        Sajay Antony:   This is so interesting. I need to drop for a standing conflict. Erlang versioning I need to read up.
00:40:34        Brandon Mitchell:       https://github.com/opencontainers/image-spec/pull/1197
00:45:44        Sajay Antony:   Managed to get out of that meeting 🙂
00:50:38        Sajay Antony:   folks have been working on CRI signature and other item validations.
00:51:29        Brandon Mitchell:       custom extensions for that make a lot of sense, I worry about it getting into the k8s api directly
00:54:11        Brandon Mitchell:       https://github.com/opencontainers/image-spec/pull/970
00:59:02        Brandon Mitchell:       Now I'm triggered
01:01:44        Sajay Antony:   atomic referrer put API, Latest referrer of an artifactType
01:02:03        Sajay Antony:   Fun stuff later folks.

## October 10, 2024

**Recording**: https://youtu.be/jur-zCrG61E

### Attendees:

- Tianon
- Brandon Mitchell
- Sajay Antony
- Brian Goff
- Ramkumar Chanchani

### Actionable Agenda Items:

- none

### Presentation/Discussion Agenda Items:

- none

### Notes:

- Mentioned open TOB votes
  - <https://groups.google.com/a/opencontainers.org/g/tob/c/OFimwVDK0Fs>
- Call to action: add agenda items for KubeCon meeting
- Short meeting, no agenda

## October 3, 2024

**Recording**: https://youtu.be/e7kLLkLvYCE

### Attendees:

- Brian Goff
- Syed Ahmed
- Brandon Klein
- Joseph Ferguson
- Michael Brown
- Ramkumar Chanchani
- Jory Burson
- Sajay Antony
- Brandon Mitchell

### Actionable Agenda Items:

- TOB Vote to archive image-tools:
  - <https://github.com/opencontainers/image-tools>
  - <https://groups.google.com/a/opencontainers.org/g/tob/c/PPFdx36D9u0>
- TOB Vote to update Code of Conduct:
  - <https://github.com/opencontainers/.github/pull/61>
  - <https://groups.google.com/a/opencontainers.org/g/tob/c/KAzq5Fnzg5Y>

### Presentation/Discussion Agenda Items:

- Brandon: How should auth be setup in the OCI GitHub repos
  - Various teams list people that haven't been involved in the project for a long time
  - Archived projects still have admin access to shared repositories
  - Inconsistent access between spec maintainers on shared repositories
- Jory has a room at KubeCon on Tuesday, OCI calendar has been updated

### Notes:

From the zoom chat:

00:06:45        Brandon Mitchell:       https://groups.google.com/a/opencontainers.org/g/tob
00:07:32        Brandon Mitchell:       https://github.com/opencontainers/image-tools
00:08:40        Sajay Antony:   Sounds good.
00:08:48        Sajay Antony:   Will reply.
00:12:41        Brandon Mitchell:       https://github.com/orgs/opencontainers/teams
00:18:16        Brandon Mitchell:       https://github.com/orgs/opencontainers/teams/website

## September 26, 2024

**Recording**: https://youtu.be/SWQMmkaNWvQ

### Attendees:

- Brandon Mitchell
- Tianon
- Ramkumar Chinchani
- Brian Goff
- Jory Burson
- Syed Ahmed
- Victor Lu

### Actionable Agenda Items:

- Fixing endpoint status codes: <https://github.com/opencontainers/distribution-spec/pull/555>

### Presentation/Discussion Agenda Items:

- Hard links between layers? <https://github.com/opencontainers/image-spec/issues/1204>

### Notes:

From the zoom chat:

00:05:51        Jory Burson (LF):       https://youtu.be/rvrZJ5C_Nwg?t=130
00:06:50        Brandon Mitchell:       So a blurry affiliation.
00:07:05        Jory Burson (LF):       https://docs.google.com/document/d/1tHcSsCwlIPRr6RKaCxtY2yCMl-0Nc9PVXX-jeVmYutk/edit
00:09:57        Tianon (he/him):        on the timing discussion Brandon and I were having, OCI and CNCF were both ostensibly created/announced in June 2015, although OCI had immediate action in July and CNCF didn't do much until the following year (which tracks with the "what are we?" early confusion CNCF had that I was mentioning)
00:10:39        Ramkumar Chinchani:     CNCF got it right by creating a formal project onboarding process
00:13:00        Tianon (he/him):        Replying to "CNCF got it right by..." for OCI, that's really more of a reflection of OCI's purpose and focus - it was never intended to be a collection of projects, but rather a place to collaborate and coordinate on the very low-level bits
00:14:20        Brandon Mitchell:       Reacted to "for OCI, that's real..." with ➕
00:15:20        Brian Goff:     lol, answering other people's questions.
00:16:16        Brian Goff:     No, no history on hardlinks between layers here.
00:17:58        Tianon (he/him):        I've sent a ping out to more Moby project maintainers to see if anyone there is willing to chime in on hard links between layers (although not holding my breath; this is a pretty hefty edge case scenario 😄)
00:19:39        Brian Goff:     Replying to "I've sent a ping out..." Yeah, I imagine a lot of 🤷

## September 19, 2024

**Recording**: https://youtu.be/7B4WAZfsB4A

### Attendees:

- Tianon
- Brandon Mitchell
- Mike Brown
- Sajay Antony
- Brian Goff
- Samuel Karp
- Syed Ahmed

### Actionable Agenda Items:

- zstd support: <https://github.com/opencontainers/image-spec/pull/1198>
- distribution-spec release process: <https://github.com/opencontainers/distribution-spec/pull/460>

### Presentation/Discussion Agenda Items:

- Proposed KubeCon room: Wednesday, Nov 13, 2:30-4:30pm MST
  - Sam to follow up and see whether we can have a room on Tuesday instead
- OCI VolumeSource KEP
  - Mention of artifacts seems to cause confusion as the KEP generally just supports images

### Notes:

From the zoom chat:

00:13:42        Brian Goff:     Nope
00:17:42        Sajay Antony:   I'm actually really excited to see that KEP materialize.
00:21:25        Sajay Antony:   Volumes  all the way down.
00:24:55        Brandon Mitchell:       https://docs.google.com/document/d/1E7iKPOuyA1jxPe8vDG8aPd8jtnCEbpDpCifXDvDCnA0/edit#
00:29:25        Brandon Mitchell:       https://github.com/kubernetes/enhancements/tree/master/keps/sig-node/4639-oci-volume-source#non-goals
00:29:50        Brandon Mitchell:       "Manifest list use cases are left out for now and will be restricted to matching architecture like we do today for images." I may have misread that
00:30:06        Tianon (he/him):        Replying to ""Manifest list use c..." yeah that sounds correct IMO
00:30:40        Tianon (he/him):        Replying to ""Manifest list use c..." but the whole discussion has me thinking about how interesting it might be to have the runtime/orchestrator mount an OCI layout inside a container 🤔
00:34:39        Sajay Antony:   layers are blobs.
00:34:55        Sajay Antony:   but for image its clearly defined.
00:38:23        Brian Goff:     So OCI is now a nix store
00:39:25        Sajay Antony:   Glad we put in the limit.
00:39:31        Sajay Antony:   Need to drop folks.
00:40:49        Brian Goff:     Now you just need a mat with different conclusions that you can jump to.
00:41:08        Brian Goff:     Replying to "Now you just need a ..." That's an "Office Space" reference

## September 12, 2024

**Recording**: https://youtu.be/8usYqCou9TU

### Attendees:
- Tianon
- Brandon Mitchell
- Ramkumar Chinchani
- Sajay Antony
- Brian Goff

### Actionable Agenda Items:

- nondistributable layers deprecation: <https://github.com/opencontainers/image-spec/pull/1200>
- zstd support: <https://github.com/opencontainers/image-spec/pull/1198>
- distribution-spec release process: <https://github.com/opencontainers/distribution-spec/pull/460>

### Presentation/Discussion Agenda Items:

- Raw image layers: <https://github.com/opencontainers/image-spec/pull/1197>
- URLs field: <https://github.com/opencontainers/image-spec/issues/1201>

### Notes:
- Blake3 status
  - PR to update support isn't seeing traction <https://github.com/opencontainers/go-digest/pull/66>
  - go-digest hasn't had a release in a long while, so support in existing projects requires an import of a commit
  - Adding this to go-digest means an added dependency to every user of the project
  - Ideally, this could make it into the Go stdlib, but even making it into x/crypto is blocked waiting for the standard to mature: <https://github.com/golang/go/issues/36632>
  - Once supported, changes to the distribution-spec APIs would be needed to allow clients to push manifests and blobs with a different digest algorithms.

Zoom chat:

00:16:02        Ramkumar Chinchani:     basically, http download something and bind-mount into container
00:16:52        Sajay Antony:   Tianon , you bring the Joy.
00:17:23        Tianon (he/him):        Replying to "Tianon , you bring t..." I try so hard - these meetings can be so dry sometimes and I want us to remember we're people 😄
00:21:14        Brandon Mitchell:       I like how Non-distributable layers says that they may include URLs but that it doesn't determine non-distributable: https://github.com/opencontainers/image-spec/blob/main/layer.md#non-distributable-layers
00:22:17        Sajay Antony:   Ah the OCI - docker - same difference.
00:22:27        Ramkumar Chinchani:     https://sysdig.com/blog/exploit-detect-mitigate-log4j-cve/
00:25:04        Brandon Mitchell:       https://github.com/opencontainers/image-spec/pull/442
00:27:19        Sajay Antony:   Oh wow song download with multiple formats indexes would be cool.
00:27:32        Tianon (he/him):        no interesting references to urls in https://github.com/opencontainers/distribution-spec/commit/c90b0f145ac6bc09d2636ee214486ac333edc284
00:32:39        Brian Goff:     I don't think we talked about it last week and I missed the week before. Anything new re: Blake3?
00:34:34        Sajay Antony:   Is there a way for Buildkit to produce Blake3 already?
00:34:51        Brian Goff:     Replying to "Is there a way for B..." Nope.
00:36:54        Brandon Mitchell:       https://github.com/opencontainers/go-digest/pull/66
00:37:06        Tianon (he/him):        one* PR away! 😂
00:37:12        Brian Goff:     Sorry, missed the last few minutes due to school calling me.
00:37:19        Tianon (he/him):        Replying to "Is there a way for B..." *actual number may vary
00:37:33        Tianon (he/him):        (talk to your doctor Docker to see if PRs are right for you)
00:39:12        Brian Goff:     Same (re: 3rd party lib)
00:40:29        Tianon (he/him):        https://github.com/golang/go/issues/36632
NTD for another meeting.tony:   Sounds like Brian is signing up for championing blake3 😂

## September 5, 2024

**Recording**: https://youtu.be/OFyzjajQ7gk

### Attendees:
- Brian Goff
- Jory Burson
- Brandon Mitchell
- Syed Ahmed
- Ramkumar Chanchani
- Tianon
- Sajay Antony
- Mike Brown
- Brandon Klein

### Actionable Agenda Items:

- Request for feedback on index entries <https://github.com/opencontainers/distribution-spec/issues/550>

### Presentation/Discussion Agenda Items:

- Remaining items for zstd support <https://github.com/opencontainers/image-spec/issues/803>
  - Action: Opened <https://github.com/opencontainers/image-spec/pull/1198>
- Deleting by tag: <https://github.com/opencontainers/distribution-spec/issues/551>
  - Action: Opened <https://github.com/opencontainers/distribution-spec/pull/552>

### Notes:

From the zoom chat:

00:03:31        Brian Goff:     2nd day of school for the kids and I'm already done this morning.
00:05:47        Tianon (he/him):        and the buildkit issue is "fixed" but the fix isn't enabled by default (it's opt-in 🙃)
00:06:58        Brandon Mitchell:       https://github.com/opencontainers/image-spec/issues/803
00:07:28        Brian Goff:     lol I think its easier to say "z-standard" then it is to say "z-s-t-d"
00:08:19        Tianon (he/him):        Replying to "lol I think its easi..." "zee studd" slurring the u a bit, for the cursed option
00:10:54        Brian Goff:     +1 should
00:15:04        Sajay Antony:   content Negotiation per blob?
00:19:58        Mike Brown:     IMO.. on the 803 PR use plain language in a note: regarding some registries and clients MAY also… and explain that this is optional and may not be supported in all 1.0/1.1 image manifest implementations
00:32:15        Brian Goff:     We have 2 digests now.
00:32:50        Brian Goff:     Probably also don't need 2 digests if you can verify the uncompressed blob digest.
00:33:00        Brian Goff:     (with transport compression)
00:38:31        Sajay Antony:   Need to drop for some fun compliance work discussions
00:46:56        Jory Burson (LF):       Back to school!
00:49:42        Brian Goff:     🎤
00:49:57        Jory Burson (LF):       Oh captain my captain!
00:52:20        Mike Brown:     https://github.com/opencontainers/image-spec/pull/775
00:52:21        Tianon (he/him):        it's probably not productive to say "a compelling reason to get the marginal gains of zstd" in the things we're missing? 😂
00:53:00        Brian Goff:     /me writes a 2nd thing called zstd
00:53:53        Brandon Mitchell:       Embrace, extend, confuse
00:54:19        Brandon Mitchell:       https://github.com/opencontainers/distribution-spec/issues/551
00:55:35        Mike Brown:     775 may be controversial but: “Container Runtimes
Implemented and upstreamed for containerd stack
containerd (1.3+)
https://github.com/containerd/imgcrypt
Implemented and upstreamed for RedHat stack
cri-o 1.17+
buildah 1.5+
skopeo“

## August 29, 2024

**Recording**: https://youtu.be/IFohU9Epv9s

### Attendees:
- Brandon Mitchell
- Brian Goff
- Tianon
- Jory Burson
- Ramkumar Chanchani
- Brandon Klein
- Mike Brown

### Actionable Agenda Items:

None

### Presentation/Discussion Agenda Items:
- Should image-spec do a patch release: <https://github.com/opencontainers/image-spec/pull/1192#issuecomment-2310756540>
- Are Index entries accessed from the manifest API: <https://github.com/opencontainers/distribution-spec/issues/550>
- Deleting by tag: <https://github.com/opencontainers/distribution-spec/issues/551>

### Notes:

From the zoom chat:

00:08:33        Brian Goff:     At least its Slack and not teams.
00:08:59        Tianon (he/him):        Replying to "At least its Slack a..." IRC!!!
00:09:37        Brandon Mitchell:       https://github.com/opencontainers/image-spec/compare/v1.1.0...main
00:10:47        Ramkumar Chinchani:     also this https://github.com/opencontainers/image-spec/commit/2d95dde8615f9ed8a911873f8eb72a8582af577a
00:11:03        Ramkumar Chinchani:     looks worth a patch release
00:12:04        Jory Burson (LF):       Alice confirmed the calendar is right now!
00:15:06        Tianon (he/him):        https://github.com/opencontainers/image-spec/blob/3c3d71753a024375415026b918ba470714383a81/image-index.md#:~:text=This%20REQUIRED%20property%20contains%20a%20list%20of%20manifests%20for%20specific%20platforms.
00:15:23        Ramkumar Chinchani:     if you push via manifest api, could show up in tags listing
00:15:47        Ramkumar Chinchani:     index or otherwise
00:16:58        Brandon Mitchell:       https://oci.dag.dev/?image=ghcr.io%2Fsudo-bmitch%2Fversion-bump%3Abuildcache
00:23:46        Ramkumar Chinchani:     i like broken links
00:24:12        Ramkumar Chinchani:     soft links vs hard links
00:30:53        Brian Goff:     NTD
00:38:00        Tianon (he/him):        Replying to "https://oci.dag.dev/..." good old Jon, saying my thoughts 5 years ago: https://github.com/moby/buildkit/issues/1143#issuecomment-533710677 (s/docs.docker.com/OCI image spec/)
00:41:30        Brandon Mitchell:       https://github.com/moby/buildkit/issues/2251
00:53:47        Ramkumar Chinchani:     Let's see what ML folks have to say
00:54:34        Tianon (he/him):        Replying to "Let's see what ML fo..." this is actually the group of folks I'm actively subtweeting 😂  they're putting artifacts directly in blobs with annotations for filename, where they could instead put those same uncompressed raw artifacts in a tarball which then has a full tar header that includes filename and then they can be mounted as images along with all standard existing tooling
00:54:51        Tianon (he/him):        Replying to "Let's see what ML fo..." `RUN --mount=type=image,...` in buildkit, the new feature Mike's talking about in k8s, etc.
00:54:57        Jory Burson (LF):       I have to drop a few minutes early! good to see ya’ll
00:59:19        Ramkumar Chinchani:     https://kubernetes.io/blog/2024/08/16/kubernetes-1-31-image-volume-source/
01:05:16        Ramkumar Chinchani:     ntd

## August 22, 2024

**Recording**: https://youtu.be/JpjDNaoGfgI

### Attendees:
- Tianon
- Brandon Mitchell
- Sajay Antony
- Brian Goff
- Mike Brown
- Ramkumar Chinchani

### Actionable Agenda Items:
- Review needed:
  - `ref.name` requirements: <https://github.com/opencontainers/image-spec/pull/1196>

### Presentation/Discussion Agenda Items:

None.

### Notes:
- Short meeting due to limited agenda.

## August 15, 2024

**Recording**: https://youtu.be/mYjKbvfRbOo

### Attendees:
- Brandon Mitchell
- Tianon
- Jory Burson 
- Ramkumar Chinchani
- Mike Brown

### Actionable Agenda Items:

None.

### Presentation/Discussion Agenda Items:
- refactoring conformance tests: <https://github.com/opencontainers/distribution-spec/issues/548>

### Notes:
- Refactoring Conformance Tests:
    - Brandon suggested that it might not be too much of an undertaking to refactor the site without breaking it.
    - Ramkumar noted that his list is only meant to suggest informally, rather than a list of changes he is advocating for (e.g. ENV vars vs. using a config file)
    - The group discussed simplfying set up and tear down steps for registries
    - Group discussed client-side testing, and some of the edge cases for testing as well as some of the implications. The group talked about ways to break the problem spaces down. Tianon noted that past efforts to consider/ work on this for the distribution spec had failed, as it proved to be a very difficult problem to work through all of the different components.
        - Discussion of different styles/approaches for testing spec conformance/compliance. 
    - ACTION: capture notes on the issue for next steps

From the zoom chat:

00:11:31        Brandon Mitchell:       https://conformance.opencontainers.org/static/v1.0/reports/zot/
00:24:13        Brandon Mitchell:       Lets see which clients support sha512
00:39:03        Brandon Mitchell:       https://hachyderm.io/@forrestbrazeal/112955281081608300

## August 8, 2024

**Recording**: https://youtu.be/GDpg7_aAzHI

### Attendees:
- Tianon
- Brandon Mitchell
- Samuel Karp
- Mike Brown
- Ramkumar Chinchani
- Josh Dolitsky
- Sajay Antony
- Michael Brown

### Actionable Agenda Items:
- image-spec review needed to remove IRC link: <https://github.com/opencontainers/image-spec/pull/1195>
  - merged
- Consider closing image-spec manifest size limit: <https://github.com/opencontainers/image-spec/issues/781>
  - closed

### Presentation/Discussion Agenda Items:
- image-spec Layout, should this be a transport, a disk representation of a repository, or both? <https://github.com/opencontainers/image-spec/issues/811>
  - Disagreement on whether any changes are needed, OCI already supports a registry in the annotation today, but few tools use that.
- registry proxy features without breaking mixed server and client versions: <https://github.com/opencontainers/distribution-spec/pull/66>
  - Brandon raised concerns with dependency confusion attacks if mix client and server versions are combine.
- distribution-spec digest verification requirements: <https://github.com/opencontainers/distribution-spec/issues/549>
  - No disagreement, a PR should be opened.
- refactoring conformance tests: <https://github.com/opencontainers/distribution-spec/issues/548>
  - Brandon has concerns on writing client conformance tests (how to write code that triggers all the various clients to call specific APIs)
  - carry forward to next week

### Notes:

From the zoom chat:

00:04:01        Brandon Mitchell:       The meeting notes for anyone that doesn't have the URL handy: https://hackmd.io/El8Dd2xrTlCaCG59ns5cwg?both
00:10:29        Brandon Mitchell:       https://github.com/opencontainers/image-spec/pull/1195
00:10:51        Brandon Mitchell:       https://github.com/opencontainers/image-spec/issues/781
00:12:03        Sajay Antony:   Sorry folks just checking the agenda.
00:14:29        Brandon Mitchell:       https://github.com/opencontainers/image-spec/issues/811
00:18:09        Tianon (he/him):        https://github.com/opencontainers/image-spec/blob/8797c3fedb77200c102c816ddcd295bb1e19d3e3/annotations.md#:~:text=org.opencontainers.image.ref.name
00:18:26        Brandon Mitchell:       io.containerd.image.name
00:19:19        Ramkumar Chinchani:     and this is in the top-level index.json so original image is untouched
00:20:05        Ramkumar Chinchani:     copy same image from dockerhub, acr, ecr all can tracked independently
00:23:09        Tianon (he/him):        This layout MAY be used in a variety of different transport mechanisms: archive formats (e.g. tar, zip), shared filesystem environments (e.g. nfs), or networked file fetching (e.g. http, ftp, rsync).
00:23:22        Tianon (he/him):        Replying to "This layout MAY be u..." https://github.com/opencontainers/image-spec/blob/8797c3fedb77200c102c816ddcd295bb1e19d3e3/image-layout.md#:~:text=This%20layout%20MAY%20be%20used%20in%20a%20variety%20of%20different%20transport%20mechanisms%3A%20archive%20formats%20(e.g.%20tar%2C%20zip)%2C%20shared%20filesystem%20environments%20(e.g.%20nfs)%2C%20or%20networked%20file%20fetching%20(e.g.%20http%2C%20ftp%2C%20rsync).
00:24:05        Tianon (he/him):        https://github.com/opencontainers/image-spec/blob/8797c3fedb77200c102c816ddcd295bb1e19d3e3/image-layout.md#indexjson-file
00:24:21        Tianon (he/him):        Replying to "https://github.com/o..." No semantic restriction is given for the "org.opencontainers.image.ref.name" annotation of descriptors.
00:26:27        Tianon (he/him):        $ docker buildx build - --output type=oci <<<$'FROM scratch\nCMD []' --tag registry.foo/bar:baz --quiet | tar --extract --to-stdout index.json | jq '.manifests[].annotation} "org.opencontainers.image.ref.name": "baz"08-08T17:25:37Z",
00:29:38        Tianon (he/him):        https://github.com/opencontainers/image-spec/commit/b692deece6f3e93d43de1615fa592b86f0f27c34
00:31:06        Josh Dolitsky:  woah woah woah
00:32:11        Mike Brown:     i suppose not saying fully qualified for ref.name is the confusing part when reading
00:32:51        Sajay Antony:   Replying to "i suppose not saying…" And the example don’t show that.
00:34:17        Mike Brown:     Replying to "i suppose not saying..." my rec is add the example add the word fully to be clear and don’t break.. the new ref.localname can be different
00:34:45        Tianon (he/him):        any tool that breaks on a full reference in ref.name is noncompliant with v1.0 of the image specification
00:35:31        Tianon (he/him):        Replying to "any tool that breaks..." if we had some way to make compliance tests for image spec, this would absolutely be worth including (but that's a Hard Problem)
00:37:16        Ramkumar Chinchani:     full name and actual layout, and how they are tied together
00:40:04        Sajay Antony:   Replying to "woah woah woah" Oh well.
00:41:27        Sajay Antony:   This is an interesting one. NTD folks.
00:42:07        Brandon Mitchell:       https://github.com/opencontainers/distribution-spec/pull/66
00:44:54        Brandon Mitchell:       https://github.com/opencontainers/distribution-spec/issues/549
00:52:24        Brandon Mitchell:       https://github.com/opencontainers/distribution-spec/issues/548
00:58:23        Ramkumar Chinchani:     the conformance test may have to run a server
00:58:31        Ramkumar Chinchani:     Replying to "the conformance test..." "include"

## August 1, 2024

**Recording**: https://youtu.be/dEI15Qa62Wc

### Attendees:
- Brandon Mitchell
- Tianon
- Jory Burson
- Sajay Antony
- Brian Goff
- Ramkumar Chinchani
- Ravi Chamarthy
- Michael Brown
- Jon Johnson
- Mike Brown

### Actionable Agenda Items:
- Any objections to private security reports in GitHub?
  - <https://github.com/opencontainers/image-spec/issues/974>
  - <https://github.com/opencontainers/distribution-spec/issues/363>
- ACTION: Security Email Alias should contain TDC + TOB (maintainers of runtime-spec + image-spec + distribution-spec + runc)
- DECISION: Enable on GitHub; maybe send a note to the dev and tob (and security) mailing lists at least that you're opening these

### Presentation/Discussion Agenda Items:
- Should we close "subject reference to blobs"? <https://github.com/opencontainers/image-spec/issues/1012>
    - Vbatts opened this some time ago; group has been awaiting clear usecases but the feature remains unplanned.
    - The group agreed to close the issue as unplanned.
- <https://github.com/opencontainers/distribution-spec/issues/546>
    - The group discussed concurrent users and cores. 
    - The group also discussed deprecating sha256

### Notes:
- Action item: scope of work & potential devs for conformance test site work (Jory to chat with Brandon)

From the zoom chat:

00:03:08        Sajay Antony:   Seattle/Puget Sound Area  is having a good day as well.
00:03:30        Jory Burson (LF):       Replying to "Seattle/Puget Sound ..." Gotta enjoy those when you get them!
00:03:48        Brian Goff:     Replying to "Seattle/Puget Sound ..." Hard agree, though I've enjoyed the overcast earlier in the week too.
00:04:19        Sajay Antony:   For 3 months of the year Brandon.
00:04:40        Ramkumar Chinchani:     warmer weather, no state income taxes, likely all-year
00:04:41        Brian Goff:     Replying to "For 3 months of the ..." Autum is amazing here.
00:06:27        Ramkumar Chinchani:     if we have time, maybe eyes on https://github.com/opencontainers/distribution-spec/issues/546
00:10:17        Tianon (he/him):        TDC + TOB
00:10:32        Tianon (he/him):        Replying to "TDC + TOB" maintainers of all projects + TOB
00:11:18        Tianon (he/him):        Replying to "TDC + TOB" runtime-spec + image-spec + distribution-spec + runc, to be more specific/precise
00:14:26        Sajay Antony:   Sorry brb
00:14:50        Tianon (he/him):        maybe send a note to the dev and tob (and security) mailing lists at least that you're opening these
00:15:15        Tianon (he/him):        Replying to "maybe send a note to..." thinking just a "hey, this is on now, we'll try it out"
00:16:52        Ramkumar Chinchani:     +1
00:21:52        Brandon Mitchell:       Are we assuming fewer concurrent users than cores?
00:24:46        Sajay Antony:   Sorry for not being able to give my 100% today.
00:25:43        Michael Brown:  +1
00:28:53        Ramkumar Chinchani:     blake3 has already landed in go-digest
00:29:15        Ramkumar Chinchani:     we have to agree on name first
00:29:25        Ramkumar Chinchani:     "blake3-256:<>"
00:30:40        Brandon Mitchell:       I think go-digest already picked a name and we'd be best to follow their lead.
00:32:21        Sajay Antony:   Not sure if there is a reason for a different name - The BLAKE3 Hashing Framework (ietf.org)
00:32:32        Ramkumar Chinchani:     sha512 is in general faster than sha256
00:32:41        Brandon Mitchell:       It's going to take longer to deprecate sha256 than Docker schema v1
00:33:13        Mike Brown:     this ^ much much longer
00:39:08        Sajay Antony:   Dropping for another internal conflict.
00:44:31        Ramkumar Chinchani:     dist-spec GA -> conformance GA config file -> run tests
00:49:42        Tianon (he/him):        the current conformance tests were funded by the OCI 👀
00:54:26        Brandon Mitchell:       https://github.com/opencontainers/oci-conformance
00:54:30        Ramkumar Chinchani:     https://conformance.opencontainers.org/
00:55:53        Brandon Mitchell:       https://github.com/opencontainers/distribution-spec/tree/main/conformance
00:57:35        Jory Burson (LF):       You want something they can drill down into
00:58:51        Brian Goff:     yay blake3

## July 25, 2024

**Recording**: https://youtu.be/_MwrvDwU-Ds

### Attendees:
- Brian Goff
- Tianon
- Brandon Mitchell
- Jory Burson
- Ramkumar Chinchani
- Mike Brown
- Michael Brown
- Sajay Antony
- Jon Johnson 

### Actionable Agenda Items:
- _add your items_

### Presentation/Discussion Agenda Items:
- distribution-spec:
  - allowing unordered chunk push: <https://github.com/opencontainers/distribution-spec/issues/546>
  - supporting sha512 content: <https://github.com/opencontainers/distribution-spec/issues/494> and <https://github.com/opencontainers/distribution-spec/pull/543>
  - FAQ for digest algorithm: <https://github.com/opencontainers/distribution-spec/pull/547>

### Notes:

- allowing unordered chunk push: <https://github.com/opencontainers/distribution-spec/issues/546>
    - Problems to work out in each direction; keeping this on the radar as Ram has not had time to poke into this issue.
- supporting sha512 content: <https://github.com/opencontainers/distribution-spec/issues/494> and <https://github.com/opencontainers/distribution-spec/pull/543>
    - Brandon has worked on the PR and reviewed a few changes
    - Action Items: update PR to suggest that users "should" include the digest algorithm. 
    - Push digest algorithms to image spec? Consider allowing push registration of digests. Can you have multiple in the same digest string?
    - Work on this before spec changes are out? Brandon thinks yes as go-digest is already shipping. 

Zoom chat:

00:11:27        Sajay Antony:   MD5.
00:16:08        Michael Brown:  Reacted to "MD5." with 😃
00:23:09        Tianon (he/him):        I believe it was Ram who pointed at https://github.com/opencontainers/go-digest/blob/22b78e47854adc56477927aba5f4c930b56af8c9/algorithm.go#L48-L99 in one of these threads, which is interesting and very spec-adjacent (if not explicitly in the spec, it's the "canonical implementation")
00:23:38        Tianon (he/him):        sha384 😭 stop
00:23:49        Jon Johnson:    BLAKE3 BLAKE3 BLAKE3
00:25:21        Ramkumar Chinchani:     i spy a "blake3"
00:26:55        Ramkumar Chinchani:     The goal of my PR was how do we(=OCI) communicate the motivation of these changes to the community.
00:30:46        Mike Brown:     https://github.com/opencontainers/image-spec/blob/39ab2d54cfa8fe1bee1ff20001264986d92ab85a/descriptor.md?plain=1#L95
00:31:58        Brian Goff:     ntd, all hail blake3
00:32:19        Sajay Antony:   Sorry folks need to drop. looks like there is a lot of love for Blake3.
00:36:16        Jon Johnson:    chaos is a ladder
00:36:32        Ramkumar Chinchani:     we did unleash "artifacts", did we not?
00:38:28        Tianon (he/him):        stopwatch running jon, three minutes
00:38:30        Mike Brown:     https://github.com/opencontainers/image-spec/pull/589
00:38:33        Mike Brown:     nice thread
00:38:49        Brandon Mitchell:       https://oci.dag.dev/?image=sudobmitch/demo:sha512
00:40:00        Tianon (he/him):        https://oci.dag.dev/?blob=sudobmitch/demo@sha512:16fdaf1a24baf259bde2b11d12faa6f2cdaec25a2744f7fdbd1c86b2d0528d248b1895c0b66db607e4b0e72f3cadbfa96a0fa3d52e4574ee011804f6d27d386f&mt=application%2Fvnd.oci.image.config.v1%2Bjson&size=4508 very cute (the answer to my theory was No, Jon Blocks Us)
00:40:12        Mike Brown:     https://github.com/opencontainers/go-digest/blob/master/algorithm.go#L69
00:40:57        Tianon (he/him):        Replying to "I believe it was Ram..." see here for where I shared that block of code earlier in this meeting, Mike 👀
00:42:18        Tianon (he/him):        Replying to "stopwatch running jo..." request timeout, unrealistic expectations!!
Error: fetching config: unsupported hash: "sha512"nfig sudobmitch/demo:sha512
00:50:29        Tianon (he/him):        j. jonah craneison
00:50:39        Tianon (he/him):        Replying to "j. jonah craneison" "get me [images] of [gzip]"
00:52:37        Tianon (he/him):        Brandon have you played with roger's https://pkg.go.dev/cuelabs.dev/go/oci/ociregistry ?
00:52:50        Tianon (he/him):        Replying to "Brandon have you pla..." would make implementing the thing you're talking about really really trivial
00:53:08        Tianon (he/him):        Replying to "Brandon have you pla..." in fact, you could go even further/worse and have any request for any sha256 manifest return your broken one, for even more fun


## July 18, 2024

**Recording**: https://youtu.be/gMrCTaOuBgA

### Attendees:
- Brian Goff
- Brandon Mitchell
- Joseph Ferguson
- Sajay Antony
- Samuel Karp
- Jory Burson
- Mike Brown
- Derek McGowan
- Ramkumar Chinchani

### Actionable Agenda Items:
- distribution-spec reviews needed:
  - allow 404 on blob delete in conformance cleanup: <https://github.com/opencontainers/distribution-spec/pull/541>
  - repository definition: <https://github.com/opencontainers/distribution-spec/pull/325>

### Presentation/Discussion Agenda Items:
- distribution-spec:
  - tag listing order: <https://github.com/opencontainers/distribution-spec/issues/545>
  - allowing unordered chunk push: <https://github.com/opencontainers/distribution-spec/issues/546>
  - supporting sha512 content: <https://github.com/opencontainers/distribution-spec/issues/494> and <https://github.com/opencontainers/distribution-spec/pull/543>
- conformance
  - CI is broken: <https://github.com/opencontainers/oci-conformance/issues/106>
  - Bundlebar is dead: <https://github.com/opencontainers/oci-conformance/issues/107>
  - distribution-spec conformance tests could use a refresh
    - minimize external dependencies
    - matrix of:
      - various APIs: run push, discover, pull, destroy in order rather than setup/teardown per test
      - various types of content: image, index, sha512, artifact, subject/referrer, extended/unknown fields
    - allow individual tests and types of data to be skipped

### Notes:
-  repository definition: <https://github.com/opencontainers/distribution-spec/pull/325> - Derek and Mike reviewed and the PR was merged.
-  allow 404 on blob delete in conformance cleanup: <https://github.com/opencontainers/distribution-spec/pull/541> - The PR was reviewed and merged.
-  tag listing order: <https://github.com/opencontainers/distribution-spec/issues/545>
    -  There were no strong opinions on ordering. The group expressed the opinion that this was not actually solving the problem the issue submitter has, and declined to move this further. Tag history seemed more relevant a concern.
- allowing unordered chunk push: <https://github.com/opencontainers/distribution-spec/issues/546>
    - Ramkumar is looking at paths to support this. There are questions about how much performance improvement can be achieved. 
 - supporting sha512 content: <https://github.com/opencontainers/distribution-spec/issues/494> and <https://github.com/opencontainers/distribution-spec/pull/543>
     - Brandon is successfully breaking things (updating sha). 

Zoom chat:

00:06:28        Brandon Mitchell:       sudobmitch/demo:sha512
00:07:25        Brandon Mitchell:       https://hub.docker.com/layers/sudobmitch/demo/sha512/images/sha256-3cd92df09792ed313ce54e934db114c4d068bf78635de46d45a4377de61e3a64?tab=layers
00:07:33        Brandon Mitchell:       https://oci.dag.dev/?image=sudobmitch/demo:sha512
00:08:34        Brian Goff:     Zoom doesn't like your sha512 either.
00:12:40        Ramkumar Chinchani:     so not idempotent
00:14:01        Sajay Antony:   tag listing isn't on top of my mind but tag history.
00:25:00        Ramkumar Chinchani:     registry "capabilities" conversation?
00:27:57        Ramkumar Chinchani:     history lesson, why fixated on sha512 ... basically sha2 family in general?
00:28:40        Derek McGowan:  I assume when people say support sha512 they are hoping for blake3 or sha3. Personally I would like to not support sha512 at all
00:28:53        Ramkumar Chinchani:     blake3
00:30:24        Brian Goff:     Perf
00:31:04        Brian Goff:     blake3 -> massive parallelism
00:33:07        Brandon Mitchell:       https://pkg.go.dev/github.com/zeebo/blake3
00:33:16        Derek McGowan:  What if I want a sha256 but the hash is a fs-verity root hash rather than a sequential blob hash?
00:36:11        Sajay Antony:   Does anyone have any references for accepted hash algorithms by NIST - for e.g. Hash Functions | CSRC (nist.gov)
00:36:22        Sajay Antony:   Is that the definitive list?
Sorry.39        Sajay Antony:   need to drop for conflict. Haven't been able to move that out folks.
00:38:26        Ramkumar Chinchani:     https://csrc.nist.gov/CSRC/media/Projects/Hash-Functions/documents^ NIST not without its drama, keccak became sha3
00:38:56        Ramkumar Chinchani:     Replying to "Does anyone have any..." looks about right
00:50:46        Jory Burson (LF):       FreeBSD Runtime WG meeting is now on the public cal, next meeting is July 29 🎉
00:57:01        Samuel Karp:    Don't know yet; depends on employer approval and speaker approval
00:59:35        Joseph Ferguson (he/him):       Call For Proposals (CFP) | LF Events (linuxfoundation.org)
01:00:49        Jory Burson (LF):       Gotta run to another call!
01:00:50        Jory Burson (LF):       thanks!
01:00:51        Brian Goff:     Throw some blake in there for good measure.
01:00:55        Brian Goff:     Blake 256 and 512

## July 11, 2024

**Recording**: https://youtu.be/X9mLUpKCFrM

### Attendees:

- Tianon
- Brandon Mitchell
- Ramkumar Chinchani
- Mike Brown
- Brandon Klein
- Samuel Karp

### Actionable Agenda Items:

- distribution-spec:
  - allow 404 on blob delete in conformance cleanup: <https://github.com/opencontainers/distribution-spec/pull/541>
  - repository definition: <https://github.com/opencontainers/distribution-spec/pull/325>
  - limits on repository name: <https://github.com/opencontainers/distribution-spec/pull/542>
  - release procedure: <https://github.com/opencontainers/distribution-spec/pull/460>

### Presentation/Discussion Agenda Items:

- distribution-spec:
  - how to specify a digest algorithm when pushing by tag: <https://github.com/opencontainers/distribution-spec/issues/494> and <https://github.com/opencontainers/distribution-spec/pull/543>

### Notes:
- Brandon will give Sam access to OCI-playground

From the zoom chat:

00:05:39        Ramkumar Chinchani:     subjective ... sha is slow, sha_ni acceleration helps, blake3 is 🏎️ 
00:06:27        Brandon Mitchell:       https://github.com/opencontainers/distribution-spec/issues/494
00:10:52        Ramkumar Chinchani:     a priori "expected hash" hint makes sense imo
00:16:18        Tianon (he/him):        your example reminds me of https://github.com/buildroot/buildroot/commit/72b0c440e8914357b9a699ad9b9ed34c38f91041 which I saw the other day
00:16:24        Tianon (he/him):        "33-bit RISC-V"
00:16:28        Tianon (he/him):        (it was a typo)
00:16:46        Ramkumar Chinchani:     multiple hash support opens door for hash conversions question
00:16:59        Ramkumar Chinchani:     Replying to "multiple hash suppor..." strictly client side?
00:17:16        Tianon (he/him):        sha257 coming right up
00:17:53        Brandon Klein:  Reacted to "sha257 coming righ..." with 😂
00:19:03        Tianon (he/him):        Replying to "multiple hash suppor..." doing a full pull/push just to change the digest of a blob feels wrong but maybe unavoidable given the current API 😬 (maybe there's some minor tweaks we could make to the blob mount API?)
00:19:42        Ramkumar Chinchani:     Replying to "multiple hash suppor..." question of who bears the cost, registry or clients
00:20:27        Tianon (he/him):        Replying to "multiple hash suppor..." someone has to calculate the new digest, and the other has to at least verify it, so pull+generate/hash+blob mount seems pretty fair
00:20:59        Brandon Mitchell:       https://github.com/opencontainers/distribution-spec/pull/543
00:21:48        Tianon (he/him):        Replying to "multiple hash suppor..." if a client wants a blob to have a different digest algo than it currently does, it's very likely that client already has that blob
00:22:04        Brandon Mitchell:       https://github.com/opencontainers/distribution-spec/pull/541
00:23:01        Brandon Mitchell:       https://github.com/opencontainers/distribution-spec/pull/542/files
00:23:44        Tianon (he/him):        FreeBST, choosing to embrace the way I heard that
00:24:01        Tianon (he/him):        Replying to "FreeBST, choosing to..." "British Summer Time"
00:24:43        Brandon Mitchell:       https://github.com/oci-playground/
00:24:45        Tianon (he/him):        Replying to "FreeBST, choosing to..." and by "freeing" it, clearly the goal is to kick it back an hour so it's on UTC, because one hour off UTC is like, "why even bother?"
00:26:17        Ramkumar Chinchani:     👍
00:29:18        Ramkumar Chinchani:     Thank god for explicity encoding <alg> in the current format <alg>:<hash>
00:30:13        Samuel Karp:    the digest of the manifest is just a digest of the manifest bytes themselves (the json document)
00:30:54        Tianon (he/him):        the way in-toto solved this, by making digests a map of many algo->digest is interesting, but doesn't really help in our content-addressable world 😄
00:32:18        Tianon (he/him):        Replying to "the way in-toto solv..." trying to find a good link and failing, maybe someone else will beat me to it 😂
00:33:00        Tianon (he/him):        Replying to "the way in-toto solv..." https://github.com/in-toto/specification/blob/v1.0/in-toto-spec.md#423-hash-object-format is the spec link, although I think there's a better example somewhere else that I've seen in their docs
00:34:58        Tianon (he/him):        https://github.com/opencontainers/image-spec/blob/036563a4a268d7c08b51a08f05a02a0fe74c7268/descriptor.md?plain=1#L143
00:35:39        Ramkumar Chinchani:     There is no MUST all be same hash alg in the language
00:36:43        Ramkumar Chinchani:     sha512 manifest packing sha1 blobs?
00:38:05        Brandon Mitchell:       "It might... just... work!"
00:38:12        Ramkumar Chinchani:     blake3
00:38:58        Ramkumar Chinchani:     alg naming/mnemonic in the general case?
00:39:26        Mike Brown:     thx trianon pull me off the cliff 🙂
00:39:45        Ramkumar Chinchani:     does openssl support blake3 yet
00:40:32        Tianon (he/him):        Replying to "does openssl support..." https://github.com/openssl/openssl/issues/11613 looks like not yet
00:42:15        Ramkumar Chinchani:     https://github.com/project-zot/zot/pull/2075

## July 4, 2024

**Canceled** (US holiday)

## June 27, 2024

**Recording**: https://youtu.be/S-WzWA6p4Lk

### Attendees:

- Brandon Mitchell
- Brian Goff
- Jory Burson
- Michael Brown
- Ramkumar Chinchani
- Sajay Antony
- Tianon
- Mike Brown
- Samuel Karp

### Actionable Agenda Items:

- conformance reviews:
  - olareg: <https://github.com/opencontainers/oci-conformance/pull/101>
  - acr: <https://github.com/opencontainers/oci-conformance/pull/103>

### Presentation/Discussion Agenda Items:

- Skip next week?
- website logo fix: <https://github.com/opencontainers/opencontainers.org/pull/154> (merged)
- image-spec:
  - blake3 support? <https://github.com/opencontainers/image-spec/issues/819>
- distribution-spec:
  - allow 404 on blob delete in conformance cleanup: <https://github.com/opencontainers/distribution-spec/pull/541>
  - repository definition: <https://github.com/opencontainers/distribution-spec/pull/325>
  - limits on repository name: <https://github.com/opencontainers/distribution-spec/pull/542> (Brandon to add example)
  - release procedure: <https://github.com/opencontainers/distribution-spec/pull/460>

### Notes:

From the zoom chat:

00:17:34        Ramkumar Chinchani:     blake3-256? leave it at default?
00:19:18        Ramkumar Chinchani:     Replying to "blake3-256? leave it..." will def help with large images
00:21:08        Sajay Antony:   @Tianon - would you be able to look at - docs: add ACR conformance results. This repo really doesn't have too many active maintainers. Thank you @Brandon Mitchell for all the reviews 🙂
00:25:47        Tianon (he/him):        Replying to "@Tianon - would you ..." yeah, there's a few folks on there who should probably be removed and we should add new folks interested in stepping up, given how lax/chill that repo is 🙈 (the current list is just folks who were willing to say "sure" during one of these calls when Josh was looking for people who could review/merge since nothing here is super load-bearing)
00:26:42        Tianon (he/him):        <lolsob emoji>
00:28:42        Tianon (he/him):        that's my secret, captain ("I'm always sad")
00:39:30        Brandon Mitchell:       https://github.com/kubernetes/enhancements/pull/4642
00:50:38        Sajay Antony:   Folks I decided to stay on this one cause it was too interesting, but my other meeting is calling me in 🙁
00:50:45        Sajay Antony:   double booked life.


## June 20, 2024

**Recording**: https://youtu.be/xy_YXtvKbn8

### Attendees:
- Jory Burson
- Brian Goff
- Brandon Mitchell
- Derek McGowan
- Marcin Franczyk
- Ramkumar Chinchani
- Syed Ahmed
- Sajay Antony
- Mike Brown

### Actionable Agenda Items:
- Reviews needed:
  - <https://github.com/opencontainers/distribution-spec/pull/537>

### Presentation/Discussion Agenda Items:
- image-spec:
  - remove validation warnings: <https://github.com/opencontainers/image-spec/pull/1192> (Sajay will review)
- distribution-spec:
  - allow 404 on blob delete in conformance cleanup: <https://github.com/opencontainers/distribution-spec/pull/541>
  - repository definition: <https://github.com/opencontainers/distribution-spec/pull/325> (Brandon will update)
  - limits on repository name: <https://github.com/opencontainers/distribution-spec/issues/530> (Brandon will open a PR)
  - how to specify a digest algorithm when pushing by tag: <https://github.com/opencontainers/distribution-spec/issues/494> (Brandon will open a PR)
- OCI image/artifact as a volume source: <https://github.com/kubernetes/enhancements/pull/4642>

### Notes:
 - <https://github.com/opencontainers/distribution-spec/pull/537>
    - Derek, please review. 
 - remove validation warnings: <https://github.com/opencontainers/image-spec/pull/1192>
    - Deleted print-f. General thumbs up esp. from Sajay. Sajay will review and Brandon will clean up and prep for merge.
 - allow 404 on blob delete in conformance cleanup: <https://github.com/opencontainers/distribution-spec/pull/541>
     - Teardown function expects certain response codes and errors crop up if returns a 404. PR updates to accept 404. 
 - repository definition: <https://github.com/opencontainers/distribution-spec/pull/325>
     - Discussed last week, but action items were unclear. Is there anything that Brandon etc. needs to do proceed, or is the push to get maintainer reviews? Derek had input on path / regsitery namespace discussion. Would like to avoid the naming discussion, if possible. Want to avoid having 2 definitions for repository, depending on context. This PR may have been the first use of 'repository.' General interest in not introducing a new concept; thought also that 'repository' is a little broader than a namespace and could include tags or shas. The group looked at containerd examples for reference. The action may be to remove the term "repository" for the time being. Defining repository as a collection, and making room to include namespace or scope, could be a compromise as well. Need a separate PR to update term to something other than 'reference'. Brandon will do a little wordsmithing and bring the PR to an upcoming call. 
- limits on repository name: <https://github.com/opencontainers/distribution-spec/issues/530>
    - limit is imposed on some distributions. Some issues with upcasing and mapping. Is this something that should be resolved in the spec? General agreement that this is an issue for implementations. Could there be an error code that would be appropriate, or that we could modify that demonstrates that the issue is a registry issue? Tianon noted that there char limit issues on the client side, where names can be pushed but not pulled by dif tools. Agreement to make this an implementer note / "contact your reg. provider for naming restrictions"
- how to specify a digest algorithm when pushing by tag: <https://github.com/opencontainers/distribution-spec/issues/494>
    - Some sense that a URL param or header may be most sensible. Client could verify, but there is risk with this approach (for older clients, or with upgrades - 256 vs. Blake3, etc). There were no objections to the url param; and if the param is unsupported it should default to the sha256 version. Alt, if not supported it should fail. 

From the zoom chat:

00:11:41        Ramkumar Chinchani:     🏎️  🏎️  🏎️ 
00:28:16        Sajay Antony:   +1 on collection of manifest, tags and blobs
00:29:59        Ramkumar Chinchani:     NTD
00:38:21        Mike Brown:     this topic reminds me of 8.3 dos file names
00:39:46        Mike Brown:     pls do not use “international_business_machines” for account name
00:40:05        Jory Burson (LF):       Name must contain “Tim"
00:40:21        Jory Burson (LF):       Replying to "Name must contain “T..." That was supposed to be lowercase
00:52:06        Tianon (he/him):        I'll channel Jon and say "BLAKE3!!!" (although unfortunately I can't cosplay this one any further than saying the word 😂)
00:56:56        Tianon (he/him):        Replying to "I'll channel Jon and..." I accidentally read https://en.wikipedia.org/wiki/BLAKE_(hash_function)#BLAKE3 and now I get why Jon's always talking about blake3 🤔
00:58:18        Derek McGowan:  Replying to "I'll channel Jon and..." It is definitely worth considering. I think the “I want to use sha512” people are just looking for pain
01:01:55        Jory Burson (LF):       We are at time! Unfortunately I have to drop

## June 13, 2024

**Recording**: https://youtu.be/yYS7OQ_qAxs

### Attendees:
- Brandon Mitchell
- Derek McGowan
- Mike Brown
- Tianon
- Sajay Antony
- Brandon Klein
- Ramkumar Chinchani
- Jory Burson
- Samuel Karp

### Actionable Agenda Items:

None.

### Presentation/Discussion Agenda Items:
- image spec:
  - review needed: <https://github.com/opencontainers/image-spec/pull/1189>
  - squashfs layers? 
    - <https://github.com/opencontainers/image-spec/issues/1190>
    - <https://github.com/opencontainers/image-spec/pull/1191>
    - <https://docs.kernel.org/filesystems/fsverity.html>
    - <https://docs.kernel.org/admin-guide/device-mapper/verity.html>
  - OCI image/artifact as a volume source: <https://github.com/kubernetes/enhancements/pull/4642>
- distribution spec:
  - review needed: <https://github.com/opencontainers/distribution-spec/pull/537>
  - repository definition: <https://github.com/opencontainers/distribution-spec/pull/325>
  - limits on repository name: <https://github.com/opencontainers/distribution-spec/issues/530>
  - how to specify a digest algorithm when pushing by tag: <https://github.com/opencontainers/distribution-spec/issues/494>

### Notes:
- Image Spec
    - <https://github.com/opencontainers/image-spec/pull/1189> needs one more review. Would be a nice change. Sajay's review is requested. 
        - Once landed, Brandon has some additional improvements to build on this. Derek suggests a patch release. 
    - <https://github.com/opencontainers/image-spec/pull/1191> - Ram provided a bit more context for the proposed change in 1191 and 1190. Discussion ensued around options for optimizing, e.g. with a block-level lazy loader. Derek noted that there are some missing primitives, and Brandon noted some bugs that need to be squashed. Nevertheless, the group expressed interest in this direction/solution. The group discussed security implications, and how MIM attacks and other types of attacks could be mitigated via the provided examples. Ram will get back to the group after more investigation into some of the security considerations raised during the discussion.
    - <https://github.com/kubernetes/enhancements/pull/4642> Brandon highlighted that this PR might be interesting to maintainers, and may highlight a gap between the container and the runtime. Mike noted that this PR may provide some cleanup for a set of maintainers. Derek noted that there didn't seem to be anything here that would be a challenge for containerd. 
- Distribution Spec
    - <https://github.com/opencontainers/distribution-spec/pull/537> - Brandon noted that this is likely an easy merge. Derek will review and provide an approval. 

- Next week:
    - "What we look like"

From the zoom chat:

00:01:46        Brandon Mitchell:       https://github.com/opencontainers/distribution-spec/pull/325
00:10:48        Sajay Antony:   Patch release sounds nice.
00:22:01        Brandon Mitchell:       A block level lazy loader would be interesting.
00:37:44        Sajay Antony:   This call is really interesting and wanted to share with some folks. @Brandon  does this get auto uploaded or do we have to do this manually?
00:37:49        Brandon Mitchell:       The concern I had was if OCI should be defining media types, and variables pointing to media types, for external media types not owned by OCI. We could include a pointer saying implementations may want to support these other media types, or if we make it an OCI media type, there should be OCI specific features that necessitate.
00:38:33        Brandon Mitchell:       Replying to "This call is really ..." I manually upload the video, usually an hour or two after our Thursday call I do all the meetings for the week.
00:40:07        Brandon Mitchell:       Would be nice if the loopbacks could be skipped and a kernel driver could point directly to a file or block device.
00:41:02        Sajay Antony:   Replying to "This call is really …" Thank you so much.
00:41:14        Sajay Antony:   NTD folks.
00:42:50        Brandon Mitchell:       I'm getting myself up to speed reading https://docs.kernel.org/filesystems/fsverity.html
00:43:27        Brandon Mitchell:       And also https://docs.kernel.org/admin-guide/device-mapper/verity.html
00:55:14        Ramkumar Chinchani:     is there a good place to start looking at writing a new containerd snapshotter?
01:00:38        Jory Burson (LF):       We are at the top of the hour, for those who have other meetings (such as myself, unfortunately!)
01:01:20        Derek McGowan:  Replying to "is there a good plac..." https://github.com/containerd/containerd/pull/9362
01:01:39        Derek McGowan:  Replying to "is there a good plac..." An interesting and relevant example
01:02:10        Jory Burson (LF):       Have to drop, but noted the next time item from mike
01:02:25        Derek McGowan:  later


## June 6, 2024

**Recording**: https://youtu.be/N2S3JSEEedc

### Attendees:
- Brandon Mitchell
- Tianon
- Marcin Franczyk
- Sajay Antony
- Brian Goff
- Ramkumar Chinchani
- Syed Ahmed
- Derek McGowan
- Brandon Klein
- Mike Brown (IBM)
- Samuel Karp
- Jory Burson (LF - Late!)

### Actionable Agenda Items:

None.

### Presentation/Discussion Agenda Items:
- image-spec:
  - validation warnings: <https://github.com/opencontainers/image-spec/issues/686>
- image compatibility proposals
- squashfs layers? https://github.com/opencontainers/image-spec/issues/1190

### Notes:

From the zoom chat:

00:09:16        Tianon (he/him):        https://pkg.go.dev/github.com/opencontainers/image-spec@v1.1.0/schema?tab=importedby
00:09:41        Tianon (he/him):        https://pkg.go.dev/github.com/opencontainers/image-spec/schema?tab=importedby without the version (which I believe changes the filtering), but same tiny list
00:11:46        Sajay Antony:   Would to good to just doc this list as an example if we wanted to.
00:15:17        Tianon (he/him):        https://github.com/opencontainers/image-spec/blob/main/image-index.md#platform-variants
00:16:15        Tianon (he/him):        "architecture" and "os" in the list above that also link out to Go's documentation (GOARCH and GOOS)
00:16:27        Tianon (he/him):        where the Go team maintains lists 🙂
00:16:48        Brandon Mitchell:       Squeaky wheel. :D
00:18:32        Marcin Franczyk:        https://docs.google.com/document/d/1EDlnY1aOtj4z_E0vHOsdPvWPAfhWa9wPJmpb1Q6JZyc/edit#heading=h.i2w8scj7fiok
00:23:35        Sajay Antony:   @Derek @Tianon  Reallly would love to get your inputs as this is very impacIt is a new artifact but this is going to be used by runtimes.
00:24:34        Ramkumar Chinchani:     in terms of adoption friction, maybe do this as annotations and namoci.cpu.amd.vendor: AuthenticAMD
00:31:55        Tianon (he/him):        also @Derek McGowan and @Brian Goff are going to be better ones to ideate on a lot of this, given they're both moby engine and containerd maintainers 🙂
00:33:59        Derek McGowan:  Replying to "also @Derek McGowan ..." I’m still having my head wrapped around it. Who is the producer and consumer of these specs, seems not runtime but then runtime keeps getting mentioned
00:34:41        Brian Goff:     I think platform is the right place to put this selection information for sure.
00:35:06        Brian Goff:     Replying to "I think platform is ..." I'm not sure runtimes today would reject unknown features?
00:35:35        Brandon Mitchell:       Replying to "I think platform is ..." Correct, but would in the future.
00:36:13        Brian Goff:     Replying to "I think platform is ..." We'd also need to implement feature detection (either by probing or config).
00:36:39        Brian Goff:     Replying to "I think platform is ..." What detector does this string correspond to.
00:36:58        Brandon Mitchell:       Replying to "I think platform is ..." Ideally, image producers concerned with backwards compat would include a general image first without any features.
00:37:26        Brandon Mitchell:       Replying to "I think platform is ..." But if they specify features they require, and the runtime ignores that, the executing container would likely just fail/segfault.
00:37:52        Brian Goff:     Replying to "I think platform is ..." Also how do build tools write this content.
00:38:32        Brandon Mitchell:       Replying to "I think platform is ..." I'm guessing a more advanced platform, linux/amd64/v2+avx2, or something like that.
00:39:47        Brandon Mitchell:       Replying to "I think platform is ..." I'm really hoping these scenarios are rare, used for special application performance improvements.
00:39:52        Brian Goff:     Replying to "I think platform is ..." https://github.com/containerd/platforms/pull/6 This was fun.
00:40:45        Brandon Mitchell:       Replying to "I think platform is ..." I totally missed that `amd64` was a valid containerd platform string until today.
00:41:34        Brian Goff:     Replying to "I think platform is ..." Also are image authors really going to create different versions of the same image for this.. e.g. "this has AMD stuff, that has nvidia, this  is pure CPU but requires avx512, etc..) vs scheduling the workload to a proper node.
00:42:26        Brandon Mitchell:       Replying to "I think platform is ..." I'd imagine it would be something weird like HPC or running ML models, where they get down to the instruction level.
00:43:10        Samuel Karp:    Replying to "I think platform i..." multi-hardware images vs. scheduling distinction is my main question here too
00:44:10        Ramkumar Chinchani:     Replying to "I think platform is ..." We have a mechanism via annotations already. If this goes into OCI, it becomes policy. Or is the need to attach this as this needs to be mutated?here?  to extend the config.
00:44:57        Sajay Antony:   Replying to "@Brandon - what's th..." Or maybe rephrase - is there relactance?
00:45:35        Derek McGowan:  My perspective is that for node selection/cluster compatibility, then an artifact likely makes sense, but I would consider that out of scope for OCI currently (put that in the same bucket as pods). For image selection from within an index, then image/platform fields should be utilized. It’s not clear to me which use case is being proposed.
00:46:00        Brian Goff:     Replying to "I think platform is ..." I guess it'd be nice to not pull this multi-TB image if my system isn't even compatible with the requirements.
00:47:41        Samuel Karp:    Kubernetes control plane components (such as the scheduler) do not necessarily have access to the image registry
00:48:32        Marcin Franczyk:        HPC came with the scheduler use case, they use flux-sched in k8s https://github.com/flux-framework/flux-sched/tree/master
00:48:33        Brian Goff:     Replying to "Kubernetes control p..." But I think its reasonable to require it for a better scheduler.
00:51:50        Samuel Karp:    Replying to "Kubernetes control..." I think that could start to raise privacy/data access concerns if the scheduler is hosted by a cloud provider; i.e., granting credentials to a component like that could enable the operator of that component to exfiltrate data.
00:52:57        Marcin Franczyk:        https://doc.6wind.com/turbo-router-3/latest/turbo-router/getting-started/run-container/host-requirements.html#
00:56:47        Brandon Mitchell:       I worry about anything in a central scheduler that needs to query every entry in an index (to pull the config or a referrer).
00:59:11        Brandon Mitchell:       What if there are three containers in the pod, and each has different requirements. Things get complicated quickly.
01:01:08        Brian Goff:     Note, we are at time.
01:01:23        Jory Burson (LF):       Sorry I was tardy today, all - I will do the notes from the recording.
01:01:46        Jory Burson (LF):       I have to drop as well , but this sounds like it’s been a good discussion
01:02:04        Ramkumar Chinchani:     https://github.com/opencontainers/image-spec/issues/1190

## May 30, 2024

**Recording**: https://youtu.be/dAPUxJMSWaQ

### Attendees:
- Jory Burson
- Brandon Mitchell
- Ramkumar Chinchani
- Tianon
- Mike Brown, Daisy's Dad
- Derek McGowan
- Brian Goff
- Marcin Franczyk
- Samuel Karp
- Sajay Antony
- Jon Johnson

### Actionable Agenda Items:
- Clean-up on mailing lists and GitHub repo permissions - e.g. Security. 
    - Overall interest in an audit of everything
    - And also understanding how everything is controlled / knitted together
- Take a survey for Jory about Standards? https://www.research.net/r/RX7BJWM

### Presentation/Discussion Agenda Items:
- image-spec:
  - Replacing validation library: <https://github.com/opencontainers/image-spec/pull/1189>
- large image support:
  - <https://github.com/opencontainers/runtime-spec/issues/1254>
  - <https://github.com/opencontainers/image-spec/issues/1190>
  - <https://github.com/opencontainers/image-spec/pull/1191>
  - <https://github.com/opencontainers/distribution-spec/issues/536>
  - <https://github.com/opencontainers/distribution-spec/pull/537>
- image compatibility wg - opinions on the proposals

### Notes:
- image-spec:Replacing validation library: <https://github.com/opencontainers/image-spec/pull/1189>
    - Brandon highlighted recent cleanup work he had done to replace the outdated validation library. 
    - Some conversation on necessity to buffer; Brandon will resolve the comment on the issue as Tianon was satisfied. 
- Ramkumar provided context for the large image support issues.
    - <https://github.com/opencontainers/runtime-spec/issues/1254>
    - <https://github.com/opencontainers/image-spec/pull/1191> - there are some open questions on this PR, and others noted that there appears to be more work needed before it would be ready to be standardized at OCI
    - <https://github.com/opencontainers/distribution-spec/pull/537>: include link to RFC to help direct people to implement. Brandon will update his review with new language. Should the language be a "may" or "should" for a registry? No strong opinion, but Brandon plans to go with "Should".
- image compatibility wg - opinions on the proposals
    - Feedback and input is requested on this material. Please review the notes and recording from the previous week to refresh and be ready to provide input

Zoom chat:

00:04:16        Tianon (he/him):        "if you got this far in the video, put pickles down in the comments!"
00:07:06        Tianon (he/him):        I think there's a TOB list, but I believe that's public, and IIRC there's a separate private list for the trademark board that might need some updates (but that's less relevant to this OSS group, since that membership is "OCI members" explicitly)
00:08:21        Tianon (he/him):        https://groups.google.com/a/opencontainers.org/g/tob lots of spam in here 😄
00:09:55        Jory Burson (LF):       Replying to "https://groups.googl..." You don’t want to hear about an exciting future investment opportunity?
00:19:11        Mike Brown:     the k8s kep for mounting an artifact as a volume https://github.com/kubernetes/enhancements/pull/4642
00:21:29        Mike Brown:     interesting we were talking about http3 last week as well
00:22:24        Brian Goff (@cpuguy83): We've discussed adding erosfs and squashfs support in containerd, btw.
00:23:12        Ramkumar Chinchani:     application/vnd.oci.image.layer.erofs
00:23:49        Samuel Karp:    +1 to what Brandon was saying
00:24:06        Derek McGowan:  Replying to "application/vnd.oci...." If there is a specific way it should be used, like it has overlayfs whiteouts in it. If it is just a plain rootfs then it isn’t necessary
00:29:45        Derek McGowan:  😂
00:30:33        Derek McGowan:  Agreed, call out the use case in point to the HTTP spec. Don’t duplicate language from the http spec
00:31:26        Ramkumar Chinchani:     dist-spec v1.1.1
00:35:25        Mike Brown:     sry DRA black hole taking up all bandwidth
00:35:36        Sajay Antony:   Need to drop folks. Sorry again, standing meeting is conflicting this with. I'll try to watch th recordings for this.

## May 23, 2024

**Recording**: https://youtu.be/3Ul77d89DC4

### Attendees:
- Mike Brown (IBM)
- Tianon
- Brandon Mitchell
- Marcin Franczyk
- Joe Huang
- Ramkumar Chinchani
- Jory Burson
- Jon Johnson
- Sajay Antony
- Derek McGowan
- Syed Ahmed
- Samuel Karp

### Actionable Agenda Items:

None.

### Presentation/Discussion Agenda Items:
- Image Compatibility WG <https://youtu.be/IawP_05firA?si=Ow9BPbp8mglW3yUX&t=2520>
- How to handle multiple inactive maintainers? <https://github.com/opencontainers/image-spec/pull/935>
- Consider replacing <https://github.com/xeipuuv/gojsonschema> with <https://github.com/santhosh-tekuri/jsonschema>
- Add support streaming patch requests: <https://github.com/opencontainers/distribution-spec/pull/404>
- Drop references to registry, replace with repository or leave ambiguous: <https://github.com/opencontainers/distribution-spec/pull/325>

### Notes:
- Quick update from Image Compatibility WG - short meeting which was recorded; Maintainer feedback is requested from Marcin. Largest question is whether it makes sense to have an external / separate artifact, and feedback on this question in particular is important.
- How to handle multiple inactive maintainers? <https://github.com/opencontainers/image-spec/pull/935> 
    - This is an old issue, speaking to the maintainers guide. Scenario to address is what happens when there is a shortage of active maintainers. 
    - Existing document is largely copied from runc spec. Open question is the impact on maintainer reviews. 
    - Some discussion on whether this is dependent upon the kind of issue that is being raised - e.g. whether it is an urgent issue vs. a feature proposal. Each project should make public how their decision process is being made (e.g. whether they do or do not allow self lgtms). Some concern over potential for people to find proxies (in bad faith).
    - vbatts is unlikely to want to maintain this PR, but Brandon requests that the group consider the maintainer availability question as it could impact the ability to cut a release.
- - Consider replacing <https://github.com/xeipuuv/gojsonschema> with <https://github.com/santhosh-tekuri/jsonschema>
    - Brandon has found some other projects that appear to be better maintained; is considering exploring other options to propose for replacing this library. Group is generally +1 to this activity.
    - Would be nice to use something that was included in the Go standardlib, but.
    - Should we fork and adopt the fork? That is one option. Need to determine if there is an appetite for this. 
- Add support for streaming patch requests: <https://github.com/opencontainers/distribution-spec/pull/404>
    - Docker has an implementation, but we don't have anything defined in the spec. May need more documentation about what happens when this is omitted. Derek noted that containerd may have also had a PR (https://github.com/containerd/containerd/pull/7459) about this. Jon noted that transfer encoding is chunked, and multiple patches that are chunked. The understanding of the group is that this is for transfer encoding. Brandon noted that other registries don't seem to support this well, but users nonetheless file PRs. Derek & Jon both noted that there are use cases wherein they do not know the size of a blob/chunk, and would be in favor of finding a solution. Jon suggested that the group look for other RFCs about setting content length. Derek noted that you can not set content length and perhaps we can add clarifying language. Jon noted this may be helpful for those who use examples as normative requirements for the spec. May need to specifically call out that this is optional. 
        - Does HTTP/2 even allow chunked encoding? Ramkumar says he doesn't believe that it is.
            - “HTTP/2 uses DATA frames to carry message payloads. The chunked transfer encoding defined in Section 4.1 of [RFC7230] MUST NOT be used in HTTP/2”
        - If we take out length, what does content range reset to? 
        - What are the clients doing today?
- Drop references to registry, replace with repository or leave ambiguous: <https://github.com/opencontainers/distribution-spec/pull/325>
    - Deferred to next meeting

Zoom chat:

00:13:57        Sajay Antony:   Wouldn't it better to call out the exception in the individual repos rather than each project define the full set?
00:29:38        Mike Brown:     https://github.com/containerd/containerd/pull/7459
00:35:10        Ramkumar Chinchani:     Does HTTP/2 even allow chunked encoding?
00:35:40        Ramkumar Chinchani:     else will tie this behavior to only HTTP/1.x
00:37:06        Sajay Antony:   NTD - I seem to have a regular 10:30 PST  which I will try to schedule out. Sorry folks.
00:37:11        Mike Brown:     “HTTP/2 uses DATA frames to carry message payloads. The chunked transfer encoding defined in Section 4.1 of [RFC7230] MUST NOT be used in HTTP/2”
00:38:03        Derek McGowan:  Agree with Ram’s point of it shouldn’t tie it to chunked encoding then
00:38:23        Mike Brown:     see https://www.rfc-editor.org/rfc/rfc9113.html
00:39:50        Ramkumar Chinchani:     HTTP/2 is old ... HTTP/3
00:45:28        Ramkumar Chinchani:     TCP path MTU all over again?
00:47:32        Ramkumar Chinchani:     This is one place we "diverge" from HTTP spec
00:47:36        Ramkumar Chinchani:     :(
00:50:06        Tianon (he/him):        https://github.com/opencontainers/distribution-spec/issues/213
00:50:44        Tianon (he/him):        also https://github.com/opencontainers/distribution-spec/pull/203
00:55:08        Tianon (he/him):        I don't know how faithful it is to the old content, but https://github.com/distribution/distribution/blob/main/docs/content/spec/api.md has quite a few examples of the correct syntax (and a handful of the wrong syntax)

## May 16, 2024

**Recording**: https://youtu.be/xpjYpn7VxHo

### Attendees:
- Jory Burson
- Tianon
- Brian Goff
- Derek McGowan
- Brandon Mitchell
- Michael Brown
- Syed Ahmed
- Sajay Antony
- Ramkumar Chinchani
- Samuel Karp
- Mike Brown

### Actionable Agenda Items:
- Jory will send out a KubeCon attendance poll (for the purposes of planning an in person meeting)

### Presentation/Discussion Agenda Items:
- image-spec:
  - mediaType syntax: <https://github.com/opencontainers/image-spec/pull/1182>
  - toml support: <https://github.com/opencontainers/image-spec/pull/1074>
- distribution-spec:
  - TOC: <https://github.com/opencontainers/distribution-spec/pull/471>
  - Require a content-type header: <https://github.com/opencontainers/distribution-spec/pull/477>

### Notes:
- Clarifying Media Type Syntax (<https://github.com/opencontainers/image-spec/pull/1182>
    - Nailing down whether parameters are or are not permitted: RFC is for a header on HTTP (for request or response) - are there any other examples of file formats with embedded mimetypes, that might have use cases for one approach or the other?
        - JSON Schema? Imported by UI not by media type. 
    - Challenges - filtering on a manifest or artifact type; what if params are based for a charset, etc. Problems may arise if these are expressly allowed. 
    - Parameters can make the implementations much harder - A group wanted to be able to use this for versioning. But issues have been raised. No clear use case at this point.
    - No strong support for permitting params. But we don't understand the purpose for them in the original RFC. 
        - No params on media type in IETF list
        - Mindful of Technical validity that technically doesn't work (spongebob example from Tianon)
- TOML Support (https://github.com/opencontainers/image-spec/pull/1074)
    - No real support for this. Closing the PR.
- Distribution Spec - TOC (https://github.com/opencontainers/distribution-spec/pull/471)
    - Changes order to keep notation up top and use cases below.
    - Does the order below match? Yes, PR makes it match.
    - Simple yes - 
- Should we require a content-type header (https://github.com/opencontainers/distribution-spec/pull/477)
    - Changing "should" to "must" - when neither happens, you get an undefined behaviour. 
    - Header ought not be the place to put a "must" - registry may error out, but the Header isn't meant to be more trusted than the content. 
    - Is "should" simply a soft "must" - it's the knob we can turn to shift behaviour over time. Potentially say, they must match (Header and Content) if they are both provided. 
    - Registries can enforce if they want to (see: "should") but we don't want to make a spec change. 
    - Decision: close PR.
- AOB
    - Derek is still working through a rebase of https://github.com/opencontainers/distribution-spec/pull/66
    - Maintainer approvals - mix of changes that are superficial or related to testing. For Substantive, Actual changes to the spec, should that require a majority vote of the maintainers (not just a couple of lgtm). We don't really have governance around that kind of thing. 
        - Brandon notes that he assumed some of that would happen at release time. 
    - Example: changes to Governance.md - probably needs more than a lgtm.
    - What needs to be voted on?
        - Clarity probably needed on spec- items. don't want to cause a delay at release - Ideally there are no surprises at release time. 
        - Maybe take on more incremental releases.
    - Some of this may go back to lack of maintainer involvment - sometimes it takes a while for issues or topics to be "discovered"
    - Balance agility vs. formal process. Most PRs are probably fine at the "lgtm" level. What scenarios require a higher threshold?
        - Any breaking change (example: https://github.com/opencontainers/distribution-spec/pull/470)
        - Any objections - that could force a quorum vote. Maybe there is also a time delay (e.g. 7 days)
            - Note that for OCI, this is not a destructive activity as there is still the "release" vote
        - Could also say, "unless objections are raised, PR will be merged on DD MM"
        - Could add a label (e.g. vote required, discussion needed) to clarify items that really need more maintainer input
    - Mike Brown gathering more information about how people want to use OCI in "pods"

Zoom chat session:

00:03:51        Tianon (he/him):        it's really really laggy at the scale we use it 😭
00:04:05        Tianon (he/him):        if I accidentally leave the tab open, my computer starts to slow down
00:04:11        Jory Burson (LF):       Replying to "if I accidentally le..." ha
00:15:00        Tianon (he/him):        so instead of "foo/bar.v2" they want "foo/bar;version=2.0" (for example)
00:15:14        Sajay Antony:   I really hope people go down that way .
00:19:37        Tianon (he/him):        https://en.wikipedia.org/wiki/Wikipedia:Chesterton%27s_fence (for anyone unfamiliar with "Chesterton's fence" ❤️)
00:19:38        Sajay Antony:   This as mediaType make the usecase for filtering really complicated - application/json; charset=utf-8; version=1.0
00:20:02        Sajay Antony:   Replying to "https://en.wikipedia..." I was going to ask.
00:20:23        Tianon (he/him):        Replying to "https://en.wikipedia..." very very similar/related to Amazon's "respect what came before"
00:21:36        Ramkumar Chinchani:     artifactType is "private" to implementations, and there is a way to no parameter for mediaType but yes parameter for artifactType etc?
00:22:17        Ramkumar Chinchani:     do we /api/v1 or /api and mediatype=v1, both are valid ways to version APIs
00:22:25        Ramkumar Chinchani:     Replying to "do we /api/v1 or /ap..." ^ for example
00:22:26        Tianon (he/him):        Replying to "artifactType is "pri..." I think the complexity is that the referrers API (and future work) allows filtering based on artifactType, and thus opens questions about whether that filtering should or should not respect parameters
00:22:40        Ramkumar Chinchani:     Replying to "artifactType is "pri..." ^ also this
00:24:27        Ramkumar Chinchani:     https://github.com/spf13/viper
00:26:07        Tianon (he/him):        encoding/json/v2 · golang/go · Discussion #63397 (github.com)
00:26:24        Tianon (he/him):        Replying to "encoding/json/v2 · g..." neverending lament that they're not solving _my_ issues with encoding/json 😂
00:30:11        Brandon Mitchell:       https://github.com/opencontainers/distribution-spec/pull/471
00:35:39        Tianon (he/him):        distribution/docs/content/spec/manifest-v2-2.md at main · distribution/distribution (github.com)
00:35:46        Sajay Antony:   Folks need to drop for another meeting that I can't skip. Thanks for brining up the image spec items first @Brandon Mitchell
00:35:48        Tianon (he/him):        Replying to "distribution/docs/co..." looks like Docker media types were "should"
00:37:33        Jory Burson (LF):       https://github.com/opencontainers/distribution-spec/pull/66
00:37:38        Jory Burson (LF):       That one right Derek?
00:37:40        Tianon (he/him):        Replying to "distribution/docs/co..." distribution/docs/content/spec/api.md at main · distribution/distribution (github.com) doesn't explicitly say yes or no on content-type being MUST but the canon example includes it
00:54:12        Brian Goff (@cpuguy83): Love that big green button.
00:54:25        Brandon Mitchell:       We have PRs open for less than 7 days?
00:55:29        Brandon Mitchell:       Example of a breaking change we merged last week: https://github.com/opencontainers/distribution-spec/pull/470
00:58:42        Brandon Mitchell:       I'll write up the change to the governance doc and force push to main.
01:03:06        Jory Burson (LF):       Oh shoot, I need to drop for another call
01:05:35        Ramkumar Chinchani:     runnable workloads + non-runnable inference data

## May 9, 2024

**Recording**: https://youtu.be/LDGIc8gIiDo

### Attendees:
- Jory Burson (LF Staff - notetaker)
- Mike Brown
- Brandon Mitchell
- Derek McGowan
- Marcin Franczyk
- Ramkumar Chinchani
- Sajay Antony
- Brian Goff
- Daisy (yellow Lab)

### Actionable Agenda Items:
- Who's taking notes?

### Presentation/Discussion Agenda Items:
- image compatibility wg update
- auth wg status
- Tag pagination: <https://github.com/opencontainers/distribution-spec/pull/470>
- mediaType: <https://github.com/opencontainers/image-spec/pull/1182>

### Notes:
- In person Meeting for OCI
    - **Action:** Jory will issue a poll in Slack to determine who is currently planning to attend KubeCon US in Utah. 
- image compatibility wg update
    - Marcin reported that the group is reviewing two different solutions for image artifacts. The group is still prototyping. Participants are encouraged to join the Image WG to weigh in, or provide input on this call. Sanjay suggested that it would be better to discuss the proposals with the group, as there are a lot of materials. The proposals to review are located at: 
        - https://github.com/opencontainers/wg-image-compatibility/tree/main/docs/proposals
    - Derek asked if there were anything controversial, or important to focus on as a first or secondary priority. Sajay suggested taht the Image WG could identify which points are controversial, and/or to develop a framework for structuring the feedback & review of the 6 proposals. Brandon emphasized that he didn't want the maintainers to generate any surprises for the Working Group. Mike recommended bringing in a Docker representative,
    - Marcin suggested that a future OCI weekly call be dedicated for reviewing the proposals. Brandon provided a counter suggestion to host the discussion and to provide the recording. 
        - **Action**: Brandon will organize the discussion and recording
- auth wg status
    - Brandon reported that there are a lot of people interested in the output of this group, but very few interested in joining the WG to do the work. The work needed is to write the spec proposal, and no one has had much time to write this document. 
    - Jory suggested that the group consider appropriating funds for a contractor to write the specification.
    - Ramkumar noted that the work addresses real problems and that these issues are important, but the issues are not "burning" and the will to resolve them has been low. Ramkumar provided an example and the group discussed. 
    -  Brandon re-iterated that the main issue to resolve is finding a person(s) to write the documented issues up into a spec proposals.
        -  FreeBSD WG and others may also be in a similar position; visibility into their efforts is low. 
-  Tag pagination and Media Types PRs
    -  Brandon shared the two PRs that he continues to work on: - Tag pagination & Media Types: <https://github.com/opencontainers/distribution-spec/pull/470 and <https://github.com/opencontainers/image-spec/pull/1182>
    -  Brandon noted that he had some feedback on the PRs from Tianon, and covered some additional points of feedback that had been brought from the group and reg clients have provided previously
    -  It was clarified that the Tag Pagination changes are technically breaking, but the impact is low and the risk is low. Derek will provide a review. 
    -  Brandon gave further input on the Media Types PR.
    -  Derek asked if the group could land https://github.com/opencontainers/distribution-spec/pull/66 and include it in a v1.2 release. Brandon asked if other groups, other than containerd, have implemented. Derek will do a rebase and clean up the PR. The group will also look for other groups that have implemented the proposal. The group discussed namespacing, briefly. 
-  AOB
    -  Re-consider having a conversation about "tenets/patterns/principles" - potentially have this conversation in person, or have the conversation in a GH thread.

zoom chat:

00:08:15        Sajay Antony:   @Marcin - is there a doc or a write up ?
00:09:00        Brandon Mitchell:       https://github.com/opencontainers/wg-image-compatibility/tree/main/docs/proposals
00:10:11        Sajay Antony:   Is there a prioritized matrix or something that would help the order of review of these 6.
00:10:47        Mike Brown:     yeah would make sense to have intermittent larger tent meetings to review directions
00:11:16        Mike Brown:     larger tent meaning other outside the wg oci members/maintainers/toc members
00:16:26        Ramkumar Chinchani:     https://github.com/opencontainers/tob/blob/main/proposals/wg-auth.md#scope
00:16:58        Ramkumar Chinchani:     "should authentication flow start with a /v2 ping"?
00:17:07        Ramkumar Chinchani:     Replying to ""should authenticati..." multi-tenancy? enable both bearer and basic at same timeltiple WWW-Authenticate challenges"?
00:18:03        Ramkumar Chinchani:     etc..
00:18:42        Mike Brown:     marcin on platform/compatibility effort there is a large effort underway in k8s to specify changes to the device class claims .. and downward api specifying pod resource requirements
00:19:38        Mike Brown:     https://github.com/kubernetes-sigs/wg-device-management
00:19:46        Mike Brown:     note use cases
00:20:55        Marcin Franczyk:        Right, I attended the last meeting. I belive the effort from our wg is not overlaping with them but could cover some missing gaps. I am going to talk to John Belamaric to discuss this.
00:21:05        Marcin Franczyk:        But thanks for pointers anyway.
00:21:40        Mike Brown:     the combo of the new device claim “types” and requirements passed down through the downward api .. are the important parts..
00:22:08        Sajay Antony:   +1 on the Basic Bearer issue.
00:22:14        Mike Brown:     reason:  see COS os’s that have a default set of devices .. eg. RHCOS
00:26:09        Sajay Antony:   Folks Need to drop for another conflict that just came up.
00:29:02        Mike Brown:     go marcin!
00:30:12        Brandon Mitchell:       https://github.com/opencontainers/wg-freebsd-runtime
00:31:05        Ramkumar Chinchani:     FreeBSD folks are trying to standardize around OCI
00:31:08        Derek McGowan:  For OCI get togethers, we should make sure Brandon gets a boat big enough to host the whole group
00:32:01        Ramkumar Chinchani:     Replying to "FreeBSD folks are tr..." https://www.youtube.com/watch?v=pggcc6fi-ow
00:32:45        Jory Burson (LF):       Replying to "For OCI get together..." Let’s go with a Yacht
00:37:48        Brandon Mitchell:       https://github.com/opencontainers/image-spec/pull/1182
00:39:05        Brandon Mitchell:       https://tools.ietf.org/html/rfc6838#section-4.2
00:43:13        Jory Burson (LF):       Which PR Derek?
00:43:31        Derek McGowan:  https://github.com/opencontainers/distribution-spec/pull/66
00:53:15        Jory Burson (LF):       Anything anyone would like to add for next week
00:53:21        Jory Burson (LF):       What kind of dog
00:53:49        Mike Brown:     yellow lab
00:55:04        Jory Burson (LF):       What is the dogs name?


## May 2, 2024

**Recording**: https://youtu.be/kKzlfUcoowY

### Attendees:
- Brandon Mitchell
- Tianon
- Marcin Franczyk
- Ramkumar Chinchani
- Sajay Antony
- Toddy
- Jory Burson (LFPM)
- Derek McGowan
- Brian Goff
- Samuel Karp
- Brandon Klein
- Michael Brown (AWS)
- Mike Brown (IBM)

### Actionable Agenda Items:

None.

### Presentation/Discussion Agenda Items:
- Tag pagination: <https://github.com/opencontainers/distribution-spec/pull/470>
- mediaType: <https://github.com/opencontainers/image-spec/pull/1182>
- distinguishing artifacts: <https://github.com/opencontainers/image-spec/pull/1141> 

### Notes:

- Distinguishing Artifacts:
    - Question: Index with non-runnable images and non-runnable images in the same context - is this something we would want to encourage? Should OCI recommend, recommend something different, or not make a recommendation.
    - Guidance was to make config digest unique. Moby maintainer opened the PR. Agreement with the goal, but question as to whether this is the best execution. Index with non-runnable images and non-images in the same context - is this something we would want to encourage? Point: this exists a lot already (buildkit). Counterpoint: that was bad. Value to document, "if you're going to do it, here's how to do it without breaking the world - here's how to mitigate / defend." Or, we provide the ideal path we want people to adopt, and record the 1-2 use cases that break. Azure has seen this used, so has enabled even though not called in the spec. Value in at least documenting the behavior and expectation. Should be able to pack all targets in one index on a single tag, let the runtime chose its preference. Platform should be something the runtime can see - order might matter, and people may build in a way that confuses runtimes. Established conventions have established some precidence for behavior. The should use platform object, but no way to prevent (aside from implementation guard rails). Spec does give guidance on the ordering of the runtime. Note that this is "Guidance" but not normative to the spec. Other point: what will older clients do? Don't want to break for those clients.
    - How could a runtime entry pick up on different types (e.g. I have two AMD-64s, which is the best)? - that's containrd works. API does need some change, may behoove us to update this as well (platform selector). Consider: roundtripping of artifacts. Marcin notes that his prototyping has not yielded succssful/ideal results. If this continues, will want to change how platform selector works. Marcin <> Mike's Colleague to explore & knowledge share. Other directions should be considered. Annotations a cool way to extend, but hard to version. 
    - Options:
        - Separate runnable from non-runnable index lists
        - Order of entries (runnable is always first)
        - Using known platforms only for for runnable entries
        - Using artifactType for non-runnable entry
        - Additional Annotation
        - Create another field
        - Indexes as a sub-index (Artifactory may have an issue with nested indexing, talk to JFrog)
    - 2.0 discussion?:
        - What manifest types are we allowed to link to?

Notes from zoom chat:

00:08:44        Brandon Mitchell:       For those not reading the notes: https://github.com/opencontainers/image-spec/pull/1141
00:11:30        Brian Goff (@cpuguy83): Not ignoring, reading 🙂
Been awhile since I looked at this.
00:19:31        Brandon Mitchell:       https://github.com/opencontainers/image-spec/pull/1141
00:23:20        Ramkumar Chinchani:     https://github.com/containerd/runwasi
00:24:04        Brandon Mitchell:       We can't stop anything, but we can give guideance.
00:25:01        Sajay Antony:   Ok Tianon - 5 yrs ago I wrote this up for dotnet - Dotnet Cloud Native Applications - HackMD
00:25:44        Derek McGowan:  Agreed on guidance, we should make sure that there is a clear way to define newer types of images via artifact types (and able to use platforms). The guidance should be how to make it backwards compatible for runtimes which may not check artifact type today.
00:27:28        Mike Brown:     use the first “match”
00:33:04        Sajay Antony:   Unfortunately I need to drop to but the artifact guidance is sparse due to some challenges in mix of artifacts and images - image-spec/artifacts-guidance.md at main · opencontainers/image-spec (github.com)
00:35:04        Sajay Antony:   ohh nested index.
00:37:37        Ramkumar Chinchani:     without guidance, likely leads to divergence and makes it harder in future to converge/push standards
00:38:14        Brian Goff (@cpuguy83): Seems like the guidance here is using `artifactType` to save a round trip to drill down into the manifest data.
00:45:14        Brian Goff (@cpuguy83): Replace "artifactType" with a config descriptor 😆
00:45:58        Tianon (he/him):        Replying to "Replace "artifactTyp..."

I mean, you say this joking, but I was literally thinking about putting the config digest on an annotation in the manifest's index descriptor just the other day 😁
00:46:23        Jory Burson (LF):       How do you guys evaluate your options typically
00:46:32        Tianon (he/him):        Replying to "Replace "artifactTyp..."

I'll channel Jon: just set "data"
00:48:30        Brandon Mitchell:       Speaking of making a decision, cough cough, maintainers. 😜  https://github.com/opencontainers/distribution-spec/pull/470
00:48:40        Mike Brown:     it is interesting that index has many of the elements but not config descriptor
00:50:30        Brian Goff (@cpuguy83): For runtimes, the only way (that I can see, atm) to stick something in the index that is not "runnable" that does not break existing runtimes would be to use a garbage platform.
00:52:22        Tianon (he/him):        Replying to "For runtimes, the on..."

if I try to run a Tianon-Hacked-Up-Java image on a runtime which doesn't support it, is there functionally much difference between "image not supported" and "can't extract layer" besides a bit of bandwidth and possibly storage?  arguably the user intent was to pull the image, so the bandwidth and storage are not unexpected (from the user POV)
00:52:42        Tianon (he/him):        Replying to "For runtimes, the on..."

or even the infamous, "exec format error"
00:56:06        Ramkumar Chinchani:     ntd
00:57:18        Brian Goff (@cpuguy83): Replying to "For runtimes, the on..."

Agree its the same.
00:57:43        Tianon (he/him):        Replying to "For runtimes, the on..."

in other words, put linux/amd64 on that java image, let the world burn 🔥
00:58:23        Brian Goff (@cpuguy83): Replying to "For runtimes, the on..."

jdk12/java
00:59:06        Brandon Klein:  g2g, have a great weekend all!
01:00:24        Brian Goff (@cpuguy83): Mixed layer compression types 🙂
01:00:47        Tianon (he/him):        tianon/test:xn--uo8h (dag.dev) birb
01:00:52        Brian Goff (@cpuguy83): Pretty sure buildkit works that way.
01:00:58        Tianon (he/him):        (this is a cursed image I pushed a long time ago)
01:01:15        Mike Brown:     yeah we need llm’s stored as a blob

## April 25, 2024

**Recording**: https://youtu.be/En2YMj-KxII

### Attendees:
- Brandon Mitchell
- Sajay Antony
- Samuel Karp
- Derek McGowan
- Ramkumar Chinchani
- Amye SP 
- Jory Burson
- Tianon
- Mike Brown (IBM)
- Brian Goff
- Jon Johnson

### Actionable Agenda Items:
- image-spec:
  - Update Go version: <https://github.com/opencontainers/image-spec/pull/1170>
- distribution-spec:
  - Conformance pull should not require tag listing: <https://github.com/opencontainers/distribution-spec/pull/476>
  - Conformance report is broken: <https://github.com/opencontainers/distribution-spec/pull/534>
  - Tag pagination: <https://github.com/opencontainers/distribution-spec/pull/470>

### Presentation/Discussion Agenda Items:
- Welcome Jory! (LF Standards team)

### Notes:
- Conversation of if/when we should consider adding maintainers

Notes from zoom chat:

00:10:57        Sajay Antony:   In converse - There is drama because people care.
00:15:09        Amye Scavarda Perrin:   Drupal did it first
00:15:12        Derek McGowan:  And if you have better information about how other standards work
00:15:17        Brian Goff (@cpuguy83): ❤️
00:15:18        Derek McGowan:  For many of us, this is the only “standards” we work on
00:15:35        Amye Scavarda Perrin:   100% - I’m really delighted to be handing off to Jory + the LF standards team
00:16:49        Derek McGowan:  I would say a “2.0” is essentially a new spec
00:17:06        Derek McGowan:  And should have a new set of maintainers
00:17:52        Jory Burson (LF):       Do you have a doc like Design Principles or priorities of constituencies?
00:19:14        Samuel Karp:    We don't have, but that sounds useful
00:19:16        Brandon Mitchell:       https://github.com/opencontainers/image-spec/blob/main/considerations.md#extensibility
00:19:19        Mike Brown:     2.0 :-O
00:19:27        Ramkumar Chinchani:     https://github.com/opencontainers/tob/blob/main/CHARTER.md
00:19:27        Sajay Antony:   FAQ is the closest - FAQ - Open Container Initiative (opencontainers.org)
00:21:44        Tianon (he/him):        https://github.com/opencontainers/image-spec/pull/935 vbatts ahead of his time
00:21:58        Derek McGowan:  Would be good to have that, more specific than charter but not so low level as working groups
00:23:52        Tianon (he/him):        the people who can tell Chesterton why the fence is here 👀
00:26:31        Sajay Antony:   @Brandon holding up a lot
00:30:36        Derek McGowan:  So we need an artifact manifest?
00:33:16        Jory Burson (LF):       Qq - what are the main OSS implementations of OCI Specs
00:33:44        Samuel Karp:    runc is the reference implementation of the runtime-spec and the most widely used
00:34:14        Brandon Mitchell:       Some of the specs have a list that people contribute to, but it's far from a complete list. E.g. https://github.com/opencontainers/image-spec/blob/main/implementations.md
00:34:28        Samuel Karp:    CNCF Distribution is afaik the largest OSS implementation of the distribution-spec; there are also very large proprietary implementations by Docker, cloud providers and others
00:34:50        Sajay Antony:   Reacted to "CNCF Distribution is..." with ❤️
00:35:21        Samuel Karp:    The image-spec is interpreted by a bunch of things; in my space it'd be higher-level container runtimes like containerd, Docker, CRI-O, podman, etc.
00:36:23        Samuel Karp:    FreeBSD too!
00:36:25        Tianon (he/him):        lots and lots of jq and bash 😀
00:36:56        Derek McGowan:  What about rkt, that was the catalyst for creating OCI in the first place 😛
00:37:11        Amye Scavarda Perrin:   Rkt is archived
00:37:23        Amye Scavarda Perrin:   Reacted to "What about rkt, that..." with 😆
00:37:31        Amye Scavarda Perrin:   But yes, we can talk about that too
00:37:32        Samuel Karp:    Kubernetes doesn't really implement anything in OCI, interestingly enough
00:37:35        Brandon Mitchell:       Getting common agreement is how we get our most active discussions, to phrase it politely. :D
00:39:21        Derek McGowan:  I mention rkt because for history, they announced https://github.com/rkt/rkt/blob/master/Documentation/app-container.md which freaked out the industry that we were going to have s
tandards wars, OCI fixed that, pretty quickly too
00:39:24        Amye Scavarda Perrin:   A good speedrun
00:39:44        Tianon (he/him):        k8s is definitely the most popular way to do multi-host orchestration, but I bet the amount of non-multi-host dwarfs it 👀
00:39:55        Amye Scavarda Perrin:   That’s a good point, Derek. Want to take us towards that next? (After Brandon)
00:39:57        Jory Burson (LF):       Gonna go re-read Phippy & Friends lol
00:40:49        Derek McGowan:  Which is cool and scary
00:41:09        Sajay Antony:   AI + OCI is something I hear on a weekly basis.
00:45:25        Amye Scavarda Perrin:   Design principles/roadmap/scoping documentation ++
00:48:11        Tianon (he/him):        if we say DAG three times, I bet Jon will show up
00:48:22        Amye Scavarda Perrin:   We have 15 minutes 😄
00:49:26        Sajay Antony:   I honestly miss the Vbatts energy.
00:49:40        Amye Scavarda Perrin:   (He busy)
00:49:48        Brandon Mitchell:       I'll start adding cupcakes to my reviews.
00:50:35        Brandon Mitchell:       Wait, I only said DAG once
00:50:50        Sajay Antony:   Wow .. @Jon Johnson
00:50:58        Sajay Antony:   DAG spell.
00:51:36        Tianon (he/him):        "what if we had _more_ DAGs?"
00:51:47        Derek McGowan:  I have been out on paternity so I missed the “As Amye leaves us for other pastures” announcement
00:52:06        Amye Scavarda Perrin:   We were waiting until Jory was available :D
00:52:24        Amye Scavarda Perrin:   I’m here through the end of May to help transition things off in both OCI and CNCF
00:53:45        Brandon Mitchell:       This is what it looks like when a large group all tries to nerd snipe Jon.
00:59:54        Samuel Karp:    "my newest Go library that I wrote" - should I be scared?
01:00:13        Tianon (he/him):        https://github.com/jonjohnsonjr/targz
01:00:19        Tianon (he/him):        Jon's too slow, I'm gonna share it with the class
01:00:43        Tianon (he/him):        proud of our boi, writing some great Go
01:02:03        Mike Brown:     gsip love it
01:02:15        Amye Scavarda Perrin:   operations@opencontainers.org
01:03:15        Ramkumar Chinchani:     rough consensus and working code?

## April 18, 2024

**Recording**: https://youtu.be/A6KFgdz3DrE

### Attendees:
- Tianon
- James Sturtevant
- Sajay Antony
- Nathan Rini
- Brandon Mitchell
- Ramkumar Chinchani
- Toddy
- Brandon Klein

### Actionable Agenda Items:

None.

### Presentation/Discussion Agenda Items:

None.

### Notes:
- Blog published - https://opencontainers.org/posts/blog/2024-03-13-image-and-distribution-1-1/
- Brief discussion on tag listing v2
  - Toddy: can the client pushing content be exposed in the tag listing API (was this pushed by the Docker engine)
  - Tianon: <https://github.com/yifeikong/curl_cffi>
- _add your notes_

## April 11, 2024

**Recording**: https://youtu.be/DFHOz8pjOdY

### Attendees:
- Tianon
- Michael Brown
- Brandon Mitchell
- Ramkumar Chinchani
- Brandon Klein
- Sajay Antony
- Brian Goff
- Samuel Karp

### Actionable Agenda Items:
- [Container Plumbing Days in Seattle](https://events.linuxfoundation.org/container-plumbing-days/) is next Monday

### Presentation/Discussion Agenda Items:

None.

### Notes:
- Discussed process to add an updated tag listing API

## April 4, 2024

**Recording**: https://youtu.be/oMd-Pc7qQz0

### Attendees:
- Ramkumar Chinchani
- Tianon
- Brandon Mitchell
- Joseph Ferguson
- Josh Dolitsky
- Syed Ahmed
- Brandon Klein
- Toddy
- Jon Johnson
- Brian Goff

### Actionable Agenda Items:

None.

### Presentation/Discussion Agenda Items:
- Blog post for 1.1 releases (Brandon): <https://github.com/opencontainers/opencontainers.org/pull/152>
- image-spec:
  - Clarify syntax for `artifactType` and `mediaType` fields in manifests (Brandon):
    - <https://github.com/sigstore/cosign/pull/3622>
    - <https://github.com/opencontainers/image-spec/pull/1182>
  - Go versions needs reviews: <https://github.com/opencontainers/image-spec/pull/1170>
  - jonboulle emeritus vote: <https://github.com/opencontainers/image-spec/pull/1179>
- distribution-spec:
  - port separator, okay to close?: <https://github.com/opencontainers/distribution-spec/pull/498>
  - TOC ordering, review needed: <https://github.com/opencontainers/distribution-spec/pull/471>
  - release process, review needed: <https://github.com/opencontainers/distribution-spec/pull/460>
  - tag pagination, does the recommended limit need to be dropped, and should a suggestion for clients to use the link header be added? (Brandon): <https://github.com/opencontainers/distribution-spec/pull/470>

### Notes:
- Fixing existing tag API
  - More users would be broken by the 413 than the Link header
  - Consensus is to prefer to break curl scripts over Link header aware clients
- Tag listing v2 wishlist
  - descriptors in responses
  - untagged manifests
  - some kind of search (annotation and artifactType)
  - link header pagination
  - graphql search?
  - query tags by digest
  - historical tags
  - all manifests that point to a digest (index to manifest, manifest to layer)
