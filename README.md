# thinOS

A small, fast operating system for thin clients. It starts straight into a simple
desktop with a dock, a web browser and an email client, and connects to cloud desktops
(Workspaces / DaaS) when you need a full desktop session.

> **Status: early design.** Nothing to download yet. See [docs/design.md](docs/design.md)
> for what's planned and the [issues](../../issues) for what's being worked on.

## What it's for

- **Thin clients and old PCs** turned into secure, low-maintenance desktops.
- **Everyday work without a session:** browse the web and read email on the device itself.
- **Cloud desktops when you need them:** RDP and SPICE, over a built-in WireGuard VPN to
  reach private networks.

## Principles

- **Small and read-only.** Built on Alpine Linux. The system can't be changed while it runs,
  and nothing is kept on the device that matters if it's lost.
- **Safe updates.** Two copies of the system: an update goes to the spare, the device
  restarts into it, and falls back to the old one if it doesn't come up.
- **One clear desktop.** A dock along the bottom and only the apps a thin client needs.
- **Works on its own.** thinOS connects to any desktop service speaking its documented
  broker API, including [vBase](https://onecomet.co.nz) Workspaces, and to plain RDP hosts.

## Getting a USB stick (planned)

Releases will be written to a USB stick with
[vBase Imager](https://github.com/MSNFernando/vbase-imager), which checks the download and
verifies the stick after writing.

## Contributing

Contributions are welcome: see [CONTRIBUTING.md](CONTRIBUTING.md). Reports of which
thin-client models work (and which don't) are especially useful. Security issues: see
[SECURITY.md](SECURITY.md); please don't open public issues for them.

## Licence

Apache License 2.0: see [LICENSE](LICENSE) and [NOTICE](NOTICE). thinOS images contain
Alpine Linux packages and other software under their own licences; each release lists
them.
