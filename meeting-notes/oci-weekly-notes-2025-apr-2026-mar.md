# OCI Weekly Dev Meeting Notes Archive - April 2025 to March 2026

## January 1, 2026

Canceled for New Years Day.

## December 25, 2025

Canceled for Christmas holiday.

## December 18, 2025

**Recording**: https://youtu.be/2ptoXp0xrrA

### Attendees:

- Tianon
- Brandon Mitchell
- Jeff Carter
- Ramkumar Chinchani
- Brandon Klein
- Jory Burson
- Mike Brown
- Samuel Karp

### Actionable Agenda Items:

None.

### Presentation/Discussion Agenda Items:

- distribution-spec is missing the cancel upload API
  - <https://github.com/opencontainers/distribution-spec/issues/352>
  - Added as an optional conformance test
  - Return it to the spec as a SHOULD, but don't enable the test by default until a 1.2 release
- distribution-spec needs clarification on out of order blob chunks with the final PUT request
  - <https://github.com/opencontainers/distribution-spec/issues/590>
  - Clarify the 416 status also applies to a chunk sent by a PUT
- No meeting next two weeks (Christmas and New Years Day)

### Notes:

Notes from the zoom chat:

00:11:18	Jeff Carter:	https://github.com/opencontainers/distribution-spec/pull/178
00:11:34	Tianon:	the purge commit is "+255 -4,433" on `spec.md`
00:11:43	Tianon:	Replying to "the purge commit is ..." that seems less than ideal
00:12:29	Tianon:	https://github.com/opencontainers/distribution-spec/commit/c90b0f145ac6bc09d2636ee214486ac333edc284#diff-bc6661da34ecae62fbe724bb93fd69b91a7f81143f2683a81163231de7e3b545L580-L590
00:12:36	Tianon:	Replying to "https://github.com/o..."

> ##### Canceling an Upload
> 
> An upload can be cancelled by issuing a DELETE request to the upload endpoint.
> The format will be as follows:
> 
> ```HTTP
> DELETE /v2/<name>/blobs/uploads/<session_id>
> ```

> After this request is issued, the upload `session_id` will no longer be valid and the registry server will dump all intermediate data.
> While uploads will time out if not completed, clients SHOULD issue this request if they encounter a fatal error but still have the ability to issue an http request.

00:20:03	Brandon Mitchell:	https://github.com/opencontainers/distribution-spec/issues/548
00:30:57	Jory Burson:	I have to drop for another call - have a wonderful holiday break and see you all in the new year!
00:34:38	Tianon:	The final chunk MAY be uploaded using a PATCH request or it MAY be uploaded in the closing PUT request. Regardless of how the final chunk is uploaded, the session MUST be closed with a PUT request.
nice, the less pathological behavior is actually supported by the spec
00:35:09	Tianon:	If a chunk is uploaded out of order, the registry MUST respond with a 416 Requested Range Not Satisfiable code. A GET request may be used to retrieve the current valid offset and upload location.
oof, why doesn't the 416 just return the range??
00:37:43	Ramkumar Chinchani:	memory constrained embedded devices pushing data/blobs - round trips less relevant
00:39:26	Tianon:	GET /v2/ 
  ... hand-wave auth? ...
  GET /v2/foo/manifests/tag
  ... hand-wave auth? ...
  GET /v2/foo/manifests/sha256:xxx
  GET /v2/foo/blobs/sha256:xxx over and over and over
00:42:03	Mike Brown:	https://github.com/containerd/containerd/blob/636a24eef6c144a3aea85a3c712258e99ea809ad/remotes/docker/pusher.go#L142
00:42:21	Tianon:	Replying to "https://github.com/c..." chunky 😂
00:42:39	Tianon:	Replying to "https://github.com/c..." (the best peanut butter 🥜)
00:44:40	Tianon:	Replying to "The final chunk MAY ..." we should change this first MAY to a SHOULD and the second MAY to MAY (but SHOULD NOT)

## December 11, 2025

**Recording**: https://youtu.be/zUo-4-yWFho

### Attendees:

- Tianon
- Brandon Mitchell
- Brian Goff
- Derek McGowan
- Jory Burson
- Mike Brown
- Jeff Carter
- James Kolb
- Syed Ahmed
- Ramkumar Chinchani

### Actionable Agenda Items:

None.

### Presentation/Discussion Agenda Items:

- TOB nominations open
- Conformance test for non-distributable layers
  - <https://github.com/opencontainers/distribution-spec/pull/588>
- Streaming blob push
  - Existing conformance test is wrong
- Blob upload directly to S3
  - Would the registry still verify digests after pushing?
  - Clients could potentially upload blob chunks concurrently and/or out of order
  - Assumes storage in S3 is the raw blob, without any other data wrapping
  - Potential for clients to send data to S3 after the PUT, registry needs to cutoff new content in S3 before verifying the digest

### Notes:

Notes from the zoom chat:

00:09:26	Tianon:	https://github.com/opencontainers/tob/issues/116
00:27:28	Jory Burson:	I have to drop at the half hour for a rescheduled 1:1 but I will see you all next week if we don’t chat before then 👋
00:42:57	Ramkumar Chinchani:	push can happen out-of-band/directly and pulls could point via a Location?
01:01:02	Derek McGowan:	Thanks Jeff

## December 4, 2025

**Recording**: https://youtu.be/V4f6VT61HyU

### Attendees:

- Tianon
- Brandon Mitchell
- Derek McGowan
- Ramkumar Chinchani
- Samuel Karp
- Jeff Carter
- Sajay Santony
- Mike Brown
- Brandon Klein

### Actionable Agenda Items:

None.

### Presentation/Discussion Agenda Items:

- TOB nominations should be opening up soon for OCI members
  - Brandon sent a reminder to operations
- distribution-spec conformance v2 progress:
  - <https://github.com/sudo-bmitch/distribution-spec/tree/pr-conformance-v2/conformance2>
  - Added blob mount, verify tag listing after pushes, head requests
  - Allow data tests to be disabled, added foreign layers
  - Adding content with unique fields and custom annotations
  - HTML report cleanup
  - Converting v1 environment variables
  - Support read-only registries
  - Stub test included for existing users
  - Need to add tests of invalid inputs
  - The conformance website will also need to be updated to handle the different tests
  - Draft PR raised for visibility: <https://github.com/opencontainers/distribution-spec/pull/588>

### Notes:

Notes from the zoom chat:

00:05:58	Brandon Mitchell:	https://github.com/opencontainers/tob/issues/118
00:07:23	Brandon Mitchell:	https://github.com/sudo-bmitch/distribution-spec/tree/pr-conformance-v2/conformance2
00:07:52	Tianon:	Replying to "https://github.com/s..." "we have oci conformance at home"
00:10:17	Ramkumar Chinchani:	Replying to "https://github.com/s..." hopefully, most if not all, have default values
00:13:15	Sajay Antony:	oh my goodness.. 👏 - @Brandon.
00:14:07	Ramkumar Chinchani:	Replying to "https://github.com/s..." getting serious :) similar to: https://github.com/jepsen-io/jepsen
00:18:19	Ramkumar Chinchani:	Replying to "https://github.com/s..." are there any registry survivors after this?
00:30:07	Tianon:	`%.0w` is a really cute way to wrap an error silently 😂
00:30:46	Derek McGowan:	Looks good! I gotta drop
00:32:38	Sajay Antony:	Its 10:30 PST and I need to drop as well. Thank you for all the stuff you are doing  @Brandon.
00:33:41	Tianon:	cursed CI idea: test as many (popular?) registries as possible and consider the tests good if at least two of them pass any given test 😂

## November 27, 2025

**Canceled**: US Thanksgiving Holiday

## November 20, 2025

**Recording**: https://youtu.be/Eaq1zpujsK4

### Attendees:

- Brandon Mitchell
- Sam Karp
- Tianon
- Brian Goff
- Ramkumar Chinchani
- Sajay Antony

### Actionable Agenda Items:

- Review needed:
  - Dependabot in the conformance repo: <https://github.com/opencontainers/oci-conformance/pull/128>

### Presentation/Discussion Agenda Items:

- How to improve OCI Working Groups?
  - Friction between a trailing spec and trailing implementations.
  - Lack of resources to do new development in OCI, most devs on implementations are focused on only supporting the existing spec with only the required changes.
  - Two working groups have stalled (auth and image compatibility).
  - Another for a reference spec is queued in a draft state.
  - FreeBSD seems to have finished (or at least merged into runtime-spec), but their work was fairly isolated from the rest of OCI.
  - Referrers had a very active community, and a lot of pull from projects to merge it, but concerns have since been raised.
  - Request for any suggested changes to the process to be made as PRs to <https://github.com/opencontainers/tob>

### Notes:

00:18:46	Ramkumar Chinchani:	“There are only two kinds of languages: the ones people complain about and the ones nobody uses.”
00:20:08	Ramkumar Chinchani:	OCI is both a trailer and a leader

## November 13, 2025

**Recording**: https://youtu.be/9LVcFVCgFOc

### Attendees:

- Tianon
- Brandon Mitchell
- Brian Goff
- Sam Karp
- Ramkumar Chinchani

### Actionable Agenda Items:

- Registry proxying, okay to merge? <https://github.com/opencontainers/distribution-spec/pull/66> (merged)

### Presentation/Discussion Agenda Items:

- KubeCon recap:
  - digest algorithms (post-quantum algorithm requirements)
  - alternatives to tar (distributing large AI models, lazy loading, block vs filesystem level deltas)
- Is there a threshold where OCI should remove a project from the list of implementations?
  - Intentional incompatability with OCI implementations?
  - What if the project is designed in a way that causes data loss for users of OCI conformant tools?
  - How do we balance users looking to OCI for a list of compatible implementations vs implementations innovating with their own alternatives?
- LLM Policies, should other projects follow runc: <https://github.com/opencontainers/runc/issues/4990>
  - LF has a policy we could leverage.
- Referrers in the OCI Layout: <https://github.com/opencontainers/image-spec/pull/1171>

### Notes:

Notes from the zoom chat:

00:33:47	Brian Goff (@cpuguy83):	"The problem with LLM issues and PRs is that LLMs allow people to produce reasonable-looking spam" That I think is the primary issue.

## November 11, 2025 - KubeCon US

**Recording**: https://youtu.be/gyghHoor350

KubeCon NA meeting Nov 11, 3:30 - 5:30pm EST, GWCC Room B202

### Attendees:

- Phil Estes
- Akihiro Suda
- Michael Brown
- Neil Smith
- Austin Vazquez
- Ayato Tokubi
- Colin Walters
- Derek McGowan
- Matthew Heon
- Peter Hunt
- Sohan Kunkerkar
- Wei Fu
- Brandon Mitchell (remote)
- Mike Brown (remote)
- Giuseppe Scrivano (remote)
- Samuel Karp (remote)
- Brent Baude (remote)
- Brian Goff (remote)

### Actionable Agenda Items:

None.

### Presentation/Discussion Agenda Items:

- containerd has implemented a storage backend, podman is interested in lessons learned.
- Changing hash algorithms is a big changes for registries.
- Changing to a non-tar blob serialization is a challenge for image-spec and runtime support.
- composefs: <https://hackmd.io/s0-bCvJRThaeitPHHBKGpw>
- Multiple challenges, some for lazy loading of content for network efficiency, efficient validation of content on disk, and others need security from post-quantum crypto algorithm support.
- Changing the digest algorithm is blocked behind rework of conformance tests: <https://github.com/sudo-bmitch/distribution-spec/tree/pr-conformance-v2/conformance2>
- sha512 support in the distribution-spec is being tracked at: <https://github.com/opencontainers/distribution-spec/pull/543>
- dm-verity is desired for on disk verification with efficient hash computation.
- erofs snapshotter support with dm-verity in containerd: <https://github.com/containerd/containerd/pull/12502>.
- Compressed vs uncompressed digests shows up in image-spec, could be moved to transport level compression in distribution-spec <https://github.com/opencontainers/distribution-spec/issues/235>.
- Different tar implementations could result in a tar that extracts differently based on the client.
- AI models may not have an efficient solution, depends on whether they can package smaller deltas of their models.
- Distribution-spec allows multiple entries for the same platform in an index so later entries could be used for a non-tar layer format. This requires scanners to scan everything to detect if two different (malicious) images are being shipped vs only a different filesystem serialization format.
- Recent linux kernels allow file backed erofs mounts (vs creating a block device).
- Desire to have lazy loading with erofs.
- Reproducibility has also been worked on by multiple groups. Timestamps have been solved in some places with `SOURCE_DATE_EPOCH`. Pinning package manager versions is also a challenge.
- Efficient storage for AI models may require internal file or block level diffs vs filesystem diffs (where entire file is COW).

## November 6, 2025

**Recording**: https://youtu.be/xc86bMUURVM

### Attendees:

- Brandon Mitchell
- Tianon
- Sam Karp
- Brian Goff
- Derek McGowan
- Ramkumar Chinchani
- James Kolb
- Mike Brown
- Jory Burson

### Actionable Agenda Items:

- Review needed:
  - Range header in chunked response: <https://github.com/opencontainers/distribution-spec/pull/581> (now merged)
  - Proxy namespaces: <https://github.com/opencontainers/distribution-spec/pull/66> (changes requested)
  - Security annotation: <https://github.com/opencontainers/image-spec/pull/1284>

### Presentation/Discussion Agenda Items:

- KubeCon NA meeting Nov 11, 3:30 - 5:30pm EST, GWCC Room B202
  - Multiple people want to join by Zoom
- Runtime Spec v1.3.0 release:
  - <https://github.com/opencontainers/runtime-spec/pull/1302>
  - <https://opencontainers.org/posts/blog/2025-11-04-oci-runtime-spec-v1-3/>
- Security release for runc:
  - <https://github.com/opencontainers/runc/releases/tag/v1.3.3>
  - <https://github.com/opencontainers/runc/releases/tag/v1.4.0-rc.3>
- specs.opencontainers.org needs updates
  - <https://github.com/opencontainers/specs.opencontainers.org/issues/13>
  - <https://github.com/opencontainers/specs.opencontainers.org/issues/14>
- opencontainers.org needs release notices:
  - runtime-spec v1.2.1 <https://github.com/opencontainers/opencontainers.org/issues/162>
  - runtime-spec v1.3.0 is also needed
- distribution-spec conformance v2 progress:
  - referrers API added
  - index with a subject added
  - reworked how tags are pushed/tracked
  - next up: converting old env vars, adding a test wrapper, use config flags to disable some data tests, and the blob mount API
- Referrers API within the OCI Layout: <https://github.com/opencontainers/image-spec/pull/1171>

### Notes:

00:04:35	Brian Goff (@cpuguy83):	Nope
00:04:41	Tianon:	also nack
00:06:38	Ramkumar Chinchani:	FreeBSD, welcome to OCI?
00:08:00	Tianon:	https://github.com/containers/crun/releases no release yet 😅
00:08:54	Tianon:	relevant to cyphar's library, https://github.com/opencontainers/runc/pull/4959#issuecomment-3486161982 might be interesting to folks (I haven't had a chance to dig into it yet)
00:09:17	Derek McGowan:	https://github.com/containerd/containerd/issues/12484
00:09:58	Tianon:	Replying to "https://github.com/c..." https://github.com/opencontainers/runc/issues/4968 for the tracking issue in runc
00:10:13	Tianon:	Replying to "https://github.com/c..." see also https://github.com/opencontainers/runc/issues/4971 for a tmpfs-related bug
00:11:23	Tianon:	"I'm just clicking links you guys are throwing in the chat here" -Brandon
https://www.youtube.com/watch?v=dQw4w9WgXcQ
00:14:05	Brian Goff (@cpuguy83):	Ubuntu has been agressive about their apparmor profiles of late.
00:14:33	Tianon:	Replying to "Ubuntu has been agre..." yeah, upstream has been making some very aggressive changes to default profiles 😞
00:20:01	Brian Goff (@cpuguy83):	Its hard to do GHA in this.
00:20:20	Brian Goff (@cpuguy83):	CI in a public repo assumes certain things.
00:34:10	Jory Burson:	I like that we still call it “teleconferencing"
00:37:39	Brian Goff (@cpuguy83):	"just nits" -- Have you ever had to pick nits out of your kid's hair?
00:38:13	Jory Burson:	Replying to ""just nits" -- Have ..." This triggers me LOL
00:38:14	Brian Goff (@cpuguy83):	Replying to ""just nits" -- Have ..." Real joke is, now your head is probably itching.
00:39:48	Brian Goff (@cpuguy83):	Take dog out before her 11:00 barking.
00:40:08	Ramkumar Chinchani:	A big thanks to Brandon for driving the conformance test refactor
00:40:32	Tianon:	a note for KubeConners: https://bsky.app/profile/lookitup.baby/post/3m4wmw4zeh22r
00:40:40	Tianon:	Replying to "a note for KubeConne..." Yeah so they’re cutting flights at the 40 busiest airports starting with 4% on Friday and ramping up to 10% through the weekend, and that includes ATL. If you’re attending #KubeCon and you aren’t threat modeling around this and making contingency plans already, strongly recommend starting now

## October 30, 2025

**Recording**: https://youtu.be/gL-QGi2n4wc

### Attendees:

- Tianon
- Brandon Mitchell
- Derek McGowan
- Sajay Antony
- Brian Goff
- Jory Burson

### Actionable Agenda Items:

- Review needed:
  - Range header in chunked response: <https://github.com/opencontainers/distribution-spec/pull/581>
  - Proxy namespaces: <https://github.com/opencontainers/distribution-spec/pull/66>
  - Security annotation: <https://github.com/opencontainers/image-spec/pull/1284>

### Presentation/Discussion Agenda Items:

- KubeCon NA meeting Nov 11, 3:30-5:30pm ET, GWCC Room B202
  - containerd maintainers may show to chat storage with crio
  - No AV available, would like to get the session on Youtube, even if it's just someone dialing into Zoom from their laptop
- FreeBSD Support in Runtime Spec:
  - <https://github.com/opencontainers/runtime-spec/pull/1286>
  - Anything needed in image spec for the platform field?
  - May need to specify how `os.version` is used
- Runtime Spec is voting on v1.3.0 release: <https://github.com/opencontainers/runtime-spec/pull/1302>
- Distribution spec discussion on static http hosting: <https://github.com/opencontainers/distribution-spec/discussions/587>

### Notes:

Notes from the zoom chat:

00:12:40	Sajay Antony:	What date/time is the session btw?
00:15:10	Tianon:	Replying to "What date/time is th..." "we have an OCI calendar?" actual message I sent Jory within the last 7 days
00:15:39	Tianon:	Replying to "What date/time is th..." wow apparently that was two weeks ago, my bad - time is fake
00:15:47	Brandon Mitchell:	Replying to "What date/time is th..." KubeCon NA meeting Nov 11, 3:30-5:30pm, GWCC Room B202
00:15:53	Brian Goff (@cpuguy83):	Can barely hear you Sajay
00:16:42	Tianon:	Replying to "What date/time is th..." and it looks like KubeCon NA is in Georgia so that's 3:30-5:30 eastern time
00:16:57	Jory Burson:	On the image spec release
00:20:48	Sajay Antony:	Replying to "What date/time is th..." Ah thanks.
00:21:51	Jory Burson:	How old are you in container years
00:22:01	Tianon:	Replying to "How old are you in c..." 🧓
00:22:03	Tianon:	Replying to "How old are you in c..." ancient
00:27:37	Brian Goff (@cpuguy83):	Replying to "How old are you in c..." Have grey hairs coming out of our ears.
00:29:47	Tianon:	Replying to "How old are you in c..." today I had the somewhat unique experience of an engineering co-worker not already knowing who I am (but still being familiar with my work), which was kind of amazing ("wait, he maintains that?" kind of energy)
00:29:49	Sajay Antony:	Folks its 30 mins past, unfortunately need to run.
00:35:18	Brian Goff (@cpuguy83):	NTD
00:44:24	Tianon:	I set up something at https://tmp.tianon.xyz/v2/ with some registry content -- crane doesn't care at all:

```
$ crane manifest tmp.tianon.xyz/test:latest
{
  "schemaVersion": 2,
  "mediaType": "application/vnd.oci.image.index.v1+json",
  "manifests": [
    {
      "mediaType": "application/vnd.oci.image.manifest.v1+json",
      "digest": "sha256:9ef42f1d602fb423fad935aac1caa0cfdbce1ad7edce64d080a4eb7b13f7cd9d",
      "size": 1165,
      "platform": {
        "os": "linux",
        "architecture": "amd64"
      },
      "annotations": {
        "com.docker.official-images.bashbrew.arch": "amd64",
        "org.opencontainers.image.base.name": "scratch",
        "org.opencontainers.image.created": "2025-04-25T23:09:46Z",
        "org.opencontainers.image.revision": "fd07cf2c5b1aa4a00d10701124615cee90956ce0",
        "org.opencontainers.image.source": "https://github.com/tianon/dockerfiles.git",
        "org.opencontainers.image.url": "https://hub.docker.com/r/tianon/true",
        "org.opencontainers.image.version":
```
00:44:45	Tianon:	Replying to "I set up something a..." but Docker sure does:

```
$ docker pull tmp.tianon.xyz/test
Using default tag: latest
Error response from daemon: missing signature key
```

00:44:54	Tianon:	Replying to "I set up something a..." it assumes it must be schema1, which is even worse
00:46:44	Tianon:	Replying to "I set up something a..."

```
$ sudo ctr content fetch tmp.tianon.xyz/test:latest
WARN[0000] reference for unknown type: application/octet-stream  digest="sha256:54601ace1bfa6c5f1fade4c284f730491c8b3072dbe40ec56e7df7d65dde589b" mediatype=application/octet-stream size=901
ctr: failed to copy: httpReadSeeker: failed open: could not fetch content descriptor sha256:54601ace1bfa6c5f1fade4c284f730491c8b3072dbe40ec56e7df7d65dde589b (application/octet-stream) from remote: not found
```
00:49:11	Jory Burson:	brb
00:52:09	Jory Burson:	Reacted to "today I had the some..." with ❤️
00:59:33	Jory Burson:	NTD for another call! Will ping about the video recording

## October 23, 2025

**Recording**: https://youtu.be/P7zgWWyZXVQ

### Attendees:

- Tianon
- Brandon Mitchell
- Jeff Carter
- Sajay Antony

### Actionable Agenda Items:

- Review needed:
  - Range header in chunked response: <https://github.com/opencontainers/distribution-spec/pull/581>
  - Proxy namespaces: <https://github.com/opencontainers/distribution-spec/pull/66>
  - Security annotation: <https://github.com/opencontainers/image-spec/pull/1284>

### Presentation/Discussion Agenda Items:

- Should govulncheck be added to GHA: <https://github.com/opencontainers/image-spec/pull/1291>
- Progress on distribution-spec conformance rewrite
  - <https://github.com/sudo-bmitch/distribution-spec/tree/pr-conformance-v2/conformance2>
- Status of tag listing v2, waiting on implementations: <https://github.com/opencontainers/distribution-spec/pull/579>

### Notes:

Notes from the zoom chat:

00:13:52	Tianon:	go run -buildvcs=true  is supported, right? 👀 (I hate it, but it's a thing)

## October 16, 2025

**Recording**: https://youtu.be/4BXKYxJHnp0

### Attendees:

- Brandon Mitchell
- Tianon
- Sajay Antony
- Brian Goff
- Ramkumar Chinchani
- Jory Burson

### Actionable Agenda Items:

- Review needed:
  - Range header in chunked response: <https://github.com/opencontainers/distribution-spec/pull/581>
  - Proxy namespaces: <https://github.com/opencontainers/distribution-spec/pull/66>
  - Security annotation: <https://github.com/opencontainers/image-spec/pull/1284>
  - image-spec implementation list: <https://github.com/opencontainers/image-spec/pull/1290> (merged)

### Presentation/Discussion Agenda Items:

- How best to support the referrers/subject entries in an OCI Layout: <https://github.com/opencontainers/image-spec/pull/1171>
- KubeCon is coming up
- Trademark board is planning a meeting, needs to plan their budget
- Send Jory thoughts on the next Container Plumbing Days

### Notes:

Notes from the zoom chat:

00:13:22	Tianon:	I've been using BuildKit's  vnd.docker.reference.digest  for this in my own code 😅
00:13:52	Tianon:	Replying to "I've been using Buil..." because it already matches the intent I have/need (which other object does this object's "subject" point to)
00:14:25	Tianon:	Replying to "I've been using Buil..." https://github.com/moby/buildkit/blob/bc3666b3b8d8faacfba73c2e29f34e32f67d8f14/docs/attestations/attestation-storage.md#attestation-manifest-descriptor
00:15:34	Tianon:	Replying to "I've been using Buil..." (and for my own needs, even if there was an official thing, I'd still be setting this thing because consistent is more useful than "standard" or "official", which is the genesis of the OCI in the first place 😅)
00:17:32	Tianon:	https://github.com/opencontainers/distribution-spec/issues/515
00:20:31	Brian Goff (@cpuguy83):	SIgn everything.
00:21:33	Brian Goff (@cpuguy83):	It means I did the things my enterprise wants me to do.
00:21:47	Tianon:	Replying to "It means I did the t..." don't say the quiet part out loud! 😂
00:29:32	Tianon:	This index provides an established path (/index.json) to have an entry point for an image-layout and to discover auxiliary descriptors.
00:29:55	Tianon:	Replying to "This index provides ..." not explicit, but reasonably well implied IMO
00:30:23	Tianon:	Replying to "This index provides ..." "you only need to list things required for discovering everything else" is how I'd read between the lines on that
00:32:58	Brian Goff (@cpuguy83):	Zoom, at least its not Teams.
00:38:48	Brian Goff (@cpuguy83):	That was LTT level segway.
00:40:40	Brian Goff (@cpuguy83):	"One of us"
00:43:23	Tianon:	"I don't know what it is and we're so far in that I'm too afraid to ask"
00:44:12	Tianon:	Replying to ""I don't know what i..." https://en.meming.world/wiki/Afraid_To_Ask_Andy

## October 9, 2025

### Attendees:

- Brandon Mitchell
- Tianon
- Brian Goff
- Syed Ahmed

### Actionable Agenda Items:

- Review needed:
  - Range header in chunked response: <https://github.com/opencontainers/distribution-spec/pull/581>
  - Proxy namespaces: <https://github.com/opencontainers/distribution-spec/pull/66>
  - Security annotation: <https://github.com/opencontainers/image-spec/pull/1284>
- Runc release 1.3.2: <https://github.com/opencontainers/runc/releases/tag/v1.3.2>

### Presentation/Discussion Agenda Items:

- No agenda items, wrapped up the meeting early.

### Notes:

none

## October 2, 2025

### Attendees:

- Brandon Mitchell
- Joseph Ferguson
- Jeff Carter
- Brian Goff
- Ramkumar Chinchani

### Actionable Agenda Items:

- Review needed:
  - Range header in chunked response: <https://github.com/opencontainers/distribution-spec/pull/581>
  - Proxy namespaces: <https://github.com/opencontainers/distribution-spec/pull/66>
  - Security annotation: <https://github.com/opencontainers/image-spec/pull/1284>

### Presentation/Discussion Agenda Items:

- No agenda, wrapped up early

### Notes:

none

## September 25, 2025

**Recording**: https://youtu.be/IpQrVMH4iNs

### Attendees:

- Tianon
- Brandon Mitchell
- Ramkumar Chinchani

### Actionable Agenda Items:

- Review needed:
  - Range header in chunked response: <https://github.com/opencontainers/distribution-spec/pull/581>
  - Proxy namespaces: <https://github.com/opencontainers/distribution-spec/pull/66>
  - Security annotation: <https://github.com/opencontainers/image-spec/pull/1284>

### Presentation/Discussion Agenda Items:

- Progress with conformance redesign: <https://github.com/sudo-bmitch/distribution-spec/tree/pr-conformance-v2/conformance2>

### Notes:

Notes from the zoom chat:

00:08:44	Ramkumar Chinchani:	GH copilot could expedite?

## September 18, 2025

**Recording**: https://youtu.be/wkZj4Uq7GC0

### Attendees:

- Brandon Mitchell
- Tianon
- Brian Goff
- Derek McGowan
- Jeff Carter
- Sajay Antony
- James Kolb
- Ramkumar Chinchani
- Jory Burson

### Actionable Agenda Items:

- Review needed:
  - Range header in chunked response: <https://github.com/opencontainers/distribution-spec/pull/581>
  - Proxy namespaces: <https://github.com/opencontainers/distribution-spec/pull/66>
  - Security annotation: <https://github.com/opencontainers/image-spec/pull/1284>
- Okay to close?
  - Search for blob: <https://github.com/opencontainers/distribution-spec/issues/585>

### Presentation/Discussion Agenda Items:

- Syntax on range headers: <https://github.com/opencontainers/distribution-spec/issues/586>
- Layers missing parent directories: <https://github.com/opencontainers/image-spec/pull/970>
  - Any desire to take this PR over?
- Self validating blobs? <https://github.com/opencontainers/image-spec/issues/1275>
- Jory working on a Trademark Board meeting

### Notes:

Notes from the zoom chat:

00:08:01	Sajay Antony:	That's kind of ambiguous
00:11:15	Sajay Antony:	Sorry my voice is totally gone.
00:11:43	Ramkumar Chinchani:	this is like "robots.txt"
00:17:20	Jory Burson:	Hiiiiii sorry I yam late
00:28:01	Ramkumar Chinchani:	This is a known breakage
00:37:40	Sajay Antony:	Thanks all, late for another meeting. Need to drop. See you next week.

## September 11, 2025

**Recording**: https://youtu.be/697AXluvdBk

### Attendees:

- Brandon Mitchell
- Tianon
- Mike Brown
- Sajay Antony
- Michael Brown

### Actionable Agenda Items:

- Review needed:
  - Range header in chunked response: <https://github.com/opencontainers/distribution-spec/pull/581>
  - Proxy namespaces: <https://github.com/opencontainers/distribution-spec/pull/66>

### Presentation/Discussion Agenda Items:

- Security annotation: <https://github.com/opencontainers/image-spec/pull/1284>
- runtime-spec is planning a 1.3 release: <https://github.com/opencontainers/runtime-spec/issues/1295>

### Notes:

Notes from the zoom chat:

00:11:23	Sajay Antony:	Do we need more maintainers in distribution?
00:18:01	Brandon Mitchell:	<operations@opencontainers.org>
00:18:45	Sajay Antony:	Artifact manifest 😂

## September 4, 2025

**Recording**: https://youtu.be/r4hhQCHHpqY

### Attendees:

- Brandon Mitchell
- Tianon
- Brian Goff
- Ramkumar Chinchani
- Jory Burson

### Actionable Agenda Items:

- Review needed:
  - Range header in chunked response: <https://github.com/opencontainers/distribution-spec/pull/581>
  - Proxy namespaces: <https://github.com/opencontainers/distribution-spec/pull/66>

### Presentation/Discussion Agenda Items:

- Security annotation: <https://github.com/opencontainers/image-spec/issues/1283>
- Container Plumbing Days retro from Jory
  - About 30 attended
- Trademark Board is planning on a meeting

### Notes:

Notes from the zoom chat:

00:08:54	Tianon:	"The URLs for accessing your security.txt file. It is important to include this if you are digitally signing the security.txt file, so that the location of the security.txt file can be digitally signed too. See the full description of Canonical"
00:09:19	Tianon:	Replying to ""The URLs for access..." added justification for pointing to a URL instead of copying the data
00:10:40	Jory Burson:	Hi hi
00:14:08	Ramkumar Chinchani:	why not use referrer artifact for this?
00:14:28	Ramkumar Chinchani:	seems like an attempt to standardize something
00:14:47	Tianon:	Replying to "why not use referrer..." referrers are kind of heavy for something that's in most cases going to be just a URL
00:14:56	Tianon:	Replying to "why not use referrer..." but there's nothing to stop anyone from using referrers
00:15:10	Tianon:	Replying to "seems like an attemp..." this is the one - freeze the annotations spec 😈

## August 28, 2025

**Recording**: https://youtu.be/GssZ0FpeYJk

### Attendees:

- Kevin Li
- Efim Verzakov
- Brandon Mitchell
- Peter Treese
- Tianon
- Ram Chinchani
- Michael Brown

### Actionable Agenda Items:

- Review needed:
  - Range header in chunked response: <https://github.com/opencontainers/distribution-spec/pull/581>
  - Proxy namespaces: <https://github.com/opencontainers/distribution-spec/pull/66>

### Presentation/Discussion Agenda Items:

- vTPM: <https://github.com/opencontainers/runtime-spec/pull/1293>
- Distribution spec conformance progress. (Brandon)
- Pass through authentication with proxy namespaces. (Brandon)

### Notes:

Notes from the zoom chat:

00:11:23	Kevin Li:	https://github.com/opencontainers/runtime-spec/pull/1293
00:17:34	Tianon:	in the VM example, libvirt creates and manages the swtpm process, right? https://github.com/libvirt/libvirt/blob/75e6158a95167f7655879f232af44a3737d30eb0/src/util/virtpm.c
00:18:08	Tianon:	Replying to "in the VM example, l..." in that example, the runc comparison is qemu, and qemu does not create TPM devices (or run swtpm)
00:18:50	Tianon:	Replying to "https://github.com/o..." https://github.com/opencontainers/runc/pull/4855
00:27:32	Ramkumar Chinchani:	ntd early today
00:34:31	Tianon:	https://bmitch.net/blog/2025-08-22-ghrc-appears-malicious/
00:34:59	Tianon:	Replying to "https://bmitch.net/b..." (now he gets to copy his personal blog link into the meeting notes, but not feel self-serving when he does so 😂)

## August 21, 2025

**Recording**: https://youtu.be/DaCyLP2hWdA

### Attendees:

- Brandon Mitchell
- Tianon
- Jory Burson
- Syed Ahmed
- Jeff Carter
- Sajay Antony
- Mike Brown

### Actionable Agenda Items:

None.

### Presentation/Discussion Agenda Items:

- Clarifying predefined annotations: <https://github.com/opencontainers/image-spec/issues/833>

### Notes:

Notes from the zoom chat:

00:12:23	Syed Ahmed:	+1 for deprecating labels
00:14:19	Jory Burson:	Oh no!
00:21:13	Sajay Antony:	I’m out for the next 2 weeks.

## August 14, 2025

**Recording**: https://youtu.be/5v6eJrQWXdw

### Attendees:

- Brandon Mitchell
- Brian Goff
- Ramkumar Chanchani
- Tianon
- Michael Brown
- Jeff Carter
- Syed Ahmed

### Actionable Agenda Items:

None.

### Presentation/Discussion Agenda Items:

- Shortened meeting reviewing some of the in-progress PRs.
  - Range header: <https://github.com/opencontainers/distribution-spec/pull/581>
  - Tag listing: <https://github.com/opencontainers/distribution-spec/pull/579>
  - Proxy namespace: <https://github.com/opencontainers/distribution-spec/pull/66>

### Notes:

Notes from the zoom chat:

00:13:37	Tianon:	ringing the bell of shame for Michael 🔔
00:15:57	Brandon Mitchell:	We only say "SHOULD NOT" error, not "MUST NOT", so it's still spec compliant.

## August 7, 2025

**Recording**: https://youtu.be/2-ylZqX9phI

### Attendees:

- Tianon
- Jeff Carter
- Mike Brown
- Isaev Isa
- Brandon Mitchell
- Brian Goff
- Jory Burson
- Efim Verzakov
- Ramkumar Chinchani
- Sajay Antony

### Actionable Agenda Items:

- Review needed:
  - Range header in chunked response: <https://github.com/opencontainers/distribution-spec/pull/581>
    - Mike asked for an example, and the GET response also needs to be updated.
  - Conformance tag list order: <https://github.com/opencontainers/distribution-spec/pull/583>
  - Proxy namespaces: <https://github.com/opencontainers/distribution-spec/pull/66>

### Presentation/Discussion Agenda Items:

- Isa asked about adding vtpm support in runc.
  - Brandon suggested opening an issue in the runc and runtime-spec repos.

### Notes:

Notes from the zoom chat:

00:26:03	Tianon:	https://developer.mozilla.org/en-US/docs/Web/HTTP/Reference/Headers/Range#requesting_multiple_ranges is really interesting (only barely related)
00:36:58	Sajay Antony:	Folks NTD. Thank you.
00:45:48	Jory Burson:	Bye q!

## July 31, 2025

**Recording**: https://youtu.be/HoNMtOJ1yV0

### Attendees:

- Brandon Mitchell
- Tianon
- Sajay Antony
- Syed Ahmed
- Derek McGowan
- Ramkumar Chinchani
- Jory Burson

### Actionable Agenda Items:

- Review needed:
  - Conformance tag list order: <https://github.com/opencontainers/distribution-spec/pull/583>
  - Proxy namespaces: <https://github.com/opencontainers/distribution-spec/pull/66>

### Presentation/Discussion Agenda Items:

- Tag listing: <https://github.com/opencontainers/distribution-spec/pull/579>

### Notes:

Notes from the zoom chat:

00:19:46	Ramkumar Chinchani:	Status of multi-hash?
00:23:00	Tianon:	vbatts response will probably be "OHMAN"
00:23:25	Brandon Mitchell:	Time's fun when you're having flies
00:23:47	Derek McGowan:	It seems a missed a conversation where there was agreement to create the word “ASCIIbetical”. While cute, can we just say “ascii order” in the spec and can explain that in the first use that is equivalent to case-sensitive or byte ordering.
00:24:05	Tianon:	Replying to "It seems a missed a ..." I didn't create it, though 😅
00:24:11	Tianon:	Replying to "It seems a missed a ..." it's a pre-existing word, although not a super popular one
00:24:23	Tianon:	Replying to "It seems a missed a ..." feel free to suggest an alternative wording on the PR and I'm happy to adjust
00:24:39	Ramkumar Chinchani:	https://en.wiktionary.org/wiki/ASCIIbetical
00:26:29	Ramkumar Chinchani:	"informal" means trouble in a technical spec
00:34:52	Sajay Antony:	Folks need to drop for another meeting. Thank you.

## July 24, 2025

**Recording**: https://youtu.be/XPfMIv6vsOA

### Attendees:

- Tianon
- Brandon Mitchell
- Sajay Antony
- Brian Goff
- Syed Ahmed
- Mike Brown

### Actionable Agenda Items:

- Review needed:
  - schema/go.sum: <https://github.com/opencontainers/image-spec/pull/1274>

### Presentation/Discussion Agenda Items:

- Tag listing sort order: <https://github.com/opencontainers/distribution-spec/pull/583>
- Version and media type inside the image config: <https://github.com/opencontainers/image-spec/issues/1275>

### Notes:

Notes from the zoom chat:

00:02:57	Brandon Mitchell:	https://github.com/opencontainers/image-spec/pull/1274
00:04:16	Tianon:	Replying to "https://github.com/o..." git rm  😇
00:06:34	Brian Goff (@cpuguy83):	https://en.wikipedia.org/?title=ASCIIbetical_order&redirect=no
00:10:16	Brian Goff (@cpuguy83):	If we were all using Windows all these problems would just go away. Case sensitive filesystems, line endings.
00:11:59	Brian Goff (@cpuguy83):	Jeez, should at least be using slices.Sort these days 🤣
00:12:23	Tianon:	Syed had the perfect opportunity to say "the tag listing is supposed to be sorted??"
00:12:46	Tianon:	Replying to "Jeez, should at leas..." Go too old, have to reload
00:13:54	Brian Goff (@cpuguy83):	I can't have emoji in my tags?!
00:14:16	Tianon:	Replying to "I can't have emoji i..." nope, but you sure can punycode them
00:14:29	Tianon:	Replying to "I can't have emoji i..." https://oci.dag.dev/?image=tianon%2Ftest:xn--uo8h
00:14:39	Tianon:	Replying to "I can't have emoji i..." https://oci.dag.dev/?image=tianon%2Ftest:xn--ls8h
00:16:00	Tianon:	Replying to "I can't have emoji i..." https://bsky.app/profile/tianon.bsky.social/post/3lcmlcho5zs24 if you want the context for that 💩 one

## July 17, 2025

**Recording**: https://youtu.be/di21DKPFmNo

### Attendees:

- Brandon Mitchell
- Tianon
- Jory Burson
- Brian Goff
- Sajay Antony

### Actionable Agenda Items:

- Okay to merge schema go.mod changes? <https://github.com/opencontainers/image-spec/pull/1253>
- Review needed for pandoc: <https://github.com/opencontainers/image-spec/pull/1272>
- Review needed for proxy namespace: <https://github.com/opencontainers/distribution-spec/pull/66>

### Presentation/Discussion Agenda Items:

- Range header changes need CI updates: <https://github.com/opencontainers/distribution-spec/pull/581>
- Tag listing needs conformance tests: <https://github.com/opencontainers/distribution-spec/pull/579>

### Notes:

Notes from the zoom chat:

00:12:22	Tianon:	yep, "looks like shell" (https://github.com/moby/moby/pull/9637#issuecomment-66822505 ❤️)
00:14:35	Brian Goff (@cpuguy83):	Replying to "yep, "looks like she..." Funny thing is he said "Looks like Bash" but the PR is making it *not* look like bash 😂
00:14:52	Tianon:	Replying to "yep, "looks like she..." it's all the same to him 😂

## July 10, 2025

**Recording**: https://youtu.be/_d8_IxMEMS0

### Attendees:

- Brian Goff
- Sajay Antony
- Mike Brown
- Derek McGowan
- Brandon Mitchell
- Joseph Ferguson
- Ramkumar Chinchani
- Xiang Gao

### Actionable Agenda Items:

- Review needed:
  - Broken link: <https://github.com/opencontainers/image-spec/pull/1271>
  - Broken link: <https://github.com/opencontainers/wg-auth/pull/14>

### Presentation/Discussion Agenda Items:

- pandoc fixes: <https://github.com/opencontainers/image-spec/pull/1272>
- alternative to linear layers: <https://github.com/opencontainers/image-spec/issues/1270>
- chunked upload `Range` value

### Notes:

Notes from the zoom chat:

00:14:05	Ramkumar Chinchani:	https://github.com/google/go-containerregistry/blob/main/cmd/crane/rebase.md
00:31:49	Brian Goff (@cpuguy83):	fs.FS makes this really nice.
00:36:06	Sajay Antony:	Thanks all. Need to drop for another meeting.
00:42:45	Ramkumar Chinchani:	https://datatracker.ietf.org/doc/html/rfc7233

## July 3, 2025

**Recording**: https://youtu.be/QEhSkvi8qdY

### Attendees:

- Tianon
- Carmi Weinzweig
- Brian Goff
- Jory Burson
- Brandon Mitchell
- Derek McGowan

### Actionable Agenda Items:

None.

### Presentation/Discussion Agenda Items:

- Proxy namespace: <https://github.com/opencontainers/distribution-spec/pull/66>
  - Brandon will push a suggested phrasing for a header.

### Notes:

Notes from the zoom chat:

00:06:14	Brian Goff (@cpuguy83):	OCI Cullinary Community
00:08:35	Jory Burson:	Open Cookery Initiative
00:24:26	Derek McGowan:	https://github.com/containerd/containerd/blob/main/docs/hosts.md#setup-default-mirror-for-all-registries

## June 26, 2025

**Recording**: https://youtu.be/YuktrplNtzQ

### Attendees:

- Jeff Carter
- James Kolb
- Carmi Weinzweig
- Tianon
- Derek McGowan
- Brandon Mitchell
- Brian Goff
- Sajay Antony
- Syed Ahmed
- Mike Brown (IBM)
- Ramkumar Chinchani

### Actionable Agenda Items:

- Reviews needed:
  - FreeBSD: <https://github.com/opencontainers/runtime-spec/pull/1286>
  - GHA Badge: <https://github.com/opencontainers/image-spec/pull/1256>
  - GHA GOPATH: <https://github.com/opencontainers/image-spec/pull/1264>
- Okay to close:
  - Streaming push: <https://github.com/opencontainers/distribution-spec/pull/576>
  - Dependabot: <https://github.com/opencontainers/distribution-spec/pull/572>

### Presentation/Discussion Agenda Items:

- Tag Listing Proposal: <https://github.com/opencontainers/distribution-spec/pull/579>
- Proxy namespace: <https://github.com/opencontainers/distribution-spec/pull/66>
- Range header when 0 bytes transfered: <https://github.com/opencontainers/distribution-spec/issues/578>

### Notes:

Notes from the zoom chat:

00:14:12	Tianon:	"thanks Gobama"
00:14:12	Carmi Weinzweig:	Thanks all. I will pass your comments back and probably be back next week. Heading off to take my car to the dealer, unless there is some other question for me. :-)
00:23:25	Sajay Antony:	This is really nice.
00:24:01	Sajay Antony:	Ah we are back to search.
00:28:06	Tianon:	maybe define the created annotation as optional, but give it an explicit meaning so that if it is specified, clients and users can rely on what the value means?
00:28:53	Tianon:	Replying to "maybe define the cre..." there's definitely value in both the timestamp that the registry (or this repo) first saw a digest and separately the time this tag was most recently updated, but maybe that's too much nuance
00:35:39	Sajay Antony:	I need to drop. Will share this internally.
00:48:01	Ramkumar Chinchani:	different upstreams, different images but same image/tags, avoid clobber?
00:50:20	Tianon:	https://github.com/docker-library/meta-scripts/blob/fab86e62cb31ee1b2ee597399a16db6658897722/registry/docker-hub.go#L9-L16  🧌
00:51:50	Tianon:	Replying to "https://github.com/d..." the whole point of this list is that I consolidate/canonicalize all these down to docker hub 😂
01:03:06	Ramkumar Chinchani:	0-0?
01:04:03	Ramkumar Chinchani:	drop the Range Header in response?

## June 19, 2025

**Recording**: https://youtu.be/HZ33AkIQI2k

### Attendees:

- Alice Sowerby
- Carmi Weinzweig
- Brandon Mitchell
- Sajay Antony
- Brian Goff

### Actionable Agenda Items:

None.

### Presentation/Discussion Agenda Items:

- Add FreeBSD as a supported platform
 <https://github.com/opencontainers/runtime-spec/pull/1286>
  - Let's come back when Tianon is here (and it's not Juneteenth)
- Proxy namespace: <https://github.com/opencontainers/distribution-spec/pull/66>
- Range header when 0 bytes transfered: <https://github.com/opencontainers/distribution-spec/issues/578>
- Meeting shortened for Juneteenth

### Notes:

Notes from the zoom chat:

00:13:06	Brian Goff (@cpuguy83):	Hello
00:14:21	Brian Goff (@cpuguy83):	Yeah no real experience there.
00:16:34	Sajay Antony:	Sorry lost connection.
00:18:45	Brian Goff (@cpuguy83):	Is this related? https://github.com/containerd/containerd/pull/11998

## June 12, 2025

**Recording**: https://youtu.be/jUa2qwX66yM

### Attendees:

- Brandon Mitchell
- Brian Goff
- Tianon
- Sajay Antony
- Ramkumar Chinchani

### Actionable Agenda Items:

None.

### Presentation/Discussion Agenda Items:

- Tag/Manifest listing improvements: <https://github.com/opencontainers/distribution-spec/issues/575>

### Notes:

Notes from the zoom chat:

00:16:33	Sajay Antony:	Happy to support the effort. Working group or otherwise.
00:21:11	Brandon Mitchell:	Or write it up on hackmd 🙃
00:22:38	Sajay Antony:	If WG is light then folks won’t have a concern.

## June 5, 2025

**Recording**: https://youtu.be/dDF152Lhkm4

### Attendees:

- Brandon Mitchell
- Tianon
- Harry Randazzo
- Syed Ahmed
- Jory Burson
- Brian Goff
- Mike Brown

### Actionable Agenda Items:

None.

### Presentation/Discussion Agenda Items:

- Container Plumbing Days
  - 3 hours to schedule
  - 19 talks, 7 talks scored at least 4 stars (out of 5)
- Mounting artifacts as a volume that are not tar files
  - cri-o is pulling in the filename from the ORAS title annotation pattern
  - Tianon would like to add a tar header in front of the artifact to convert it to a tar file

### Notes:

Notes from the zoom chat:

00:12:40	Tianon:	"have y'all heard the good news of open containers?"
00:12:42	Brian Goff (@cpuguy83):	I would love to go, but of course cannot make that.
00:13:07	Tianon:	Replying to ""have y'all heard th..." the double entendre of our name makes this even funnier
00:13:37	Brian Goff (@cpuguy83):	Replying to "I would love to go, ..." Travel is very difficult for me at this time.
00:14:07	Brandon Mitchell:	Replying to "I would love to go, ..." And folks want to be sure they can return home.
00:14:38	Brian Goff (@cpuguy83):	Replying to "I would love to go, ..." My family would all be happy to be stranded in Amsterdam, I think 🙂
00:16:25	Tianon:	Replying to "I would love to go, ..." yeah, given *gestures wildly* I wouldn't feel totally safe flying within the US right now, let alone outside it
00:16:55	Brandon Mitchell:	Replying to "I would love to go, ..." Knowing my luck, my connection would be through Newark.
00:18:35	Brian Goff (@cpuguy83):	Replying to "I would love to go, ..." lol, yeah.
00:21:02	Tianon:	Jory feeling bad that this is "all" she has and she's almost single-handedly carried the empty-agenda meeting for ~20 minutes with relevant content 💪 ❤️
00:23:41	Brian Goff (@cpuguy83):	Nothing like being in a talk and then all of sudden be like "wait... how did I get here? What have I already said?"
00:25:40	Brian Goff (@cpuguy83):	Brain: "Sorry, 500ms of empty space is too much you need to add something else in there"
00:26:45	Brian Goff (@cpuguy83):	Brian is GOMAXPROCS=1 but it sure does know how to make use of iowait
00:28:30	Brian Goff (@cpuguy83):	Tianon in a wig: name of the next runc release.
00:29:19	Mike Brown:	I’m here to fill in the elder category
00:29:53	Brian Goff (@cpuguy83):	Oh I need to get some paper bills in so I can get my kids passports.
00:32:25	Tianon:	what about UID, GID, permissions?
00:32:45	Tianon:	Replying to "what about UID, GID,..." mtime?
00:33:01	Tianon:	Replying to "what about UID, GID,..." (see what I mean about reimplementing the tar header?)
00:37:36	Harry Randazzo:	magic strings prob?
00:38:13	Tianon:	https://pkg.go.dev/archive/tar#Header
00:39:57	Tianon:	Replying to "magic strings prob?" yeah, the only way you get "encoding" is by inferring meaning from the filename (extension, usually) or from magic bytes 😅
00:40:18	Harry Randazzo:	a lot of tar upload implementations also strip the tar header info to make more reproducible tarballs, so some implementations may need to rework to not strip anymore, but that creates more storage overhead
00:40:37	Tianon:	Replying to "magic strings prob?" utf-16 byte-order mark anyone? (thanks Microsoft! 😂)
00:41:34	Tianon:	Replying to "a lot of tar upload ..." yeah, but by the nature of the tar format that'd have to be just zeroing header values, not actually removing the header (or it wouldn't be tar anymore) 🙈
00:42:40	Syed Ahmed:	I build a kind node image with the OCI artifact mount support @ quay.io/syahmed/kindest/node:crio-v1.33 If you want to try it out locally
00:43:42	Tianon:	Replying to "what about UID, GID,..." to convert a raw file into a tar file, all that's required is to append a suitable 512 byte header to the front and it's suddenly a tar file 😅  you can have a layer per file and still append 512 bytes at the front of each one so that you get the semantic data necessary too - a range request can easily start at 512 instead of 0 and the streaming use case is fine again
00:44:12	Tianon:	Replying to "what about UID, GID,..." so "extracting the tar" is a heavy way to describe "read the 512 bytes to get filename, then dump the rest into the file"
00:44:22	Harry Randazzo:	Replying to "a lot of tar uploa..." oh yea, by strip I meant zeroize not actually remove xD
00:47:10	Harry Randazzo:	cant wait to mount a tar that was set to a user that doesnt exist
00:47:36	Brandon Mitchell:	Replying to "cant wait to mount a..." It's just a uid/gid, so it doesn't matter when it doesn't exist.
00:47:54	Harry Randazzo:	oras will auto tar if you specify a dir https://github.com/oras-project/oras-go/blob/main/content/file/utils.go#L36
00:47:54	Tianon:	Replying to "cant wait to mount a..." yeah, as far as the kernel knows/cares, all users are just numbers so they all "exist" 😅
00:48:23	Brandon Mitchell:	Replying to "cant wait to mount a..." But I'm not just a number!
00:49:55	Tianon:	Replying to "cant wait to mount a..." to clarify further, /etc/passwd is a pure-userspace construction (the kernel never reads nor cares about it 👀)
00:51:16	Harry Randazzo:	what is the media type on the config for a mountable artifact?
00:51:18	Tianon:	yeah, it's less "artifacts are bad" and more "if you want filesystem content with filesystem semantics like filename, use the filesystem format"
00:51:37	Tianon:	Replying to "yeah, it's less "art..." and in OCI, that's tar
00:52:52	Brandon Mitchell:	Replying to "what is the media ty..." https://github.com/CloudNativeAI/model-spec/tree/main/specs-go/v1
00:54:15	Mike Brown:	Replying to "yeah, it's less "art..." ^^
00:56:32	Syed Ahmed:	Replying to "yeah, it's less "art..." We can have opinions on how a “mounted” artifact can work it can be similar to how secrets and config maps are mounted inside a container
00:56:43	Syed Ahmed:	Replying to "yeah, it's less "art..." You don’t necessarily  need to wrap it in a tar

## May 29, 2025

**Recording**: https://youtu.be/js5vXeJ4jTM

### Attendees:

- Tianon
- Brandon Mitchell
- Brian Goff
- Syed Ahmed
- Jory Burson
- Sajay Antony
- James Kolb
- Ram Chinchani
- Samuel Karp
- Mike Brown

### Actionable Agenda Items:

None.

### Presentation/Discussion Agenda Items:

- Where does <certification@opencontainers.org> go?
  - <https://github.com/opencontainers/oci-conformance/blob/main/participation-form/OCI_Certified_Form.md>
  - <https://github.com/opencontainers/oci-conformance/pull/127>
- umoci v0.5.0 released: 
  - <https://github.com/opencontainers/umoci/releases/tag/v0.5.0>
  - <https://www.cyphar.com/blog/post/20250525-umoci-0.5>
- Alternative OCI digest implementation: <https://github.com/sudo-bmitch/oci-digest/>
- CNCF voting on ModelPack adoption as a sandbox project: <https://github.com/cncf/sandbox/issues/358>
- Model-spec discussion on media types: <https://github.com/CloudNativeAI/model-spec/issues/54>
- How does cri-o handle ownership/permissions/etc when mounting artifacts without tar packaging? <https://github.com/cri-o/cri-o/issues/8953>
- Uploading large artifacts: <https://github.com/opencontainers/distribution-spec/issues/573>

### Notes:

Notes from the zoom chat:

00:06:33	Sajay Antony:	+1 @Tianon
00:08:34	Ramkumar Chinchani:	where is Josh?
00:19:52	Ramkumar Chinchani:	aptly "oci-digest"?
00:31:17	Tianon:	"those who don't understand tar headers are doomed to reimplement them" (and probably in some cursed JSON)
00:33:45	Tianon:	I'll go on the record again: such huge files are bad and we collectively should feel bad
00:35:23	Samuel Karp:	registry operator can control the maximum layer size
00:35:53	Samuel Karp:	ECR limit used to be 10GiB iirc.  Sounds like you raised it since I left though.
00:36:51	Tianon:	Replying to "ECR limit used to be..." this is literally exactly the number that came to mind for me as a sane limit when you suggested it was possible
00:40:53	Tianon:	"panic at dis go"
00:41:37	Jory Burson:	Replying to ""panic at dis go"" Panic, at the disc, Go!
00:41:53	Sajay Antony:	Ntd folks. Thank you.
00:47:29	Tianon:	https://github.com/opencontainers/go-digest/blob/master/MAINTAINERS
00:55:42	Tianon:	An invalid digest string will case the marshaler to fail.
I could see this being problematic for using this in the image-spec structs -- tools will have a hard time returning good structured errors if the unmarshal fails and they can't somehow delay validation (and provide more detail/structure to their errors)
00:57:36	Tianon:	Replying to "An invalid digest st..." for example, something like https://github.com/opencontainers/distribution-spec/blob/v1.1.1/spec.md#error-codes  (I guess this is notably missing a code for "unsupported digest algorithm" or "invalid digest string" but it is conceivable)
00:59:28	Ramkumar Chinchani:	imo, validation and conformance should "belong" in the spec repo.
01:02:59	Samuel Karp:	I think I win the "tab is open and it takes me a while to get to it" prize

## May 23, 2025

**Recording**: https://youtu.be/lyhLh_bgOO4

### Attendees:

- Tianon
- Brandon Mitchell
- Jory Burson
- Jeff Carter
- Ramkumar Chinchani
- Brian Goff
- Derek McGowan
- Syed Ahmed
- Sajay Antony

### Actionable Agenda Items:

None.

### Presentation/Discussion Agenda Items:

- Querying registry for updates: <https://github.com/opencontainers/distribution-spec/issues/575>
- Splitting out image-spec json schema tests: <https://github.com/opencontainers/image-spec/pull/1253>
- Cleanup GHA for image-spec: <https://github.com/opencontainers/image-spec/issues/1263>
- Container plumbing days mini-summit
  - Attendance is looking good

### Notes:

Notes from the zoom chat:

00:13:49	Ramkumar Chinchani:	https://github.com/opencontainers/distribution-spec/issues/71
00:19:28	Tianon:	https://oci.dag.dev/?repo=registry.k8s.io%2Fbusybox an example of someone who's already overloaded the "tag listing" API with more metadata
00:22:31	Tianon:	Replying to "https://oci.dag.dev/..." https://oci.dag.dev/?repo=gcr.io/distroless/static
00:25:21	Sajay Antony:	Replying to "https://oci.dag.dev/..." This is nice.
00:27:01	Ramkumar Chinchani:	guidelines: 1. handle large scale 2. don't make more work for registry
00:27:10	Ramkumar Chinchani:	ntd early today
00:29:40	Jeff Carter:	could just do it as a GET /v2/<name>/manifests/?n=<integer>&sort=tktk&last=<last> fixes the issue with "list" being a possible reference
00:35:26	Tianon:	https://pkg.go.dev/github.com/opencontainers/image-spec/schema?tab=importedby
00:36:45	Sajay Antony:	NTD early for another meeting folks. Thank you.

## May 15, 2025

**Recording**: https://youtu.be/iPSRwC0dI-E

### Attendees:

- Brandon Mitchell
- Ramkumar Chinchani
- Sajay Antony
- Jeff Carter
- Samuel Karp
- Mike Brown
- James Kolb

### Actionable Agenda Items:

None

### Presentation/Discussion Agenda Items:

- Progress on pushing manifest with alternate digest algorithms
  - Currently behind rewriting conformance tests
  - That's behind getting auth standardized (stalled WG)
  - Brandon is temporarily distracted working on a v2 proposal to go-digest
- No other agenda items so the meeting ended early.

### Notes:

Notes from the zoom chat:

00:03:42	Sajay Antony:	Small group today.
00:07:00	Brandon Mitchell:	https://github.com/sudo-bmitch/oci-digest/
00:10:47	Samuel Karp:	wrap up early is always a good option if we have no agenda

## May 8, 2025

**Recording**: https://youtu.be/LSEyukQX1Fw

### Attendees:

- Brandon Mitchell
- Jeff Carter
- Ramkumar Chinchani
- Harry Randazzo
- James Kolb
- Derek McGowan
- Syed Ahmed
- Samuel Karp
- Sajay Antony

### Actionable Agenda Items:

None

### Presentation/Discussion Agenda Items:

- Is concurrent upload support needed?
  - <https://github.com/opencontainers/distribution-spec/issues/546>
  - <https://github.com/opencontainers/distribution-spec/issues/573>
  - <https://github.com/opencontainers/distribution-spec/issues/574>
- How would we support digest encodings other than hex?
  - <https://github.com/opencontainers/image-spec/blob/v1.0.1/descriptor.md#digests>
  - <https://github.com/opencontainers/go-digest/blob/1e56c6daea3b29090ddd17e3e9d88196f0d8815b/algorithm.go#L249-L256>
  - Brandon demoing an alternative digest implementation <https://github.com/sudo-bmitch/oci-digest/>
- Ram demoing blake3 with stacker
- Harry asking about conditional manifest pushing
  - <https://github.com/opencontainers/distribution-spec/issues/250>

### Notes:

Notes from the zoom chat:

00:23:07	Ramkumar Chinchani:	push s3 blobs directly. push manifest referring to blobs to OCI reg backed by s3. OCI spec doesn't say I need to use the blob push API first to push the manifest
00:28:25	Sajay Antony:	Feel free to let' Shiwei know. he's a crypto guy btw.
00:30:31	Sajay Antony:	Replying to "push s3 blobs direct..." These scenarios would then need cloud specific tooling right? Also might be a comeback for remoteUrls which we tried to deprecate.
00:31:32	Ramkumar Chinchani:	Replying to "push s3 blobs direct..." Still in the camp that this is a special use case ... until camps get switched
00:34:30	Sajay Antony:	Need to drop for another appointment.
00:39:23	Ramkumar Chinchani:	https://github.com/zeebo/blake3/issues/7

## May 1, 2025

**Recording**: https://youtu.be/3BeERAs7n0k

### Attendees:

- Tianon
- Brandon Mitchell
- Ramkumar Chinchani
- Samuel Karp
- Jeff Carter
- Derek McGowan
- Brandon Klein
- James Kolb
- Harry Randazzo
- Brian Goff
- Mike Brown

### Actionable Agenda Items:

None.

### Presentation/Discussion Agenda Items:

- Supporting push by tag with alternate digest algorithms: <https://github.com/opencontainers/distribution-spec/pull/543>
- Promote blake3 in go-digest: <https://github.com/opencontainers/go-digest/pull/108>.
- Parallel hashing proposal: <https://github.com/opencontainers/distribution-spec/issues/574>.
- Invalid layer media types discussion from sig-node and ORAS.

### Notes:

Notes from the zoom chat:

00:04:55	Ramkumar Chinchani:	https://github.com/opencontainers/distribution-spec/pull/543
00:15:02	Ramkumar Chinchani:	https://github.com/opencontainers/go-digest/pull/108
00:18:06	Brandon Mitchell:	https://github.com/golang/go/issues/36632
00:22:31	Brandon Mitchell:	https://github.com/golang/go/issues/70471
00:27:54	Brandon Mitchell:	https://pkg.go.dev/hash
00:31:16	Brian Goff (@cpuguy83):	You could implement v1 on v2 (in the case of removing panics in v2)
00:34:17	Brandon Mitchell:	brb
00:34:37	Derek McGowan:	https://pkg.go.dev/crypto#Hash
00:36:50	Derek McGowan:	Vs https://pkg.go.dev/hash#Hash
00:37:14	Brian Goff (@cpuguy83):	https://github.com/opencontainers/go-digest/commit/b9e02e015be61903bbee58e3fd349114fa28e0b4
00:41:49	Brian Goff (@cpuguy83):	"The cryptoHash interface mimics crypto.Hash, but is a subset of the methods that we require. crypto.Hash is a concrete type that makes it hard to bring new hash function implementations in."
00:42:38	Brian Goff (@cpuguy83):	panic at the digest
00:46:14	Derek McGowan:	https://github.com/opencontainers/go-digest/blob/master/digest.go#L135  this will probably cause panics in some codebases
00:46:46	Brian Goff (@cpuguy83):	`defer recover()` no problem.
00:46:59	Brian Goff (@cpuguy83):	Woah zoom does code blocks now.
00:48:09	Brian Goff (@cpuguy83):	Should do a named release like runc does "Don't panic!"
00:52:50	Ramkumar Chinchani:	https://github.com/opencontainers/distribution-spec/issues/574 just landed
00:55:28	Brian Goff (@cpuguy83):	NTD
00:56:34	Tianon:	Replying to "https://github.com/o..." not sure I understand why this isn't a comment on #573 - because it's a concrete proposal?
00:58:57	Tianon:	"put your file in a tar" sounds heavier than it is -- just generate a single simple binary tar header and prepend it on your file during upload (and use the uncompressed tar media type)
00:59:47	Tianon:	Replying to ""put your file in a ..." then you get all the https://pkg.go.dev/archive/tar#Header fields for "free", and existing container image tooling "just works" (and an efficient packing format, to boot, unlike strings in a JSON object of annotations)
01:00:20	Brandon Mitchell:	Replying to ""put your file in a ..." "free" as the consumer, but that metadata now needs to be generated by the producer
01:00:55	Tianon:	Replying to ""put your file in a ..." but this is metadata they're already stuffing into annotations
01:01:01	Tianon:	Replying to ""put your file in a ..." most of it's optional
01:02:33	Derek McGowan:	https://github.com/containerd/containerd/pull/11744
01:03:51	Ramkumar Chinchani:	IANA redux?
01:04:05	Tianon:	Replying to "IANA redux?" IANA/v2
01:04:16	Brandon Mitchell:	Replying to "IANA redux?" OCANA

## April 24, 2025

**Recording**: https://youtu.be/KHJKOSk48o0

### Attendees:

- Brandon Mitchell
- Tianon
- Derek McGowan
- Ramkumar Chinchani
- Brian Goff
- Syed Ahmed
- Jeff Carter
- Mike Brown

### Actionable Agenda Items:

None

### Presentation/Discussion Agenda Items:

- blake3: <https://github.com/opencontainers/image-spec/pull/1240>
- Parallel blob upload and large blob handling: <https://github.com/opencontainers/distribution-spec/issues/573>

### Notes:

Notes from the zoom chat:

00:03:46	Brandon Mitchell:	https://github.com/opencontainers/image-spec/pull/1240
00:05:30	Tianon:	blake3 also supposedly makes it possible to do checksum verification on a partial pull, thanks to the merkle dag
00:06:37	Tianon:	Replying to "blake3 also supposed..." https://en.wikipedia.org/wiki/BLAKE_(hash_function)#BLAKE3
00:07:05	Tianon:	Replying to "blake3 also supposed..." "In addition to providing parallelism, the Merkle tree format also allows for verified streaming (on-the-fly verifying) and incremental updates."
00:10:54	Brandon Mitchell:	Sounds like my suggestion on the parallel blob uploads, make a new hash algorithm definition: https://github.com/opencontainers/distribution-spec/issues/573#issuecomment-2815931325
00:11:16	Derek McGowan:	Do we need a large artifacts working group?
00:11:45	Brandon Mitchell:	Replying to "Do we need a large a..." If someone wants to run it, raise it with the TOB.
00:14:46	Brandon Mitchell:	https://github.com/opencontainers/distribution-spec/issues/573
00:18:27	Tianon:	"org.opencontainers.image.digest.sha256", "org.opencontainers.image.digest.blake3", etc etc as annotations? 👀
00:18:36	Brandon Mitchell:	"400GB models": Hub maintainers crying in S3 bills.
00:18:50	Tianon:	Replying to ""org.opencontainers...." similar to how the in-toto version of our "descriptor" object has digest as a map instead of just a string
00:20:56	Tianon:	https://docs.kernel.org/admin-guide/device-mapper/verity.html#hash-tree
00:21:57	Ramkumar Chinchani:	https://docs.kernel.org/admin-guide/device-mapper/verity.html devicemapper verity
00:21:59	Jeff Carter:	Replying to ""400GB models": Hub ..." i should share my hack of building an S3 API on top of an OCI registry, where an OCI artifact = s3 bucket
00:22:04	Ramkumar Chinchani:	block-based
00:28:35	Brandon Mitchell:	Everything is a merkle tree of hashes :D
00:32:38	Jeff Carter:	we've seen manifests with 25,000 layers. At 5gb chunks, that's space for a 125 TB model :D
00:33:39	Brian Goff:	200KB, guess I have to get off dial-up finally.
00:35:41	Tianon:	https://github.com/opencontainers/distribution-spec/pull/293#issuecomment-1452780554
00:36:26	Tianon:	Replying to "https://github.com/o..." if you copy https://oci.dag.dev/?image=tianon%2Ftest:eeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeee  and try to make it even one single byte bigger, Hub will reject it
00:38:16	Tianon:	Replying to "https://github.com/o..." https://iliana.fyi/blog/e98e/ for anyone who isn't familiar with the reference (it's a delightful story about GitHub)
00:51:39	Syed Ahmed:	Windows containers
00:57:13	Brandon Mitchell:	https://developers.cloudflare.com/workers/platform/limits/#response-limits
01:01:50	Ramkumar Chinchani:	https://github.com/pytorch/pytorch/issues/141350

## April 17, 2025

**Recording**: https://youtu.be/Vp8sfMPuqcA

### Attendees:

- Brandon Mitchell
- Jory Burson
- Ramkumar Chinchani
- Sajay Antony
- Jeff Carter
- Samuel Karp
- Syed Ahmed

### Actionable Agenda Items:

None

### Presentation/Discussion Agenda Items:

- Support for other layer media types: <https://github.com/opencontainers/image-spec/pull/1191>
  - Rework the PR to focus on whether OCI should support new media types (`manifest.md`)
  - Discussion from there can look at how much this improves performance
- More discussion on parallel blob uploads
  - Recommendation to open an issue in GitHub to consolidate the discussion
- License annotation usage: <https://github.com/opencontainers/image-spec/issues/1257>
- Reference spec working group: <https://github.com/opencontainers/tob/pull/114>

### Notes:

Notes from the zoom chat:

00:05:53	Brandon Mitchell:	https://groups.google.com/a/opencontainers.org/g/tob
00:16:52	Sajay Antony:	Hey @Syed, Given the discussion of concurrent upload, there is some interest in folks i talked to in Azure as well.
00:24:09	Samuel Karp:	yep, count me in
00:26:21	Syed Ahmed:	So far I see LLMs, VM images, libs
00:27:14	Sajay Antony:	Yep VM images are also in the mix here.
00:30:29	Syed Ahmed:	Yes, agree with the compatibility aspect
00:31:18	Ramkumar Chinchani:	overlap with CDN ideas
00:32:14	Syed Ahmed:	I’ll create a channel in the dist slack for this

## April 10, 2025

**Recording**: https://youtu.be/SEih1RI7sFA

### Attendees:

- Tianon
- Syed Ahmed
- Jory Burson
- Brian Goff
- Brandon Mitchell
- Sajay Antony
- Derek McGowan
- Mike Brown
- Michael Brown
- Samuel Karp

### Actionable Agenda Items:

- Container Plumbing Days CFP is open, promotions encouraged: <https://groups.google.com/a/opencontainers.org/g/dev/c/lWLddPSeyRU/m/w1KTQ-hLBAAJ>
- _add your items_

### Presentation/Discussion Agenda Items:

- Fixing image-spec badge
  - Previous PR was closed: <https://github.com/opencontainers/image-spec/pull/1251>
- Reference spec working group: <https://github.com/opencontainers/tob/pull/114>
- Mailing list spam
  - <https://groups.google.com/a/opencontainers.org/g/dev>
  - <https://groups.google.com/a/opencontainers.org/g/tob>
- parallel blob upload/download
  - Out of order push: <https://github.com/opencontainers/distribution-spec/issues/546>
  - Blake3: <https://github.com/opencontainers/image-spec/pull/1240>
  - erofs/squashfs: <https://github.com/opencontainers/image-spec/pull/1191>
  - dm-verity: <https://docs.kernel.org/admin-guide/device-mapper/verity.html>
  - ability to shard a blob into multiple chunks with multiple digests and a map of digests
  - Derek: spec should follow an implementation
  - Brandon: consider making the chunks into blobs/layers to avoid redesigning registries
- Deferred: Support for other layer media types: <https://github.com/opencontainers/image-spec/pull/1191>

### Notes:

Notes from the zoom chat:

00:18:54	Mike Brown:	new KEP that may be semi related https://github.com/kubernetes/enhancements/pull/5097
00:19:41	Derek McGowan:	I thought LF moved everything over to that other system
00:20:35	Mike Brown:	kep ^ excerpt: “The proposal aims to address the challenge of verifying which registry an image is being pulled from when deploying applications in Kubernetes having multiple image mirrors configured. Currently, users have to manually check the runtime logs to determine which registry was being used, but this approach can be time-consuming and error-prone. The proposed solution seeks to provide transparency by adding a new field in the container status as well as in the image inspect section which provides the details of the registry from where the image is pulled. This would help users to better manage their applications' dependencies, troubleshoot issues related to image availability, and ensure compliance with organization security policies.”
00:20:43	Brian Goff (@cpuguy83):	❤️ the internet
00:38:31	Sajay Antony:	@Syed Ahmed can we also call out why we need an API/spec here and why not go down something like QUIC
00:39:26	Tianon (he/him):	+1 to Derek ❤️; at the very least, it would help to have a proof of concept that clearly shows the problem, the solution, and how much better, faster, stronger, etc the solution is (and concretely how hard it might be to change other clients/servers to support it)
00:42:06	Sajay Antony:	Replying to "@Syed Ahmed can we a..." ok maybe this was a stupid question since multi stream for a single patch isn't in scope.
00:57:05	Tianon (he/him):	"For uploads, your updated AWS client automatically calculates a checksum of the object and sends it to Amazon S3 along with the size of the object as a part of the request."
00:57:11	Tianon (he/him):	Replying to ""For uploads, your u..." https://docs.aws.amazon.com/AmazonS3/latest/userguide/mpuoverview.html
00:58:42	Brandon Mitchell:	"Amazon S3 automatically uses the CRC-64/NVME checksum algorithm."

## April 3, 2025

Canceled for KubeCon EU

## April 1, 2025 (KubeCon EU)

**Recording**: https://youtu.be/FGjZvVR_N38

10am - 11am BST [convert to your timezone](https://dateful.com/time-zone-converter?t=10am&d=2025-04-01&tz2=British-Summer-Time-BST)
Level 1, ICC Prince Regent Room 1

### Attendees:

- Mike Brown
- Samuel Karp
- Antoni Oeja
- Alexander Kanevskiy
- Arnaud Meukam
- Toru Komatsu
- Phil Estes
- Giuseppe Scrivano
- Akihiro Suda

### Actionable Agenda Items:

None

### Presentation/Discussion Agenda Items:

- (@aojea) [Linux Network Devices runtime-spec](https://github.com/opencontainers/runtime-spec/pull/1271)
    - Latest version with a more thoroughly explanation of all edge cases and internal details of the proposal
    - [runc implementation](https://github.com/opencontainers/runc/pull/4538) with end to end test cases covering the main user stories
    - [slides](https://docs.google.com/presentation/d/1Vdr7BhbYXeWjwmLjGmqnUkvJr_eOUdU0x-JxfXWxUT8/edit?slide=id.g2f0d2381f13_0_852#slide=id.g2f0d2381f13_0_852)
    - Next steps: introduce container edits in CDI spec and in NRI protocol

- (@kad) Old PRs about RDT:
    - [Schemata in spec](https://github.com/opencontainers/runtime-spec/pull/1230)
    - [Docs clarification](https://github.com/opencontainers/runtime-spec/pull/1196)
-  (@kad) [Linux Memory Policy](https://github.com/opencontainers/runtime-spec/pull/1282)

### Notes:

Notes from the zoom chat:

00:26:29	Arnaud Meukam:	https://docs.google.com/presentation/d/1Vdr7BhbYXeWjwmLjGmqnUkvJr_eOUdU0x-JxfXWxUT8/edit#slide=id.g2f0d2381f13_0_852
00:30:48	Phil Estes:	https://github.com/opencontainers/runtime-spec/pull/1271
