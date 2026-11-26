# Contributing to thinOS

Thanks for helping. Bug reports, hardware reports, documentation and code are all welcome.

## Before you start

- **Bugs and hardware reports:** open an issue. For hardware, give the make and model, the
  CPU, the graphics and Wi-Fi chips (`lspci -nn`, `lsusb`), and what works and what doesn't.
- **Bigger changes:** open an issue first to agree the approach, so your work isn't wasted.
- **Security issues:** never in a public issue. See [SECURITY.md](SECURITY.md).

## Pull requests

- One change per pull request, with a clear description of what and why.
- Keep the system small: a new package needs a reason, and its size in the description.
- Builds and checks must pass in CI.

## Sign your commits off (DCO)

thinOS uses the [Developer Certificate of Origin](https://developercertificate.org/)
instead of a contributor agreement. By adding a `Signed-off-by` line to each commit you
confirm you wrote the change, or otherwise have the right to submit it under the
project's licence (Apache 2.0):

```
git commit -s -m "Dock: show running apps"
```

which adds `Signed-off-by: Your Name <you@example.com>` using your git identity.

## Licence

By contributing, you agree that your contributions are licensed under the
[Apache License 2.0](LICENSE).
