# Security

## Reporting Security Issues

When reporting a security issue, do not create an issue or file a pull
request on GitHub. Instead, disclose the issue responsibly by sending an email
to security@opencontainers.org (which is inhabited only by the maintainers of
the various OCI projects).

The maintainers take security seriously. If you discover a security issue,
please bring it to their attention right away!

## Disclosure Distribution List

This list is used to provide actionable information to multiple distribution vendors at once.
This list is not intended for individuals to find out about security issues.

### Embargo Policy

The information members receive on security-announce@opencontainers.org must not be made public, shared, nor even hinted at anywhere beyond the need-to-know within your specific team except with the list's explicit approval.
This holds true until the public disclosure date/time that was agreed upon by the list.
Members of the list and others may not use the information for anything other than getting the issue fixed for your respective distribution's users.

Before any information from the list is shared with respective members of your team required to fix said issue, they must agree to the same terms and only find out information on a need-to-know basis.

In the unfortunate event you share the information beyond what is allowed by this policy, you must urgently inform the security@opencontainers.org mailing list of exactly what information leaked and to whom.
A retrospective will take place after the leak so we can assess how to not make the same mistake in the future.

If you continue to leak information and break the policy outlined here, you will be removed from the list.

### Contributing Back

This is a team effort. As a member of the list you must carry some water. This
could be in the form of the following:

#### Technical

- Review and/or test the proposed patches and point out potential issues with
  them (such as incomplete fixes for the originally reported issues, additional
  issues you might notice, and newly introduced bugs), and inform the list of the
  work done even if no issues were encountered.

#### Administrative

- Help draft emails to the public disclosure mailing list.
- Help with release notes.

### Membership Criteria

To be eligible for the security-announce@opencontainers.org mailing list, your
distribution should:

1. Have an actively monitored security email alias for our project.
1. Have a user base not limited to your own organization.
1. Have a publicly verifiable track record up to present day of fixing security
   issues.
1. Not be a downstream or rebuild of another distribution.
1. Accept the [Embargo Policy](#embargo-policy) that is outlined above.
1. Be willing to [contribute back](#contributing-back) as outlined above.
1. Have someone already on the list vouch for the person requesting membership
   on behalf of your distribution.

#### Removal

If your distribution stops meeting one or more of these criteria
after joining the list then you will be unsubscribed.

### Requesting to Join

New membership requests are sent to security@opencontainers.org

In the body of your request please specify how you qualify and fulfill each
criterion listed in [Membership Criteria](#membership-criteria).

Here is a psuedo example:

```email
To: security@opencontainers.org
Subject: Seven-Corp Membership to security-announce@opencontainers.org

Below are each criterion and why I think we, Seven-Corp, qualify.

> 0. Have an actively monitored security alias email for our project.

Yes, please subscribe security-response-team@example.com to the distributor's
announce list.

> 1. Have a user base not limited to your own organization.

Our user base spans of the extensive "Seven" community. We have a slack and
GitHub repos and mailing lists where the community hangs out. [links]

> 2. Have a publicly verifiable track record up to present day of fixing security
   issues.

We announce on our blog all upstream patches we apply to "Seven." [link to blog
posts]

> 3. Not be a downstream or rebuild of another distribution.

This does not apply, "Seven" is a unique snowflake distribution.

> 4. Accept the Embargo Policy that is outlined above.

We accept.

> 5. Be willing to contribute back as outlined above.

We are definitely willing to help!

> 6. Be willing and able to handle PGP-encrypted email.

Yes.

> 7. Have someone already on the list vouch for the person requesting membership
   on behalf of your distribution.

CrashOverride will vouch for Acidburn joining the list on behalf of the "Seven"
distribution.

```

### Templates

These are templates used in correspondance on behalf of this security function.

```email
Welcome,

You (or your list) have been identified as a contact for receiving security announcements from the Open Containers Initiative (OCI).
This list (security-announce@opencontainers.org) is used to provide actionable information to multiple distribution vendors at once.
This list is not intended for individuals to find out about security issues.
You can find more information here: https://github.com/opencontainers/org/blob/master/SECURITY.md

OCI is largely a specs organization and hosts a few software projects as well, notably `runc`.

If you feel your inclusion on this list is in error, please notify "security@opencontainers.org" for removal.

Thanks,
Vincent Batts
```
