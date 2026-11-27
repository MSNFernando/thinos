# thinOS design

Status: early design (2026-11). Decisions so far, and what's still open.

## Decided

- **Base:** Alpine Linux. Small, simple, and quick to patch.
- **System layout:** read-only root, two copies of the system (A/B). An update is
  written to the spare copy, the device restarts into it and marks it good once it's up;
  if it doesn't come up, the device falls back to the previous copy. Settings and
  user data live on a separate small partition.
- **Desktop:** a kiosk-style Wayland compositor running thinOS's own shell, with
  - a **dock along the bottom** (apps, running windows, network, sound, clock, power);
  - sign-in, and settings for Wi-Fi, displays, sound, keyboard and time zone.
- **Built-in apps:**
  - a **web browser**;
  - an **email client**;
  - a **Workspaces client** for cloud desktops (RDP through FreeRDP; SPICE);
  - **WireGuard**, to reach private networks.
  Browsing and email work without starting a desktop session.
- **Writing a stick:** releases are images written with vBase Imager.
- **Licence:** Apache 2.0; public development on GitHub.

## Editions

Two builds from the same base, system layout and update mechanism:

- **thinOS Desktop:** the full desktop: the dock, the web browser (Chromium), the email
  client (Thunderbird), settings, the Workspaces client and WireGuard.
- **thinOS Connect:** the smallest build: sign-in, network and display settings,
  WireGuard and the Workspaces client (RDP / SPICE) only. Starts straight into a desktop
  session; for kiosks, shared desks and low-end hardware.

First choices (2026-11): Chromium, Thunderbird, and Qt/QML for thinOS's own shell, since
compatibility matters more than size on hardware with 4 GB of memory or more. Connect
leaves the browser and email client out.

## Wallpapers

18 photographs from Unsplash (owner's choice, 2026-11-27) in `wallpapers/`, at 3840×2160 and
1920×1080 (WebP), with `wallpapers.json` (titles, photographers, sources) for the picker in
Settings, which credits the photographer ("Photo: Name, Unsplash"). Default: *Ember light*. They
stay under the Unsplash License, not Apache 2.0 (`wallpapers/LICENSE.md`). The same set is
offered in vBase: the console's sign-in page and a wallpaper choice for Windows VMs.

## Open questions

- Compositor: `cage` (one full-screen app) with our shell as that app, or a small
  compositor of our own (e.g. on wlroots) so the dock and app windows are managed
  together.
- Updates: a delta format or whole images; where the update channel is hosted.
- Hardware to support first: a few common thin-client models (x86_64), then ARM64.
- Device management: enrolment with a vBase tenant, settings pushed from the console.

## Things to check early

Wi-Fi firmware and graphics on real thin clients; musl compatibility of the apps chosen;
USB redirection, printing and smart cards in desktop sessions; several monitors.
