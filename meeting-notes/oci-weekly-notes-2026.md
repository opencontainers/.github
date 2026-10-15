# OCI Weekly Dev Meeting Notes Archive - 2026

## September 24, 2026

**Recording**: https://youtu.be/I2k_SHar2ic

### Attendees:

- Tianon
- Brandon Mitchell
- Brian Goff
- Samuel Karp
- Jory Burson
- Ramkumar Chinchani

### Actionable Agenda Items:

- distribution-spec reviews:
  - `digest-algorithm` conformance test: <https://github.com/opencontainers/distribution-spec/pull/623>
  - Transport compression conformance test: <https://github.com/opencontainers/distribution-spec/pull/624>
- image-spec reviews:
  - Descriptor integer limits: <https://github.com/opencontainers/image-spec/pull/1334>
  - Deprecate image ID: <https://github.com/opencontainers/image-spec/pull/1336>

### Presentation/Discussion Agenda Items:

- distribution project v3.1.2 released <https://github.com/distribution/distribution/releases/tag/v3.1.2>
- dev mailing list pending message
- Security risk of clients following pagination links.

### Notes:

Notes from the zoom chat:

00:08:14	Samuel Karp:	spam
00:08:17	Brian Goff:	People are so into OCI. They will be so excited.
00:08:31	Tianon:	+1 spam
00:09:49	Brian Goff:	SHould be in the spec.
00:11:29	Tianon:	with all the love in the world, I would cancel this meeting if I thought I could get away with it

## September 17, 2026

**Recording**: https://youtu.be/qj2N_qpsacE

### Attendees:

- Brandon Mitchell
- Tianon
- Ramkumar Chinchani
- Jory Burson
- Sajay Antony
- Brian Goff

### Actionable Agenda Items:

- distribution-spec reviews:
  - `digest-algorithm` conformance test: <https://github.com/opencontainers/distribution-spec/pull/623>
  - Transport compression conformance test: <https://github.com/opencontainers/distribution-spec/pull/624>
- image-spec reviews:
  - Remove golangci-lint: <https://github.com/opencontainers/image-spec/pull/1337>
  - Descriptor integer limits: <https://github.com/opencontainers/image-spec/pull/1334>
  - Deprecate image ID: <https://github.com/opencontainers/image-spec/pull/1336>

### Presentation/Discussion Agenda Items:

- rootfs.diffids pr was closed quick: <https://github.com/opencontainers/image-spec/pull/1340>
- containerd released: <https://github.com/containerd/containerd/releases/tag/v2.4.0>
- AI Coding disclosure: <https://docs.kernel.org/process/coding-assistants.html>

### Notes:

Notes from the zoom chat:

00:10:01	Brian Goff:	9PB
00:11:12	Brian Goff:	5 years from now and AI models have zillions of params we'll come back to this recording and kick ourselves.
00:15:56	Brian Goff:	lol, remembering when we hit issues with 1GB layers, then 4GB layers.
00:15:59	Sajay Antony:	Sounds like a seed vault for models.
00:16:59	Brian Goff:	They get split into separate files, and even distributed.
00:17:52	Ramkumar Chinchani:	model lineages?
00:21:45	Sajay Antony:	This is neat - https://docs.kernel.org/process/coding-assistants.html
00:22:28	Brian Goff:	Assisted-By: Slopus
00:22:53	Brian Goff:	I think the content of the change is often its own atribution to the model.
00:22:56	Jory Burson:	brb
00:24:21	Brian Goff:	Excuse me while I go yell at my models.

## September 10, 2026

**Recording**: https://youtu.be/bJCSMWgwmwQ

### Attendees:

- Samuel Karp
- Brian Goff
- Brandon Mitchell
- El hadji Abdoul Samba Dia
- Sajay Antony
- Ramkumar Chinchani

### Actionable Agenda Items:

- distribution-spec reviews:
  - `digest-algorithm` conformance test: <https://github.com/opencontainers/distribution-spec/pull/623>
  - Transport compression conformance test: <https://github.com/opencontainers/distribution-spec/pull/624>
- image-spec reviews:
  - Remove golangci-lint: <https://github.com/opencontainers/image-spec/pull/1337>
  - Descriptor integer limits: <https://github.com/opencontainers/image-spec/pull/1334>
  - Deprecate image ID: <https://github.com/opencontainers/image-spec/pull/1336>

### Presentation/Discussion Agenda Items:

- How should tooling handle mixed digest algorithms in content
  - This is expected when a base image has a different algorithm with some build tooling
  - Signing tooling shouldn't make assumptions based on the algorithm of the manifest, but it could provide extra assurances based on its own scan of the content being signed
- Can registries switch between bearer and basic auth? Should they support clients that reuse auth tokens with old scopes for new requests?

### Notes:

Notes from the zoom chat:

00:22:18	Brandon Mitchell:	https://github.com/goharbor/harbor/issues/18856
00:27:02	Sajay Antony:	Thanks for driving the meeting Brandon

## September 3, 2026

**Recording**: https://youtu.be/e8-4DsuVYK8

### Attendees:

- Brandon Mitchell
- Derek McGowan
- El hadji Abdoul Samda Dia
- Jeff Carter
- Shaon Hossain
- Sajay Antony
- Brian Goff
- Jory Burson
- Samuel Karp

### Actionable Agenda Items:

- distribution-spec reviews:
  - `digest-algorithm` conformance test: <https://github.com/opencontainers/distribution-spec/pull/623>
  - Transport compression conformance test: <https://github.com/opencontainers/distribution-spec/pull/624>
- image-spec reviews:
  - Remove golangci-lint: <https://github.com/opencontainers/image-spec/pull/1337>
  - Descriptor integer limits: <https://github.com/opencontainers/image-spec/pull/1334>
  - Deprecate image ID: <https://github.com/opencontainers/image-spec/pull/1336>

### Presentation/Discussion Agenda Items:

- Transport compression may have issues with some clients, Jeff to follow up
- CRA requirements: <https://groups.google.com/a/opencontainers.org/g/tob/c/IpZ2_e35Zew>
- Jory is working on getting our room at KubeCon

### Notes:

No notes.

## August 27, 2026

**Recording**: https://youtu.be/uTn2lXoRCf8

### Attendees:

- Brandon Mitchell
- Tianon
- Brandon Klein
- Yi Chen
- El hadji Abdoul Samba Dia
- Jeff Carter
- Derek McGowan
- Samuel Karp
- Sajay Antony
- Shaon Hossain

### Actionable Agenda Items:

- Ready for review:
  - Blob upload location: <https://github.com/opencontainers/distribution-spec/pull/619>

### Presentation/Discussion Agenda Items:

- Deprecate image ID but not chain ID: <https://github.com/opencontainers/image-spec/pull/1336>
- OCI Auth Spec - Basic and Docker Bearer Token Auth
- Response formats for new APIs

### Notes:

Notes from the zoom chat:

00:17:41	Sajay Antony:	Does the TLS use case get covered by the working group?
00:22:57	Jeff Carter:	I want basic + bearer upgrade path 😄
00:23:06	Jeff Carter:	Replying to "I want basic + beare..." Aka session IDs
00:33:19	Derek McGowan:	Replying to "I want basic + beare..." Cookies?
00:34:24	Derek McGowan:	Replying to "I want basic + beare..." I don’t think that would be too hard to support on the client
00:41:10	Jeff Carter:	Replying to "I want basic + beare..." Yeah. Client sends the basic auth, registry can do the token exchange on the backend (which is way faster). Then returns the response along with the generated bearer token for the client to use on the next request so we don’t have redo the authZ check
00:45:53	Tianon:	https://github.com/cue-labs/oci/issues/38
00:54:28	Tianon:	https://developer.mozilla.org/en-US/docs/Web/HTTP/Reference/Headers/Accept-Encoding is how a client specifies that they want transport compression, and which ones they support
00:54:56	Tianon:	Replying to "https://developer.mozilla.org/en-US/docs/Web/HTTP/Reference/Headers/Accept-Encoding is how a client specifies that they want transport compression, and which ones they support" https://developer.mozilla.org/en-US/docs/Web/HTTP/Reference/Headers/Content-Encoding is how the server says it did the thing
00:55:18	Tianon:	Replying to "https://developer.mozilla.org/en-US/docs/Web/HTTP/Reference/Headers/Accept-Encoding is how a client specifies that they want transport compression, and which ones they support"

    // Multiple, in the order in which they were applied
    Content-Encoding: deflate, gzip
    this is cursed
   
00:56:30	Tianon:

    // DisableCompression, if true, prevents the Transport from
	// requesting compression with an "Accept-Encoding: gzip"
	// request header when the Request contains no existing
	// Accept-Encoding value. If the Transport requests gzip on
	// its own and gets a gzipped response, it's transparently
	// decoded in the Response.Body. However, if the user
	// explicitly requested gzip it is not automatically
	// uncompressed.
	DisableCompression bool
    
00:56:39	Tianon:	Replying to "	// DisableCompression, if true, ..." https://pkg.go.dev/net/http#:~:text=DisableKeepAlives%20bool%0A%0A%09//-,DisableCompression,-%2C%20if%20true%2C%20prevents

## August 20, 2026

**Recording**: https://youtu.be/iiJcatupShE

### Attendees:

- Brandon Mitchell
- Shaon Hossain
- Jory Burson
- Tianon
- Jeff Carter
- Brian Goff
- Samuel Karp
- Sajay Antony
- Ramkumar Chinchani
- El hadji Abdoul Samdb Dia

### Actionable Agenda Items:

- Ready for review:
  - Blob upload location: <https://github.com/opencontainers/distribution-spec/pull/619>

### Presentation/Discussion Agenda Items:

- Should image-spec define image ID and layer chain ID? <https://github.com/opencontainers/image-spec/issues/1333>
  - Can probably drop Layer Chain ID.
  - Image ID needs a historical implementers note.
- image-spec descriptor size: <https://github.com/opencontainers/image-spec/pull/1334>
- image-spec linter: <https://github.com/opencontainers/image-spec/pull/1335>
  - Refuse this PR, but probably need to update for the latest version of Go.
- Should we require approval from running actions for all external contributors, not just first time contributors?
  - Declined: there is no access from GHA to anything sensitive.
- CRA may have requirements for specs, Jory will follow up.
- KubeCon NA, Nov 9-12, Salt Lake City, UT. Jory will follow up with an on-site meeting.

### Notes:

Notes from the zoom chat:

00:04:43	Shaon Hossain:	Shaon, Sean, Shaun, Shawn, ...
00:05:13	Tianon:	Replying to "Shaon, Sean, Shaun, Shawn, ..." give Utah a minute; they'll work a Q in there somewhere
00:05:25	Shaon Hossain:	Replying to "Shaon, Sean, Shaun, Sha..." haha
00:11:20	Sajay Antony:	I know ImageId is used in many places. So it would nice if we don’t deleted but move it out to a historical section.
00:13:05	Sajay Antony:	Yes that’s what is used by some scanners.
00:18:19	Jory Burson:	I HAD NO IDEA
00:18:24	Jory Burson:	TY Tianon
00:20:44	Tianon:	Replying to "TY Tianon" wait what did i do
00:22:11	Shaon Hossain:	Does this look like AI generated PR to any of you?
00:23:49	Brian Goff:	Replying to "TY Tianon" Too many things to name, I'm sure.
00:23:50	Sajay Antony:	It’s fair to push back.
00:24:13	Jory Burson:	Replying to "TY Tianon" The unified diff view!!
00:24:22	Shaon Hossain:	+1
00:24:23	Jory Burson:	Replying to "TY Tianon" I didn’t know how to find that
00:25:43	Ramkumar Chinchani:	ci/cd DoS?
00:29:57	Tianon:	Replying to "TY Tianon" it's honestly the only view I ever use 😂
00:30:02	Tianon:	Replying to "TY Tianon" I can't even look at the diff properly in split view
00:34:34	Tianon:	let's delete the Go files
00:35:04	Brandon Mitchell:	Replying to "let's delete the Go files" Flagged and reported as a bot.
00:37:17	Tianon:	Replying to "let's delete the Go files" BEEP BOOP 🤖
00:37:45	Brandon Mitchell:	Maybe Microsoft could help with that, automatically forwarding GHSAs to the CRA. Do we know anyone at MS?
00:38:03	Sajay Antony:	Replying to "Maybe Microsoft coul..." Brian is also here.
00:38:14	Brian Goff:	Replying to "Maybe Microsoft co..." <promptly leaves the meeting>
00:39:54	Brandon Mitchell:	But the sand is so nice, maybe just on the sand with a beach town in between.
00:41:27	Brian Goff:	Is this something that Akrities could/would do? Maybe it too slow.
00:41:35	Brian Goff:	*its
00:41:37	Tianon:	spend our money fighting the legislation instead
00:42:09	Samuel Karp:	Is Akrities doing anything yet? Haven't received anything on the containerd side.
00:42:29	Tianon:	(we're also not part of the CNCF, so I don't think they'd want us under their umbrella for just this)
00:42:56	Samuel Karp:	Akrities is LF, not CNCF (afaik)
00:43:25	Tianon:	right, there was a mention of maybe the CNCF taking care of this for us if they end up doing their own thing
00:43:34	Jory Burson:	https://training.linuxfoundation.org/express-learning/understanding-the-eu-cyber-resilience-act-cra-lfel1001/
00:43:50	Tianon:	Replying to "https://training.linuxfoundation.org/express-learning/understanding-the-eu-cyber-resilience-act-cra-lfel1001/" Europe isn't real and it can't hurt US
00:43:51	Samuel Karp:	Before Jory leaves: have we talked about an OCI meeting at Kubecon NA yet?
00:43:52	Sajay Antony:	Sheesh
00:44:11	Sajay Antony:	Replying to "Sheesh" Well more trainings.

## August 13, 2026

**Recording**: https://youtu.be/94pAsg6lCmo

### Attendees:

- Jeff Carter
- Brandon Mitchell
- Sajay Antony
- Samuel Karp
- Derek McGowan
- Tianon
- Brian Goff
- Sergey Kanzhelev
- Brandon Klein

### Actionable Agenda Items:

- Ready for review:
  - Blob upload location: <https://github.com/opencontainers/distribution-spec/pull/619>

### Presentation/Discussion Agenda Items:

- Merging profiles: https://github.com/opencontainers/runtime-spec/issues/1317 (Sergey)
  - Push back from runtime-spec maintainers
  - Would be good to see multiple implementations
  - Suggestion to open a working group under the TOB
  - Samuel expressed interest in joining the working group

### Notes:

Notes from the zoom chat:

00:08:50	Sajay Antony:	I’m honestly getting pulled in on another project meeting with an overlapping time so might be reduced meeting attendance but can follow up async as needed. So might have to split meeting time 50% attendance going forward.

## August 6, 2026

**Recording**: https://youtu.be/nLE1nPg-0Bo

### Attendees:

- Tianon
- Samuel Karp
- Brandon Mitchell
- Brian Goff
- Jory Burson
- Ramkumar Chinchani

### Actionable Agenda Items:

- Ready for review:
  - Blob upload location: <https://github.com/opencontainers/distribution-spec/pull/619>
- LF support needed to update distribution-spec maintainer list (add tianon, drop vbatts): <https://github.com/opencontainers/distribution-spec/pull/620>

### Presentation/Discussion Agenda Items:

- Is there an RFC or upstream spec for URIs with query parameters formatted as `key=value`?
- go-digest refactoring digestset: <https://github.com/opencontainers/go-digest/pull/120>
- zot conformance was merged: <https://conformance.opencontainers.org/#zot>

### Notes:

Notes from the zoom chat:

00:05:16	Tianon:	is that https://datatracker.ietf.org/doc/html/rfc3986  ?
00:06:36	Jory Burson:	Hi sorry I was eating lunch very fast!
00:07:43	Tianon:	Replying to "Hi sorry I was eating lunch very fast!" the size of the world is wild - I barely got up early enough to make it to this meeting and you're already having lunch
00:08:50	Brian Goff:	News to me, never even heard of this package.

## July 30, 2026

**Recording**: https://youtu.be/F7x3FjMlWTE

### Attendees:

- Brandon Mitchell
- Tianon
- Ramkumar Chinchani
- Shaon Hossain
- El hadji Abdoul Samda Dia
- Jeff Carter
- Derek McGowan
- Samuel Karp

### Actionable Agenda Items:

- Ready for review:
  - Blob upload location: <https://github.com/opencontainers/distribution-spec/pull/619>
  - Add Tianon as a maintainer: <https://github.com/opencontainers/distribution-spec/pull/620> (merged :tada:)

### Presentation/Discussion Agenda Items:

None.

### Notes:

Notes from the zoom chat:

00:10:46	Ramkumar Chinchani:	what if there is HA and the session-id is expected to more "global" across registries?
00:11:05	Sajay Antony:	Actually push location sharing is something that might be interesting.
00:11:34	Tianon:	Replying to "what if there is HA and the session-id is expected to more "global" across registries?" that's still a registry implementation choice and thus a registry implementation concern on how unique their unique ID needs to be, right?
00:12:03	Ramkumar Chinchani:	Replying to "what if there is HA and the session-id is expected to more "global" across registries?" ambiguity is the enemy of standards - just imo
00:13:46	Sajay Antony:	The issue is that then is there value in standardizing the push?
00:17:50	Samuel Karp:	"the registry must support concurrent uploads" not "use a unique ID"
00:20:54	Jeff Carter:	“Additionally, it SHOULD match exactly the `<blob-push-location>` obtained from the `POST` request. It SHOULD NOT be assembled manually by clients except where absolute/relative conversion is necessary.”
00:21:13	Jeff Carter:	Hilariously, after getting the upload location, we don’t even require the client use it
00:25:16	Sajay Antony:	+1 on MUST on the location.

## July 23, 2026

**Recording**: https://youtu.be/BfeBWjSKzLc

### Attendees:

- Tianon
- Brandon Mitchell
- Jon Johnson
- Derek McGowan
- Jory Burson
- Jeff Carter
- Sajay Antony
- Brandon Klein
- Brian Goff
- Samuel Karp
- El hadji Abdoul Samda Dia

### Actionable Agenda Items:

None.

### Presentation/Discussion Agenda Items:

- Blob upload location: <https://github.com/opencontainers/distribution-spec/pull/619>
- Tag history proposal: <https://github.com/opencontainers/distribution-spec/pull/606>
  - Should annotations be used for registry content?
  - Should pagination use the link header?
  - Are there any requirements for a server to retain old tag history? What does a history GC look like?
  - 400 (bad request) for a not finding a digest? It could be a valid request and the server lacks enough history. Consider an empty list and 200 status. Searching for a digest could also return multiple times a tag was assigned that digest.
- Community Inviter is broken: https://opencontainers.org/community/overview/#chat
  - CNCF is using https://github.com/cncf/slack-inviter

### Notes:

Notes from the zoom chat:

00:11:53	Sajay Antony:	Ok I can drop now. My day has been made.
00:11:58	Jory Burson:	The hat makes me happy
00:19:12	Tianon:	sort_by(.annotations | ."org.opencontainers.distribution.tag.created" // ."org.opencontainers.distribution.tag.deleted")
00:20:33	Tianon:	"thinking out loud" is practically the whole ethos of this meeting
00:27:09	Brandon Mitchell:	We're losing language containment.
00:27:47	Sajay Antony:	Descriptor list just slightly > image index.
00:28:28	Jeff Carter:	https://github.com/opencontainers/distribution-spec/pull/579/changes
00:30:08	Brandon Mitchell:	Tianon is trying so hard to bait me.
00:30:12	Jeff Carter:	xml
00:30:43	Derek McGowan:	I gotta drop, if maintainer discussion comes up, I’m supportive of adding a couple more maintainers to distribution spec
00:31:02	Tianon:	Replying to "Tianon is trying so hard to bait me." bait, convince, same picture
00:31:09	Brian Goff:	Mix it up, make people guess. Keep the spec spicy.
00:34:30	Tianon:	"The internet is really really great ... for malware"
00:35:27	Tianon:	empty index is my favorite shape of index
00:38:06	Tianon:	etags don't work great for canonically server-generated content, but if-modified-since and last-modified could be OK (only solve half the problem, not great for actual server-side querying)
00:40:25	Tianon:	a different perspective: a new struct probably requires a change over in the image-spec to add the new struct / decide how it fits in an oci-layout
00:43:04	Sajay Antony:	The referrers choice of index in the end was nice.
00:44:47	Tianon:	https://pkg.go.dev/github.com/opencontainers/distribution-spec/specs-go/v1?tab=importedby
00:44:56	Tianon:	Replying to "https://pkg.go.dev/github.com/opencontainers/distribution-spec/specs-go/v1?tab=importedby" nobody else cares about this module either
00:48:50	Jeff Carter:	It might’ve been the tag listing proposal that we talked about this - it does include manufactured annotations for the response itself, but could include  annotations pulled up from the actual manifests should the registry choose
00:49:28	Jeff Carter:	Replying to "It might’ve been the..." https://github.com/opencontainers/distribution-spec/pull/579/changes#r2172556954
00:49:54	Jeff Carter:	Replying to "It might’ve been the..." I’m proud of myself for remembering a GitHub issue before Tianon did. Extra points for it coming from Tianon himself
00:50:15	Sajay Antony:	If would be good to call out that distribution annotation may be under this namespace.
00:50:23	Tianon:	Replying to "It might’ve been the tag listing proposal that we talked about this - it does include manufactured annotations for the response itself, but could include  annotations pulled up from the actual manifests should the registry choose" literally me, incredible
00:52:22	Tianon:	loving that jeff felt left out and went to find a hat
00:53:17	Sajay Antony:	Ok I need to drop now 🙂
00:53:54	Jory Burson:	I think you are all still friends here
00:54:04	Jory Burson:	In fact I think this would be quite the funny podcast
00:54:05	Samuel Karp:	TOB only
00:54:18	Samuel Karp:	afaik it's just TOB but I'll check
00:54:44	Jon Johnson:	I've heard of a 10 gallon hat but not a litre hat
00:54:51	Jory Burson:	LOL
00:54:52	Brandon Mitchell:	Reacted to "I've heard of a 10 g..." with 🤣
00:55:19	Jon Johnson:	i've got to drop, good to see you all
00:55:41	Tianon:	https://join.slack.com/t/opencontainers/shared_invite/zt-vzxfzkkl-CbsYY9zwMhSTkXlvvhmBVA
00:56:04	Tianon:	Replying to "https://join.slack.com/t/opencontainers/shared_invite/zt-vzxfzkkl-CbsYY9zwMhSTkXlvvhmBVA" I keep this stored in the #opencontainers /topic on IRC because we've had this problem repeatedly over the years
00:56:32	Jeff Carter:	Replying to "https://join.slack.c..." IRC???
00:57:37	Tianon:	Replying to "https://join.slack.com/t/opencontainers/shared_invite/zt-vzxfzkkl-CbsYY9zwMhSTkXlvvhmBVA" the full /topic: The Open Container Initiative is (unfortunately) on Slack -- visit https://chat.opencontainers.org/ to join the conversation (if that doesn't work, try https://join.slack.com/t/opencontainers/shared_invite/zt-vzxfzkkl-CbsYY9zwMhSTkXlvvhmBVA)
00:57:52	Tianon:	Replying to "https://join.slack.com/t/opencontainers/shared_invite/zt-vzxfzkkl-CbsYY9zwMhSTkXlvvhmBVA" mostly for vbatts who was continuously and repeatedly sad that we're not using IRC
00:58:00	Jeff Carter:	Replying to "https://join.slack.c..." Is there a DOI irc client
00:58:11	Tianon:	Replying to "https://join.slack.com/t/opencontainers/shared_invite/zt-vzxfzkkl-CbsYY9zwMhSTkXlvvhmBVA" there is, in fact
00:58:19	Tianon:	Replying to "https://join.slack.com/t/opencontainers/shared_invite/zt-vzxfzkkl-CbsYY9zwMhSTkXlvvhmBVA" https://hub.docker.com/_/irssi
00:58:29	Samuel Karp:	https://github.com/cncf/slack-inviter is what Daniel did for CNCF
00:58:41	Tianon:	Replying to "https://join.slack.com/t/opencontainers/shared_invite/zt-vzxfzkkl-CbsYY9zwMhSTkXlvvhmBVA" since 2015

## July 16, 2026

**Recording**: https://youtu.be/5RrKrKQLdOE

### Attendees:

- Tianon
- Brandon Mitchell
- Mike Brown
- Samuel Karp
- Shaon Hossain
- Jeff Carter
- Derek McGowan
- Brian Goff
- Ramkumar Chinchani

### Actionable Agenda Items:

- Change "reference" in distribution-spec: <https://github.com/opencontainers/distribution-spec/pull/616> (merged)
- Update dependencies in conformance webpage generator: <https://github.com/opencontainers/oci-conformance/pull/134> (diff provided showing no change in output)

### Presentation/Discussion Agenda Items:

- Brandon will open a PR clarifying blob push SHOULD go to `/v2/<name>/blobs/uploads/<unique-id>`
  - After the meeting, <https://github.com/opencontainers/distribution-spec/pull/619> was opened.

### Notes:

Notes from the zoom chat:

00:02:49	Shaon Hossain:	smart
00:07:45	Tianon:	(that emoji reaction is my boat rocking)
00:08:25	Shaon Hossain:	Do we have any one from Red Hat? How can I ask to join?
00:10:13	Mike Brown:	https://github.com/kubernetes/kubernetes/pull/139156#discussion_r3579661421  FYI another image name question came up this week
00:22:12	Tianon:	I don't think this is part of things that were deleted!
00:22:24	Tianon:	Replying to "I don't think this is part of things that were deleted!" (yes, I was actively digging up my notes when someone mentioned 443)
00:24:21	Tianon:	Replying to "I don't think this is part of things that were deleted!" it was missing details about redirects /  Location:  on  GET  requests, but not uploads (we fixed the former in https://github.com/opencontainers/distribution-spec/pull/607)
00:45:16	Tianon:	n=0 coming right up, just for Jeff

## July 9, 2026

**Recording**: https://youtu.be/3l-z1zXzQQE

### Attendees:

- Jory Burson
- Brandon Mitchell
- Jeff Carter
- Shaon Hossain
- Tianon
- Ramkumar Chinchani
- Brian Goff
- Derek McGowan
- El hadji Abdoul Samba Dia

### Actionable Agenda Items:

- Copyright headers:
  - TOB guidance: <https://github.com/opencontainers/tob/pull/159>
  - image-spec: <https://github.com/opencontainers/image-spec/pull/1323>
  - distribution-spec: <https://github.com/opencontainers/distribution-spec/pull/615>
  - All were merged after the meeting finished
- distribution-spec conformance fixes:
  - export output directory: <https://github.com/opencontainers/distribution-spec/pull/614> (merged)
  - set commit hash when building without git: <https://github.com/opencontainers/distribution-spec/pull/617>

### Presentation/Discussion Agenda Items:

- Change "reference" in distribution-spec:
  - Current PR uses "instance" <https://github.com/opencontainers/distribution-spec/pull/616>
  - Issue now suggests "tag-or-digest" (PR was updated after the meeting)

### Notes:

Notes from the zoom chat:

00:15:29	Brandon Mitchell:	https://xkcd.com/1172/
00:16:43	Tianon:	🇺🇸

## July 2, 2026

**Recording**: https://youtu.be/6V59XES_HV0

### Attendees:

- Brandon Mitchell
- Jeff Carter
- Ramkumar Chinchani
- Sajay Antony
- El hadji Abdoul Samda Dia
- Brian Goff

### Actionable Agenda Items:

- Copyright headers:
  - TOB guidance: <https://github.com/opencontainers/tob/pull/159>
  - image-spec: <https://github.com/opencontainers/image-spec/pull/1323>
  - distribution-spec: <https://github.com/opencontainers/distribution-spec/pull/615>
- distribution-spec conformance fixes:
  - export output directory: <https://github.com/opencontainers/distribution-spec/pull/614>
  - set commit hash when building without git: <https://github.com/opencontainers/distribution-spec/pull/617>

### Presentation/Discussion Agenda Items:

- Change "reference" to "instance" in distribution-spec: <https://github.com/opencontainers/distribution-spec/pull/616>
- Conformance results for zot: <https://github.com/opencontainers/oci-conformance/pull/132>
- Add reserved extension names: <https://github.com/opencontainers/distribution-spec/pull/618>
- Update Tag History proposal: <https://github.com/opencontainers/distribution-spec/pull/606>
  - Ability to pass pinned digest -> tag@digest or send as digest query param?
  - Too much overloading of 404?

### Notes:

Notes from the zoom chat:

00:22:29	Ramkumar Chinchani:	deleting a tag also cleans up all history?
00:22:54	Brandon Mitchell:	"Deleted manifests SHOULD NOT be removed from tag history."
00:23:37	Brandon Mitchell:	"Tag history SHOULD remain queryable after the tag is deleted."
00:23:55	Ramkumar Chinchani:	So the behavior is a historical log?
00:28:12	Ramkumar Chinchani:	is there an extension thingie that has already landed in the oci layout?

## June 25, 2026

**Recording**: https://youtu.be/JvXIjSrIpIo

### Attendees:

- Brandon Mitchell
- Brian Goff
- Sajay Antony
- Shaon Hossain
- Ramkumar Chinchani

### Actionable Agenda Items:

- distribution-spec fix to conformance action: <https://github.com/opencontainers/distribution-spec/pull/614>
- oci-conformance result for olareg: <https://github.com/opencontainers/oci-conformance/pull/131>
- TOB copyright header guidance: <https://github.com/opencontainers/tob/pull/159>

### Presentation/Discussion Agenda Items:

- distribution-spec conformance v2 was merged. :tada:
  - blog post is live: <https://opencontainers.org/posts/blog/2026-04-04-distribution-spec-conformance/>

### Notes:

Notes from the zoom chat:

00:08:08	Sajay Antony:	Sounds reasonable.
00:08:47	Shaon Hossain:	Thanks for merging it!
00:09:15	Sajay Antony:	Your single handedly holding up conformance.

## June 18, 2026

**Recording**: https://youtu.be/2rLrXzcupTE

### Attendees:

- Ofek Gabay
- Brandon Mitchell
- Jory Burson
- Brian Goff
- Jeff Carter
- Joao Ricardo Baptista
- Shaon Hossain
- Tianon
- Derek McGowan
- Samuel Karp

### Actionable Agenda Items:

- distribution-spec reviews:
  - conformance v2: <https://github.com/opencontainers/distribution-spec/pull/588>
  - conformance v2 blog post: <https://github.com/opencontainers/opencontainers.org/pull/167>
- TOB
  - copyright header guidance: <https://github.com/opencontainers/tob/pull/159>

### Presentation/Discussion Agenda Items:

- Discussed outstanding issues around starting a reference-spec WG
  - <https://github.com/opencontainers/tob/pull/114>
  - Still lacking ownership that would drive the WG
  - Also lacking concensus within OCI that this would make a good spec

### Notes:

Notes from the zoom chat:

00:04:35	Brian Goff (@cpuguy83):	Always love hearing the word "chuffed"
00:04:56	Jory Burson:	Replying to "Always love hearing ..." I love that word
00:18:20	Brian Goff (@cpuguy83):	"oci-layout://" is buildkit.
00:18:40	Tianon:	Replying to ""oci-layout://" is buildkit." and the syntax is super ambiguous
00:18:58	Tianon:	Replying to ""oci-layout://" is buildkit." has a bunch of really fun (read: sharp) edge cases
00:19:55	Jeff Carter:	rocket.chat
00:20:19	Tianon:	Replying to "rocket.chat" Jon's not even here to get triggered by this reference
00:27:42	Brian Goff (@cpuguy83):	What client would use ref.name?
00:27:48	Brian Goff (@cpuguy83):	Replying to "What client would ..." Seems dangerous.
00:31:10	Jory Burson:	NTD for competing call - talk to you all soon
00:32:11	Tianon:	https://xkcd.com/927/

## June 11, 2026

**Recording**: https://youtu.be/gNWnhyFOqis

### Attendees:

- Brandon Mitchell
- Shaon Hossain
- Ofek Gabay
- Brian Goff
- Derek McGowan
- Jeff Carter
- Mike "pod-spec" Brown
- Sajay Antony
- Joseph Ferguson
- El Hadji Abdoul Samba Dia
- Ramkumar Chinchani

### Actionable Agenda Items:

- distribution-spec reviews:
  - conformance v2: <https://github.com/opencontainers/distribution-spec/pull/588>
  - conformance v2 blog post: <https://github.com/opencontainers/opencontainers.org/pull/167>
  - Update extension spec: <https://github.com/opencontainers/distribution-spec/pull/612> (merged)

### Presentation/Discussion Agenda Items:

- CNCF's AI OCI initiative:
  - <https://github.com/cncf/toc/issues/1740>
  - <https://github.com/cncf/toc/pull/2163>
- Alternate word for "reference" in distribution-spec for tag or digest
  - locator, selector, identifier, tag_or_digest, instance, pointy-mc-point-face, partially qualified reference, resolver
  - r9e .. is a tag or digest
- Character in a reference to reserve for various implementation extensions
  - `scheme://registry:port/repo/path:tag@digest?query_params#implementation_extension`
- FYI: kubernetes KEP using OCI artifacts for security profiles - https://github.com/kubernetes/enhancements/pull/6062
  - Landlock support is coming to the Go stdlib: <https://github.com/golang/go/issues/68595>

### Notes:

Notes from the zoom chat:

00:20:21	Brandon Mitchell:	https://github.com/cncf/toc/pull/2163
00:22:52	Jeff Carter:	“Manifest identifier” -> mid
00:23:12	Jeff Carter:	TorD
00:26:25	Jeff Carter:	mani-pointy
00:26:39	Brian Goff:	pointy-mc-point-face
00:29:09	Shaon Hossain:	tag_or_digest sounds clean
00:31:06	Mike Brown:	r9e is a tag or digest
00:33:58	Sajay Antony:	are we looking at say getting the signature using #sig or something like that?
00:34:54	Sajay Antony:	or are you looking to pass in args?
00:36:22	Brian Goff:	Should be fun to use on a CLI
00:36:26	Ofek Gabay:	Is there option for having several custom implementations for an extension?
00:36:52	Jeff Carter:	We briefly talked about adding support for query params on references… I still want it
00:36:52	Brian Goff:	&
00:37:18	Ramkumar Chinchani:	> Character in a reference to reserve for various implementation extensions
scheme://registry:port/repo/path:tag@digest#implementation_extension
00:37:18	Ramkumar Chinchani:	what is an example of an implementation extension?
00:37:38	Brian Goff:	& is great because you get both the URL headache AND the CLI headache.
00:40:16	Brian Goff:	ntd
00:40:58	Sajay Antony:	I'm cautiously optimistic that this might be useful. But still not sure how its going to be used.
00:41:49	Jeff Carter:	PUT /v2/<repo>/manifest/<tag>?ttl=1d to automatically delete an image!
00:42:42	Ramkumar Chinchani:	http anchor name char = #
00:53:38	Sajay Antony:	That's really helpful @Mike.

## June 4, 2026

**Recording**: https://youtu.be/oS56aG1835I

### Attendees:

- Brandon Mitchell
- Jory Burson
- Brandon Klein
- Sajay Antony
- Jeff Carter

### Actionable Agenda Items:

- distribution-spec reviews:
  - conformance v2: <https://github.com/opencontainers/distribution-spec/pull/588>
  - conformance v2 blog post: <https://github.com/opencontainers/opencontainers.org/pull/167>
  - Update extension spec: <https://github.com/opencontainers/distribution-spec/pull/612>

### Presentation/Discussion Agenda Items:

- Should "developer surveys" be allowed on the dev OCI list?
  - A: Nope.
- Short meeting, adjourn early.

### Notes:

Notes from the zoom chat:

00:02:47	Sajay Antony:	Very loaded question @Brandon
00:08:41	Brandon Mitchell:	https://groups.google.com/a/opencontainers.org/g/dev

## May 28, 2026

**Recording**: https://youtu.be/QHOMZtlgxWw

### Attendees:

- Brandon Mitchell
- Brian Goff
- Tianon
- Jeff Carter
- Samuel Karp
- Jory Burson

### Actionable Agenda Items:

- distribution-spec reviews:
  - conformance v2: <https://github.com/opencontainers/distribution-spec/pull/588>
  - conformance v2 blog post: <https://github.com/opencontainers/opencontainers.org/pull/167>
  - Update extension spec: <https://github.com/opencontainers/distribution-spec/pull/612>
  - Tag History extension: <https://github.com/opencontainers/distribution-spec/pull/606>

### Presentation/Discussion Agenda Items:

No agenda so meeting wrapped up early.

### Notes:

None.

## May 21, 2026

**Recording**: https://youtu.be/nB-CGP_ios8

### Attendees:

- Tianon
- Brandon Mitchell
- Shaon Hossain
- Brian Goff
- Jory Burson
- Jeff Carter
- Brandon Klein
- Derek McGowan

### Actionable Agenda Items:

- distribution-spec reviews:
  - conformance v2: <https://github.com/opencontainers/distribution-spec/pull/588>
  - conformance v2 blog post: <https://github.com/opencontainers/opencontainers.org/pull/167>
  - Tag History extension: <https://github.com/opencontainers/distribution-spec/pull/606>

### Presentation/Discussion Agenda Items:

- Update extension spec: <https://github.com/opencontainers/distribution-spec/pull/612>
- Can registries store multiple digests pointing to the same blob to minimize storage when someone pushes content with multiple algorithms?
- erofs work in containerd getting standardized: <https://github.com/dmcgowan/erofs-image-spec/pull/1>

### Notes:

Notes from the zoom chat:

00:07:02	Brian Goff:	apologies for the open mic with the fire alarm testing :)
00:07:05	Jory Burson:	We covered Lizards already
00:22:59	Derek McGowan:	aha 512 is pointless and no one is ready to commit to Blake. Are there companies requiring sha 512 for security theater?
00:26:26	Jeff Carter:	Sha512 support is more about making sure registries & clients are set up to support other things. We’ve identified a lot of tooling that hardcodes sha256 that we’ve had to get fixed
00:26:35	Jeff Carter:	It’s not really a practical thing we’re seeing
00:29:16	Shaon Hossain:	+1
00:29:54	Jory Burson:	Thanks dad
00:30:28	Brian Goff:	Finding a collision, yeah.
00:32:26	Brian Goff:	Woodworking, Smoking meat, etc...
00:33:21	Derek McGowan:	https://github.com/erofs/erofs-image-spec/pull/1
00:33:59	Tianon:	"in which Tianon suggests yet again that we deprecate diffids completely"
00:34:17	Brandon Mitchell:	Replying to ""in which Tianon sug..." I was waiting for that.
00:34:28	Tianon:	Replying to ""in which Tianon suggests yet again that we deprecate diffids completely"" the broken record is still broken
00:44:44	Brandon Mitchell:	I felt that "ohh"
00:45:41	Brandon Mitchell:	Kubernetes code having a leak of the abstraction? Never!
00:53:17	Tianon:	umoci's history entries are roughly "umoci was here"
00:53:30	Tianon:	Replying to "umoci's history entries are roughly "umoci was here"" (it has flags to control this, but they are pretty wonk)
00:56:04	Derek McGowan:	As you should be

## May 14, 2026

**Recording**: https://youtu.be/gk8CXoQFxtk

### Attendees:

- Brandon Mitchell
- Jory Burson
- Derek McGowan
- Brian Goff
- Jeff Carter
- Shaon Hossain
- Joseph Ferguson
- Michael Brown
- Sajay Antony
- Syed Ahmed

### Actionable Agenda Items:

- distribution-spec reviews:
  - provide non-canonical digest algorithm hint to registries on blob upload: <https://github.com/opencontainers/distribution-spec/pull/543> (merged)
  - conformance v2: <https://github.com/opencontainers/distribution-spec/pull/588>
  - oci-conformance processing of conformance v2: <https://github.com/opencontainers/oci-conformance/pull/130>
  - conformance v2 blog post: <https://github.com/opencontainers/opencontainers.org/pull/167>
  - Tag History extension: <https://github.com/opencontainers/distribution-spec/pull/606>
- image-spec reviews:
  - one sentence per line: <https://github.com/opencontainers/image-spec/pull/1315> (merged)

### Presentation/Discussion Agenda Items:

- Syntax for distribution-spec extensions, does tag need to be a query parameter
  - `GET /v2/<name>/_oci/tag/history/<tag>``
  - `GET /v2/<name>/_oci/tag/history/?tag=<tag>`
  - We could delegate everything after `_<namespace>` to the extension owner
- Query parameters for references
  - `docker push jcarter3/image:temp?ttl=15m`
  - `docker pull debian:latest?cooldown=7d`
  - My need to prefix user submitted query parameters to avoid collisions with OCI query parameters
- erofs work in containerd getting standardized: <https://github.com/dmcgowan/erofs-image-spec/pull/1>

### Notes:

Notes from the zoom chat:

00:08:29	Brandon Mitchell:	https://github.com/opencontainers/image-spec/pull/1315
00:13:31	Brian Goff:	oooh now I need to squat some extensions.
00:15:06	Sajay Antony:	I recall it might be due to the deprecation of `_catalog`
00:15:18	Jeff Carter:	Chainguard added extensions under `_chainguard`
00:21:06	Jeff Carter:	Chainguard History endpoint:
00:21:06	Jeff Carter:	`curl -H "$auth_header" \`
00:21:06	Jeff Carter:	`  https://cgr.dev/v2/chainguard/python/_chainguard/history/latest`
00:21:06	Jeff Carter:	Prior art says it’s okay 😄
00:23:38	Sajay Antony:	I honestly like `_oci/tag/history/<tag>`
00:26:48	Michael Brown:	have to pop out
00:28:00	Brandon Mitchell:	ttl.sh
00:28:29	Brandon Mitchell:	tag or path
00:29:09	Michael Brown:	cool use cases..
00:29:15	Jeff Carter:	`docker push jcarter3/image:temp?ttl=15m`
00:29:15	Jeff Carter:	`docker pull debian:latest?cooldown=7d`
00:29:16	Sajay Antony:	These are really cool and I've heard similar asks.
00:29:29	Brandon Mitchell:	https://github.com/opencontainers/tob/pull/114
00:33:50	Brian Goff:	`oci-layout://` `docker-image://` in buildkit.
00:36:27	Sajay Antony:	Folks NTD.  Thank you.
00:43:25	Brian Goff:	Except for cri :)
00:44:56	Brian Goff:	https://github.com/cpuguy83/go-docker/blob/01fe2a4b3621f76e6a077171f42e38733c66099e/image/ref.go#L44-L86
00:50:03	Brian Goff:	NTD
00:50:33	Derek McGowan:	https://github.com/dmcgowan/erofs-image-spec/pull/1

## May 7, 2026

**Recording**: https://youtu.be/48V0nhy9KEQ

### Attendees:

- Tianon
- Brian Goff
- Brandon Mitchell
- Shaon Hossain
- Jeff Carter
- Jory Burson
- Mike Brown
- Sajay Antony
- Brandon Klein
- Ramkumar Chinchani
- Samuel Karp

### Actionable Agenda Items:

- distribution-spec reviews:
  - provide non-canonical digest algorithm hint to registries on blob upload: <https://github.com/opencontainers/distribution-spec/pull/543>
  - conformance v2: <https://github.com/opencontainers/distribution-spec/pull/588>
  - oci-conformance processing of conformance v2: <https://github.com/opencontainers/oci-conformance/pull/130>
  - conformance v2 blog post: <https://github.com/opencontainers/opencontainers.org/pull/167>
  - RFC pointers and HTTP Redirect support: <https://github.com/opencontainers/distribution-spec/pull/607> (merged)
  - Tag History extension: <https://github.com/opencontainers/distribution-spec/pull/606>
- image-spec reviews:
  - `.wh.` filename handling: <https://github.com/opencontainers/image-spec/pull/1314> (merged)
  - one sentence per line: <https://github.com/opencontainers/image-spec/pull/1315>

### Presentation/Discussion Agenda Items:

- MUST or SHOULD clients follow redirects? <https://github.com/opencontainers/distribution-spec/pull/607/changes#r3139647507>
- Interest in a "reference" spec?
  - <https://github.com/opencontainers/tob/pull/114>
  - <https://github.com/opencontainers/distribution-spec/issues/610>
- Request to improve readability in distribution-spec: <https://github.com/opencontainers/distribution-spec/issues/609>
- json v2 is likely accept in Go: <https://github.com/golang/go/issues/71497>
- repository listing endpoint (_catalog replacement): <https://github.com/opencontainers/distribution-spec/pull/611>

### Notes:

Notes from the zoom chat:

00:04:41	Jory Burson:	Go Ready!
00:11:06	Sajay Antony:	Really happy that we are tacking the delete.
00:11:52	Sajay Antony:	Actually pointing to the deleted digest makes sense.
00:21:30	Brian Goff:	I would want to skip it in the runtime so as not to break existing images.
00:21:41	Sajay Antony:	@Brian Goff I’ll probably lean in on you to consider if white out files would cause any issue 😁
00:24:32	Ramkumar Chinchani:	are we breaking the dist-spec if not MUST?
00:37:09	Sajay Antony:	Need to drop for another meeting folks. Thank you all.
00:37:21	Brian Goff:	NTD for another meeting as well.
00:38:12	Ramkumar Chinchani:	are we envisioning a separate 1.0.x and 1.1.x and 1.2.x series forever?
00:40:06	Jory Burson:	I need to drop to take a quick call! Back in a few, I think!
00:45:08	Tianon:	https://github.com/distribution/distribution/blob/7287385db888a5391c99caa9c608395ccca06f0e/docs/content/spec/api.md#listing-repositories for anyone curious about the OG _catalog spec
00:51:21	Tianon:	https://oci.dag.dev/?repo=registry.k8s.io
00:51:40	Tianon:	Replying to "https://oci.dag.dev/?repo=registry.k8s.io" https://oci.dag.dev/?repo=registry.k8s.io%2Fetcd
00:52:01	Tianon:	Replying to "https://oci.dag.dev/?repo=registry.k8s.io" https://oci.dag.dev/?repo=registry.k8s.io%2Fetcd%2Fetcd
00:52:12	Ramkumar Chinchani:	Replying to "https://oci.dag.dev/?repo=registry.k8s.io" tags=[], child=[...]

## April 30, 2026

**Recording**: https://youtu.be/Wi8229j9K9Y

### Attendees:

- Brandon Mitchell
- Samuel Karp
- Tianon
- Brian Goff
- Jeff Carter

### Actionable Agenda Items:

- distribution-spec reviews:
  - provide non-canonical digest algorithm hint to registries on blob upload: <https://github.com/opencontainers/distribution-spec/pull/543>
  - conformance v2: <https://github.com/opencontainers/distribution-spec/pull/588>
  - oci-conformance processing of conformance v2: <https://github.com/opencontainers/oci-conformance/pull/130>
  - conformance v2 blog post: <https://github.com/opencontainers/opencontainers.org/pull/167>
  - RFC pointers and HTTP Redirect support: <https://github.com/opencontainers/distribution-spec/pull/607>
- image-spec reviews:
  - `.wh.` filename handling: <https://github.com/opencontainers/image-spec/pull/1314>
  - one sentence per line: <https://github.com/opencontainers/image-spec/pull/1315>

### Presentation/Discussion Agenda Items:

No agenda, meeting ended early.

### Notes:

Notes from the zoom chat:

00:05:14        Brian Goff:     AiDHD

## April 23, 2026

**Recording**: https://youtu.be/oHI5eh_uNDE

### Attendees:

- Tianon
- Brandon Mitchell
- Jeff Carter
- Brian Goff
- Samuel Karp
- Sajay Antony
- Ramkumar Chinchani

### Actionable Agenda Items:

- Ready for review:
  - provide non-canonical digest algorithm hint to registries on blob upload: <https://github.com/opencontainers/distribution-spec/pull/543>
  - conformance v2: <https://github.com/opencontainers/distribution-spec/pull/588>
  - oci-conformance processing of conformance v2: <https://github.com/opencontainers/oci-conformance/pull/130>
  - conformance v2 blog post: <https://github.com/opencontainers/opencontainers.org/pull/167>

### Presentation/Discussion Agenda Items:

- Merged pushing digest with tag: <https://github.com/opencontainers/distribution-spec/pull/600>
- Tag History proposal (WIP): <https://github.com/opencontainers/distribution-spec/pull/606> (Jeff)
  - Suggested using `_oci/tags/history` extension for the endpoint to avoid name collisions
- Discussed removal of parts of spec in <https://github.com/opencontainers/distribution-spec/issues/443>
- Need to link to HTTP RFCs for redirects <https://github.com/opencontainers/distribution-spec/issues/397>
  - Currently link to <https://www.rfc-editor.org/rfc/rfc9110.html#name-range-requests> for handling range requests

### Notes:

Notes from the zoom chat:

00:08:11	Brandon Mitchell:	/v2/project-x/tag/manifests/history
00:22:02	Sajay Antony:	It will be easier to route that off
00:23:43	Ramkumar Chinchani:	"standardized" extensions under OCI pls
00:26:12	Ramkumar Chinchani:	pagination, query, etc should be a standard thing for blobs, manifests, "tags", catalog, etc endpoints? we are approaching this piecemeal
00:27:15	Sajay Antony:	Replying to "pagination, query, etc should be a standard thing for blobs, manifests, "tags", catalog, etc endpoints? we are approaching this piecemeal" Its always about who has the energy to push these through.
00:30:21	Ramkumar Chinchani:	the risk is every endpoint behavior looks different if piecemeal
00:41:26	Sajay Antony:	Sorry I need to jump only another security call. Happy to send an update to the PR with the RFC link if folks want to comment in the issue.

## April 16, 2026

**Recording**: https://youtu.be/uCANZLOKKP4

### Attendees:

- Brandon Mitchell
- Brian Goff
- Mike Brown
- Jeff Carter
- Sajay Antony
- Ramkumar Chinchani
- Samuel Karp

### Actionable Agenda Items:

- Ready for review:
  - push digest with tag: <https://github.com/opencontainers/distribution-spec/pull/600>
  - provide non-canonical digest algorithm hint to registries on blob upload: <https://github.com/opencontainers/distribution-spec/pull/543>
  - conformance v2: <https://github.com/opencontainers/distribution-spec/pull/588>
  - oci-conformance processing of conformance v2: <https://github.com/opencontainers/oci-conformance/pull/130>
  - conformance v2 blog post: <https://github.com/opencontainers/opencontainers.org/pull/167>

### Presentation/Discussion Agenda Items:

- OCI Certification (vs Conformance)
  - <https://opencontainers.org/community/certified/>
  - <https://github.com/opencontainers/oci-conformance/blob/main/README.md#oci-certified-conformance-program>
- Clarify `.wh.`: <https://github.com/opencontainers/image-spec/pull/1314/>

### Notes:

Notes from the zoom chat:

00:10:35	Sajay Antony:	Its better to discuss with Jory on this.
00:12:25	Sajay Antony:	I believe the ancestors had good reasoning to do these things.
00:12:44	Sajay Antony:	But always good to revisit.
00:14:23	Brian Goff:	Wait, what is this list? I don't remember this.
00:14:56	Sajay Antony:	Yep I was confused as well and looking up who is Rob Dobin.
00:15:55	Brian Goff:	Haven't worked at Docker since 2018
00:17:24	Sajay Antony:	I'm ok following up for Microsoft but I honestly don't know where to start. Should we just open an issue and tag Jory on it?
00:35:18	Samuel Karp:	That's what I sent to Brandon
00:35:26	Samuel Karp:	I just didn't post it publicly on GitHub for that one
00:36:59	Sajay Antony:	Headers is in the plural sense might be incorrect. But I'm ok merging and correcting as a follow up and I'm not a maintainer. So leaving the decision to the maintainers.
00:39:06	Brian Goff:	At least we didn't have to litigate how to phrase this in the actual RFC
00:42:17	Brian Goff:	Considering purchasing fieldlines.io

## April 9, 2026

**Recording**: https://youtu.be/EZolEXO1uUA

### Attendees:

- Brandon Mitchell
- Tianon
- Jeff Carter
- Ramkumar Chinchani
- Derek McGowan
- Brian Goff
- Jory Burson
- Samuel Karp

### Actionable Agenda Items:

- Ready for review:
  - push digest with tag: <https://github.com/opencontainers/distribution-spec/pull/600>
  - provide non-canonical digest algorithm hint to registries on blob upload: <https://github.com/opencontainers/distribution-spec/pull/543>
  - conformance v2 PRs (see discussion links below).

### Presentation/Discussion Agenda Items:

- Conformance v2 status:
  - conformance v2: <https://github.com/opencontainers/distribution-spec/pull/588>
  - updates to oci-conformance: <https://github.com/opencontainers/oci-conformance/pull/130>
  - separate spec.md changes: <https://github.com/opencontainers/distribution-spec/pull/602>
  - Blog post ready: <https://github.com/opencontainers/opencontainers.org/pull/167>
- New/updated Endpoints:
  - Tag History
  - Tag Listing v2
    - Issue: <https://github.com/opencontainers/distribution-spec/issues/575>
    - PR: <https://github.com/opencontainers/distribution-spec/pull/579>
  - PATCH /manifest to update tags without pushing full manifest
- The existing certified page on the website needs replacing:
  - <https://opencontainers.org/community/certified/>
  - <https://github.com/opencontainers/opencontainers.org/blob/main/content/community/certified.md>
- Discussion on treating distribution-spec more like a storage protocol
  - Related discussion: <https://github.com/opencontainers/distribution-spec/discussions/587>

### Notes:

Notes from the zoom chat:

00:08:30	Ramkumar Chinchani:	enables blake3 path?
00:08:59	Tianon:	Replying to "enables blake3 path?" in the one place left where it was annoying, yeah
00:09:14	Tianon:	Replying to "enables blake3 path?" where a client starts an upload without a digest, uploads the whole blob, then provides a digest
00:09:25	Tianon:	Replying to "enables blake3 path?" so that they can include the digest-algorithm in that first "start upload" request
00:09:53	Tianon:	Replying to "enables blake3 path?" (but even without that, a server can support blake3 here, it just requires a potentially expensive re-hash after the blob upload is already complete)
00:12:34	Tianon:	https://github.com/opencontainers/distribution-spec/pull/579
00:15:35	Jory Burson:	Oh hi
00:16:26	Ramkumar Chinchani:	is this a "search" requirement, phrased differently?
00:18:18	Ramkumar Chinchani:	Replying to "is this a "search" requirement, phrased differently?" search=X wtih "sort" "since" etc etc
00:21:54	Tianon:	fwiw, I love "lightweight tag updates" and think it's worth time/consideration
00:23:39	Ramkumar Chinchani:	Replying to "fwiw, I love "lightweight tag updates" and think it's worth time/consideration" related to multi-tag update?
00:24:21	Tianon:	Replying to "fwiw, I love "lightweight tag updates" and think it's worth time/consideration" related yeah, but not necessarily only - if you know a registry already has a manifest's content, it's kind of silly to re-upload the entire manifest just to assign it to a new tag
00:24:53	Jory Burson:	Is that reason to sh** talk each other
00:25:25	Sajay Antony:	I'm here for weekly multi-vitamins.
00:25:37	Ramkumar Chinchani:	most times just ... speechless, but currently connecting from a public place.
00:28:57	Jory Burson:	lol
00:31:03	Ramkumar Chinchani:	Crazy thought (maybe) ... why is dist-spec a different container thing and not similar to something like NFS and CIFS so that storage folks can just adopt.
00:31:48	Jory Burson:	I have to drop 🙁 I am sorry I was late
00:32:31	Tianon:	Replying to "Crazy thought (maybe) ... why is dist-spec a different container thing and not similar to something like NFS and CIFS so that storage folks can just adopt." see also https://github.com/opencontainers/distribution-spec/discussions/587 for some prior discussion (courtesy of Brandon having put a link to it on an issue recently)

## April 2, 2026

**Recording**: https://youtu.be/WPJ8otszuRY

### Attendees:

- Brandon Mitchell
- Tianon
- Brian Goff
- Derek McGowan
- Jeff Carter
- Shaon Hossain
- Jory Burson
- Samuel Karp

### Actionable Agenda Items:

- Ready for review:
  - remove `go.sum` ignore: <https://github.com/opencontainers/distribution-spec/pull/601>
  - conformance page should render conformance v2 output: <https://github.com/opencontainers/oci-conformance/pull/130>
    - separate spec.md from rest of the changes into a separate PR
  - conformance v2: <https://github.com/opencontainers/distribution-spec/pull/588>

### Presentation/Discussion Agenda Items:

- Pushing tags with a digest: <https://github.com/opencontainers/distribution-spec/pull/600>
- Desire for digest algorithm when pushing blobs with patch API
  - <https://github.com/opencontainers/distribution-spec/pull/543>
- Conformance v2 progress:
  - <https://github.com/sudo-bmitch/distribution-spec/tree/pr-conformance-v2/conformance>
  - <https://github.com/opencontainers/distribution-spec/pull/588>
  - <https://github.com/opencontainers/oci-conformance/pull/130>
- containerd/platforms limits on OS Features: <https://github.com/containerd/platforms/pull/29>

### Notes:

Notes from the zoom chat:

00:14:07	Jory Burson:	Auth by one
00:24:49	Shaon Hossain:	I think, it will have to enabled from Brandon’s account
00:24:49	Samuel Karp:	I've been working on some review prompts too if you want more code review comments from an LLM 😂
00:31:22	Brian Goff:	NTD for a team meeting.
00:37:48	Sajay Antony:	Thanks for need to drop. Hope to see your PR merged Brandon.
00:37:58	Jory Burson:	Branda-bot
00:48:55	Jory Burson:	“It’s your fault for listening to us"

## March 26, 2026

**Recording**: https://youtu.be/VRDpKMj-Bx4

### Attendees:

- Tianon
- Brandon Mitchell
- Jory Burson
- Jeff Carter
- Shaon Hossain
- Samuel Karp
- Brian Goff

### Actionable Agenda Items:

None.

### Presentation/Discussion Agenda Items:

- The calendar link is not easy to find
  - Tianon enthusiastically volunteered to update <https://github.com/opencontainers/opencontainers.org/blob/main/content/community/overview.md>
  - Brandon said the website is a joy to maintain and he's happy to do it forever
- Should auth tokens be reused in conformance tests, and if so, how?
  - <https://github.com/opencontainers/distribution-spec/pull/588#issuecomment-4129594822>
- Redesign go.mod/go.sum handling in distribution-spec?
  - No objection, Brandon will work on a PR to use `go work`.

### Notes:

Notes from the zoom chat:

00:27:00	Brian Goff:	hardware mic switch.
00:30:03	Brian Goff:	C-suites

## March 25, 2026 KubeCon EU

**Recording**: https://youtu.be/DAnasIyCZ70

Location: D501, (5th Floor, Elcium building)

### Attendees:

- Mike Brown
- Alexander
- Krisztian
- Antonio
- Toru Komatsu
- Brandon Mitchell (remote)

### Actionable Agenda Items:

None.

### Presentation/Discussion Agenda Items:

- Networking
  - <https://github.com/opencontainers/runtime-spec/blob/main/config-linux.md#network-devices>
  - <https://github.com/opencontainers/runtime-spec/blob/main/config.md#posix-platform-hooks>
  - CNI: <https://github.com/containernetworking/cni>
  - NRI: <https://github.com/containerd/nri>
  - CDI: <https://github.com/cncf-tags/container-device-interface>
  - CRI: <https://github.com/kubernetes/cri-api>
  - Considering a WG to collaborate
- OCI Podspec is still desired

### Notes:

None.

## March 19, 2026

**Recording**: https://youtu.be/hkyvyqnmXbU

### Attendees:

- Mike Brown (IBM - containerd/kubernetes/oci)
- Brandon Mitchell
- Brian Goff
- Tianon
- Jory Burson
- Jeff Carter
- Sajay Antony
- Shaon Hossain
- Ram Chinchani

### Actionable Agenda Items:

- Jory will look into getting a room at KubeCon EU

### Presentation/Discussion Agenda Items:

- Conformance v2 progress:
  - <https://github.com/sudo-bmitch/distribution-spec/tree/pr-conformance-v2/conformance>
  - <https://github.com/opencontainers/distribution-spec/pull/588>
  - <https://github.com/opencontainers/oci-conformance/pull/130>
  - Desire to allow failed conformance results to be uploaded to conformance page.
  - Brandon should write a blog

### Notes:

Notes from the zoom chat:

00:08:59	Shaon Hossain:	👏
00:15:05	Tianon:	shouldn't we not only allow but even encourage people to submit conformance results with failing tests?  having a record of failing conformance seems more valuable than the alternative of folks not submitting because they're not 100% (which has been something that artificially blocks folks from submitting in the past, and the way you've structured these new tests makes it more obvious exactly what the nuance of the failures is)
00:15:52	Shaon Hossain:	Curious, how did we pick what registry we put in this page? 🙂
00:16:21	Tianon:	Replying to "Curious, how did we ..." all the registries listed on that page are self-conformance result submissions by each registry
00:17:18	Shaon Hossain:	Replying to "Curious, how did we ..." we would like to add Quay in there too
00:17:45	Brian Goff:	Failures are more interesting
00:19:36	Tianon:	Replying to "Curious, how did we ..." if you'd like to submit with the current conformance tests, https://github.com/opencontainers/oci-conformance is the place to do so 🙂
00:23:55	Ramkumar Chinchani:	is there a priority list for these tests?
ecosystem tooling may work just fine even with some failing tests.
00:24:17	Ramkumar Chinchani:	but still would like to know when the tests fail.
00:27:19	Jory Burson:	lololol
00:27:24	Shaon Hossain:	Just curious, how are you testing sha512 blobs here?
00:36:29	Ramkumar Chinchani:	keep tests simple?
00:37:03	Sajay Antony:	Interested to see how the manifest push for 512 turns out. NTD folks. Good stuff Brandon. Thank you.
00:37:32	Ramkumar Chinchani:	olareg is the only registry that is happy currently?
00:38:10	Ramkumar Chinchani:	is there a priority list for these tests?
ecosystem tooling may work just fine even with some failing tests.
00:38:31	Tianon:	I had some minor patches to https://pkg.go.dev/cuelabs.dev/go/oci/ociregistry/ocimem that had it happy for a while, but then Brandon kept adding more tests and broke it again in ways that were harder to fix 😂
00:39:22	Ramkumar Chinchani:	Worry is we are focusing only on the server side. What if clients break when we fix the registry this way.
00:40:06	Ramkumar Chinchani:	zot has client tests, so we will know soon enough
00:40:24	Ramkumar Chinchani:	all of the above
00:41:36	Ramkumar Chinchani:	baby steps
00:44:56	Jory Burson:	Get it together Jeff
00:45:04	Jory Burson:	jk
00:50:06	Brandon Mitchell:	uses: sudo-bmitch/distribution-spec@pr-conformance-v2
00:51:01	Tianon:	Replying to "uses: sudo-bmitch/di..." Brandon's GitHub username makes this look spicier than it is 😂
00:52:01	Jory Burson:	BLOGG
00:52:04	Shaon Hossain:	Replying to "uses: sudo-bmitch/di..." 🎉
00:52:09	Ramkumar Chinchani:	unleash hell
00:52:12	Jory Burson:	Web log
00:55:08	Ramkumar Chinchani:	version the GH action

## March 12, 2026

**Recording**: https://youtu.be/52BtHhyMWRM

### Attendees:

- Brandon Mitchell
- Derek McGowan
- Brian Goff
- Samuel Karp
- Tianon (joined late)
- Jeff Carter (joined late)

### Actionable Agenda Items:

None.

### Presentation/Discussion Agenda Items:

- Packaging images with different layer media types with a platform.OS.Feature descriptor: <https://github.com/containerd/platforms/pull/16>
- Conformance v2 progress: <https://github.com/opencontainers/distribution-spec/pull/588>
- Reviewing 416 on out-of-order chunked data in put: <https://github.com/opencontainers/distribution-spec/pull/593>
- Reviewing pushing tags with a digest: <https://github.com/opencontainers/distribution-spec/pull/600>

### Notes:

Notes from the zoom chat:

00:13:39	Brian Goff:	Want "docker build" to output erofs :)
Uphill battle trying to get people to want to spend time on erofs.
00:23:45	Derek McGowan:	https://github.com/dragonflyoss/nydus/issues/1692
00:24:00	Samuel Karp:	Maybe ECR should be compliant with the spec 😂
00:28:00	Brandon Mitchell:	https://github.com/regclient/regclient/blob/ee44fc8d6c28e8f749ccb0a220e58cf2118a1a31/types/platform/platform_test.go#L146

## March 5, 2026

**Recording**: https://youtu.be/jooGiKOjoZw

### Attendees:

- Jeff Carter
- Brian Goff
- Tianon
- Brandon Mitchell
- Shaon Hossain
- Sajay Antony
- Jory Burson
- Samuel Karp

### Actionable Agenda Items:

None.

### Presentation/Discussion Agenda Items:

- Push by digest with multiple tags support: <https://github.com/opencontainers/distribution-spec/pull/600>
  - Brandon will add to the new conformance test with a version-gate in the next few weeks.
  - Jeff will fix pushing to Docker Hub with a non-canonical digest algorithm.
- Upcoming events: <https://docs.google.com/spreadsheets/d/1SUF-qTBEY4_mV1ERgP_TM3VYidfZPp9boSsCs1nH4v0/edit?gid=0#gid=0>
  - Jory will check if anyone can make KubeCon Japan
  - Brandon and Sam will try to make KubeCon US
- TOB meeting topics:
  - <https://github.com/opencontainers/tob/issues/154>
  - <https://github.com/opencontainers/tob/issues/155>
  - <https://github.com/opencontainers/tob/issues/151>

### Notes:

Notes from the zoom chat:

00:04:53	Brian Goff:	What is this? MUST support pushing 5 times at once, and SHOULD NOT set an upper limit
00:09:48	Brandon Mitchell:	For folks just joining, we don't have much of an agenda today, so add anything you'd like to talk about.
00:11:03	Tianon:	"trouble, right here in river city"
00:11:28	Jory Burson:	I think P stands for Party
00:11:49	Tianon:	Replying to ""trouble, right here..." https://www.imdb.com/title/tt0056262/
00:12:54	Jeff Carter:	Replying to "What is this? MUST ..." 5 tags 🤦
00:17:57	Jory Burson:	Yay!
00:30:00	Sajay Antony:	Thanks for organizing the meeting Jory.
00:30:58	Brandon Mitchell:	https://github.com/opencontainers/tob/issues/151
00:31:00	Sajay Antony:	Thank you all. NTD for another meeting.
00:32:11	Brian Goff:	NTD folks.
00:32:23	Brian Goff:	Have a great rest of your week.
00:32:44	Tianon:	"one container to open them all"
00:40:45	Samuel Karp:	only on festivus
00:42:41	Tianon:	I'm impressed that Brandon read the IRC logs - makes me feel even better about making sure we preserve them

## February 26, 2026

**Recording**: https://youtu.be/4YNhV8P_sn4

### Attendees:

- Brandon Mitchell
- Tianon
- Brian Goff
- Jory Burson
- Jeff Carter
- Sajay Antony
- Derek McGowan
- Ramkumar Chinchani
- Syed Ahmed
- _add yourself_

### Actionable Agenda Items:

- Review needed for making Docker-Content-Digest non-optional: <https://github.com/opencontainers/distribution-spec/pull/595>

### Presentation/Discussion Agenda Items:

- Pushing multiple tags: <https://github.com/opencontainers/distribution-spec/pull/600>
- Blob upload proof of ownership: <https://groups.google.com/a/opencontainers.org/g/dev/c/DEseqbBsXeE>

### Notes:

Notes from the zoom chat:

00:09:18	Ramkumar Chinchani:	how often does this requirement come up?
00:09:36	Ramkumar Chinchani:	need to push multiple tags for same manifest?
00:10:26	Ramkumar Chinchani:	golang 1.25.x, 1.25, latest for every 1.25.x
00:10:51	Brandon Mitchell:	^ that's the common use case (plus a non-canonical digest + tag)
00:13:53	Derek McGowan:	Busy busy 😀
00:22:57	Ramkumar Chinchani:	AI model turf
00:23:51	Ramkumar Chinchani:	storage community needs to implement dist spec
00:24:40	Brian Goff (@cpuguy83):	If I can't put it on my fat32 formaatted disk I don't want it.
00:25:58	Ramkumar Chinchani:	currently dist spec is beginning to chew on storage thingies
00:26:40	Sajay Antony:	Thanks for the stickers.
00:27:30	Sajay Antony:	I’d ask for the larger logo only sticker. Those were nice.
00:27:34	Syed Ahmed:	I have one PR pending approval https://github.com/opencontainers/distribution-spec/pull/595

## February 19, 2026

**Recording**: https://youtu.be/KOf2bj0sbMk

### Attendees:

- Brandon Mitchell
- Tianon
- Shaon Hossain
- Samuel Karp
- Brian Goff
- Sajay Antony

### Actionable Agenda Items:

- Review for irc meeting minutes: <https://github.com/opencontainers/.github/pull/71>
- distribution-spec blob put with invalid range: <https://github.com/opencontainers/distribution-spec/pull/593>
- Docker-Content-Digest header: <https://github.com/opencontainers/distribution-spec/pull/595>

### Presentation/Discussion Agenda Items:

- Updates from Jory:
  - Likely regrets from Jory unless she can dial in from the road
  - Stickers on the way to interested TOB Members
  - There is a new poll out for a meeting date/time to accomodate more TOB Members. Agenda to be proposed on email thread.
- image-spec empty config: <https://github.com/opencontainers/image-spec/pull/1309>
- Progress of supporting other digest algorithms:
  - issue: <https://github.com/opencontainers/distribution-spec/issues/494>
  - Proposal for a header: <https://github.com/opencontainers/distribution-spec/pull/543>
  - Proposal to push multiple tags: <https://github.com/opencontainers/distribution-spec/issues/591>
  - Blocking effort to rework conformance tests: <https://github.com/opencontainers/distribution-spec/pull/588>
  - Next step in conformance test rewrite is to adjust <https://conformance.opencontainers.org> web page for different categories (API and data types), then GHA jobs need to be reworked.

### Notes:

Notes from the zoom chat:

00:08:24	Brian Goff (@cpuguy83):	https://github.com/project-dalec/dalec/blob/f5516996a8426f612d14d4e55650570ff2895c3c/docs/spec.schema.json#L99-L102
00:22:47	Samuel Karp:	https://communityinviter.com/apps/opencontainers/join-the-oci-community

## February 12, 2026

**Recording**: https://youtu.be/8-X_xurTJoc

### Attendees:

- Brandon Mitchell
- Samuel Karp
- Tianon
- Brian Goff
- Jeff Carter
- Sajay Antony
- Jory Burson

### Actionable Agenda Items:

- TOB held "simple majority" vote (5/8 present and voting in the affirmative) to have a TOB meeting

### Presentation/Discussion Agenda Items:

- TOB:
  - Election results: <https://github.com/opencontainers/tob/issues/148>
  - Seat count: <https://github.com/opencontainers/tob/issues/155>
- image.base.source annotation: <https://github.com/opencontainers/image-spec/issues/1308>

### Notes:

Notes from the zoom chat:

00:03:18	Tianon:	This Charter may be amended by a two thirds vote of the Technical Oversight Board
00:03:30	Tianon:	Replying to "This Charter may be ..." this one's definitely open to interpretation 😂
00:06:30	Jory Burson:	hello
00:06:33	Jory Burson:	I’m alive
00:07:20	Sajay Antony:	Replying to "I’m alive" Glad to have you back Jory.
00:08:58	Tianon:	hey, 5/8 TOB members here isn't too bad!  I'm impressed 🫶
00:13:12	Tianon:	The prefix  org.opencontainers  is reserved for keys defined in Open Container Initiative (OCI) specifications and MUST NOT be used by other specifications and extensions.
00:16:04	Jory Burson:	Monument to your Greatness
00:16:52	Sajay Antony:	manifest embedded blobs test eh.
00:22:15	Tianon:	https://oci.dag.dev/?image=tianon/test:eeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeee ref https://iliana.fyi/blog/e98e/ (related to Brandon's "aaaaaa")
00:22:41	Tianon:	Replying to "https://oci.dag.dev/..." max length on the tag too, because of course it is
00:27:22	Sajay Antony:	We love it either way.

## February 5, 2026

**Recording**: https://youtu.be/leBTsXJhkTI

### Attendees:

- Samuel Karp
- Jeff Carter
- Tianon
- Brandon Mitchell
- Sajay Antony
- Ramkumar Chinchani
- Shaon Hossain
- Syed Ahmed

### Actionable Agenda Items:

- distribution-spec blob put with invalid range: <https://github.com/opencontainers/distribution-spec/pull/593>
- Docker-Content-Digest header: <https://github.com/opencontainers/distribution-spec/pull/595>

### Presentation/Discussion Agenda Items:

- image-spec platforms: <https://github.com/opencontainers/image-spec/pull/1305>
- Licensing headers: <https://github.com/opencontainers/tob/issues/151>
- LF needed:
  - TOB election status: <https://github.com/opencontainers/tob/issues/148>

### Notes:

Notes from the zoom chat:

00:09:28	Brandon Mitchell:	https://github.com/opencontainers/image-spec/pull/1305
00:11:02	Sajay Antony:	Replying to "https://github.com/o..." +1 on your response
00:11:33	Tianon:	I should probably footnote that comment with the fact that for all of my personal builds of anything containerd-adjacent, I patch that normalization code to be explicit about v8 for arm64 because implicit values suck, especially when they're embedded in an image
00:12:33	Tianon:	https://github.com/containerd/platforms/blob/2e51fd9435bd985e1753954b24f4b0453f4e4767/database.go#L76

## January 29, 2026

**Recording**: https://youtu.be/XEFNm7yyoAY

### Attendees:

- Brandon Mitchell
- Tianon
- Syed Ahmed
- Derek McGowan
- Jeff Carter
- Samuel Karp
- Brian Goff
- Shaon Hossian
- Sajay Antony

### Actionable Agenda Items:

- Review needed to archive minutes: <https://github.com/opencontainers/.github/pull/68>
- distribution-spec cancel endpoint: <https://github.com/opencontainers/distribution-spec/pull/594>
- distribution-spec blob put with invalid range: <https://github.com/opencontainers/distribution-spec/pull/593>

### Presentation/Discussion Agenda Items:

- Docker-Content-Digest header:
  - <https://github.com/opencontainers/distribution-spec/pull/595>
  - Context: <https://github.com/opencontainers/distribution-spec/pull/543#discussion_r2693119425>
- LF needed:
  - TOB election status: <https://github.com/opencontainers/tob/issues/148>
  - Licensing headers are inconsistent: <https://github.com/opencontainers/tob/issues/151>

### Notes:

Notes from the zoom chat:

00:07:41	Shaon Hossain:	+1 calendar year
00:10:45	Tianon:	I'd probably say "reasonably" instead of "safely" but that's some very fine hair splitting
00:11:18	Sajay Antony:	Do we say anywhere its "algo:digest" ?
00:11:27	Sajay Antony:	or just digest
00:12:25	Tianon:	Replying to "Do we say anywhere i..." https://github.com/opencontainers/image-spec/blob/v1.1.1/descriptor.md#digests (not sure if the dist-spec references this explicitly, but if not, it probably should)
00:14:08	Sajay Antony:	Replying to "Do we say anywhere i..." Great there is a big header "Digests" 🙂
00:14:45	Tianon:	Replying to "Do we say anywhere i..." - **Digest**: a unique identifier created from a cryptographic hash of a Blob's content. Digests are defined under the OCI Image Spec <sup>[apdx-3](#appendix)</sup>
00:14:48	Tianon:	Replying to "Do we say anywhere i..." in the dist-spec
00:15:15	Tianon:	Replying to "Do we say anywhere i..." and: | apdx-3 | [OCI Image Spec - digests](https://github.com/opencontainers/image-spec/blob/v1.0.1/descriptor.md#digests) | Description of digests, defined by the OCI Image Spec |
00:16:18	Brian Goff (@cpuguy83):	If it compiles the first time then worry.
00:20:26	Sajay Antony:	Good day folks

## January 22, 2026

**Recording**: https://youtu.be/36OCFqQQj_o

### Attendees:

- Brandon Mitchell
- Mike Brown
- Tianon
- Jeff Carter
- Syed Ahmed
- Brian Goff
- Ramkumar Chinchani
- Sajay Antony
- Shaon Hossain

### Actionable Agenda Items:

None.

### Presentation/Discussion Agenda Items:

- Docker-Content-Digest header:
  - <https://github.com/opencontainers/distribution-spec/pull/595>
  - Context: <https://github.com/opencontainers/distribution-spec/pull/543#discussion_r2693119425>
- Accept/Content-Type negotiation:
  - <https://github.com/opencontainers/distribution-spec/issues/596>
- TOB election status: <https://github.com/opencontainers/tob/issues/148>
- Licensing headers are inconsistent: <https://github.com/opencontainers/distribution-spec/pull/589#issuecomment-3774778393>

### Notes:

Notes from the zoom chat:

00:06:44	Ramkumar Chinchani:	MUST - pay attention, ignore everything else
00:26:52	Ramkumar Chinchani:	Any trademark issues with Docker-* strings? past, present and future? or was that part of the donation/open-sourcing?
00:32:48	Brian Goff (@cpuguy83):	Oh wow, I never realized that.
00:33:13	Tianon:	Replying to "Oh wow, I never real..." only ever bumped into it on accident, never on purpose lol (but it was a "compatibility" feature)
00:33:36	Brian Goff (@cpuguy83):	Replying to "Oh wow, I never real..." I remember the v1 manifest thing being the default return and you had to ask for v2... is that this?
00:34:07	Brian Goff (@cpuguy83):	Replying to "Oh wow, I never real..." Ah yeah, that's this.
00:34:18	Tianon:	Replying to "Oh wow, I never real..." part of this - the other half was unwrapping an index if your Accept header wasn't big enough
00:34:19	Brian Goff (@cpuguy83):	Replying to "Oh wow, I never real..." When I hit that I was like wtf is going on.
00:41:55	Tianon:	https://github.com/tianon/oci-schema1
00:45:57	Sajay Antony:	Folks need to drop for another call.
00:48:58	Jeff Carter:	I’ll ask Claude to summarize it for me
00:54:32	Shaon Hossain:	We want some snow! Ski resorts are suffering from lack of snow this year
00:54:39	Shaon Hossain:	(In Seattle)
00:54:53	Tianon:	Canada? "Northern USA" 😂
00:55:06	Brian Goff (@cpuguy83):	I've never seen even 1ft, I don't think.
00:55:14	Tianon:	Replying to "Canada? "Northern US..." "that's bait!"

## January 15, 2026

**Recording**: https://youtu.be/HOmrzEpH-jk

### Attendees:

- Tianon
- Brandon Mitchell
- Shaon Hossain
- Syed Ahmed
- Brian Goff
- Samuel Karp
- Ramkumar Chinchani
- James Kolb
- Jeff Carter
- Mike Brown

### Actionable Agenda Items:

- Ready for review:
  - distribution-spec blob put with an invalid range: <https://github.com/opencontainers/distribution-spec/pull/593>
  - distribution-spec blob upload cancel endpoint: <https://github.com/opencontainers/distribution-spec/pull/594>

### Presentation/Discussion Agenda Items:

- TOB election status, need LF
- Are licensing headers needed: <https://github.com/opencontainers/distribution-spec/pull/589>, need LF
- There is no way to add referrers to tagged content in a backwards compatible way that also supports alternative digests
  - <https://github.com/opencontainers/distribution-spec/pull/543#discussion_r2693119425>
  - The distribution project no longer depends on the Accept header, returning the manifest even if no Accept header is provided.
  - The content negotiation doc is being ignored: <https://github.com/opencontainers/distribution-spec/blob/v1.1.1/content-negotiation.md>
  - OCI could require RFC 9530: <https://datatracker.ietf.org/doc/rfc9530/>
  - Reviewed the removal of the OCI headers in <https://github.com/opencontainers/distribution-spec/issues/207> and <https://github.com/opencontainers/distribution-spec/pull/208>
  - Syed planning to open a PR for better supporting a digest header

### Notes:

Notes from the zoom chat:

00:06:22	Ramkumar Chinchani:	GH enabled the "Agents" tab
00:14:14	Ramkumar Chinchani:	https://github.com/opencontainers/distribution-spec/issues/409
00:17:46	Ramkumar Chinchani:	security = image protected by signatures?
00:23:03	Jeff Carter:	https://github.com/opencontainers/distribution-spec/pull/208
00:49:36	Brian Goff (@cpuguy83):	Let me sneek in some blake3 digests just to mess things up.
00:49:50	Mike Brown:	🙂
00:50:40	Mike Brown:	panic will arrive soon.. see quantum hardware release schedules
00:51:18	Brian Goff (@cpuguy83):	https://datatracker.ietf.org/doc/rfc9530/
00:52:12	Tianon:	Replying to "https://datatracker...." that's adorable
00:52:42	Tianon:	Replying to "https://datatracker...."
   ```
   Content-Digest: \
     sha-256=:d435Qo+nKZ+gLcUHn7GQtQ72hiBVAgqoLsZnZPiTGPk=:,\
     sha-512=:YMAam51Jz/jOATT6/zvHrLVgOYTGFy1d6GJiOHTohq4yP+pgk4vf2aCs\
     yRZOtw8MjkM7iw7yZ/WkppmM44T3qg==:
   ```
00:52:45	Tianon:	Replying to "https://datatracker...." I love it
00:53:39	Ramkumar Chinchani:	Replying to "panic will arrive so..." asymmetric crypto most affected. hashes and symmetric crypto mostly fine.
00:54:29	Mike Brown:	Replying to "https://datatracker...." this
00:55:59	Ramkumar Chinchani:	FIPS-140 excludes blake3
00:57:53	James Kolb:	https://pulp.plan.io/issues/4646

## January 8, 2026

**Recording**: https://youtu.be/r13LWCA6FKA

### Attendees:

- Tianon
- Alexander Kanevskiy
- Brandon Mitchell
- Derek McGowan
- Shaon Hossain
- Samuel Karp
- Jeff Carter
- Brian Goff
- Sajay Antony
- Brady Pratt
- Syed Ahmed

### Actionable Agenda Items:

- PR still needed for blob PUT with an invalid range: <https://github.com/opencontainers/distribution-spec/issues/590> (assigned to Brandon)
- Review for PR 1296 <https://github.com/opencontainers/runtime-spec/pull/1296> (all suggestions and requested changes addressed)

### Presentation/Discussion Agenda Items:

- `.wh.` file handling: <https://github.com/opencontainers/image-spec/issues/1301>
- Are licensing headers needed: <https://github.com/opencontainers/distribution-spec/pull/589>
- Pushing multiple tags: <https://github.com/opencontainers/distribution-spec/issues/591>
- TOB election status

### Notes:

Notes from the zoom chat:

00:01:30	Tianon:	just had a power blip which hopefully wasn't a harbinger of outages to come lol
00:12:09	Brandon Mitchell:	Sam needs a new mic.
00:12:18	Samuel Karp:	do I sound like a robot?
00:12:23	Brandon Mitchell:	Yup
00:12:45	Samuel Karp:	maybe a zoom thing? this is using my normal mic...
00:14:34	Brian Goff (@cpuguy83):	Its all static, have you tried replugging?
00:17:24	Brian Goff (@cpuguy83):	*on purpose*
00:19:44	Samuel Karp:	it's usb, so I won't try until I drop this call because I don't want the device to disappear while I'm here
00:20:33	Derek McGowan:	I think containerd will hit this case https://github.com/containerd/containerd/blob/main/pkg/archive/tar.go#L813
00:28:25	Tianon:	"copyright of theseus" is a cursed thought I've had related to this discussion and I'm thrilled to see it's nowhere near original: https://opensource.stackexchange.com/a/4347/40765
00:34:32	Samuel Karp:	https://opensource.google/documentation/reference/releasing/authors?hl=en
00:44:17	Sajay Antony:	Did you have some rough number of max tags you want to support per put? Don't want different implementors to have different limits.
00:47:49	Brian Goff (@cpuguy83):	"If you want a guarentee use digests" -- I keep telling people that, but they won't do it.
00:47:50	Tianon:	Replying to "Did you have some ro..." maybe URL path less than 2000 characters? 😂 (https://stackoverflow.com/a/417184/433558 is cute and I think we've discussed this problem in OCI before but maybe I'm mis-remembering)
00:48:23	Tianon:	Replying to ""If you want a guare..." "if you want immutable images, that's literally what pull-by-digest is designed for" is a set of words I retype on a regular basis
00:49:40	Brian Goff (@cpuguy83):	Oh, Tianon will try it, I'm sure.
00:50:10	Tianon:	10 lmao
00:50:23	Tianon:	Replying to "10 lmao" low enough that it's almost not worth doing the feature

## January 1, 2026

Canceled for New Years Day.
