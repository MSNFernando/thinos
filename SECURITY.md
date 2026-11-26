# Security policy

## Reporting a vulnerability

Please report security problems **privately** through GitHub: on this repository, open
**Security → Report a vulnerability**. Don't open a public issue, pull request or
discussion about it.

Include what's affected (version or commit), how to reproduce it, and the impact as you
understand it. We'll acknowledge the report within a few days, keep you informed, and
credit you in the advisory if you'd like.

## Supported versions

thinOS hasn't had a release yet. Once it has, security fixes go to the latest release, and
devices update to it through the normal update channel.

## Update signing

Updates are signed, and devices refuse anything that isn't. The signing key is never
stored in this repository or in CI configuration; only tagged releases are signed.
