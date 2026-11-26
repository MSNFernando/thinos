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

## Open questions

- Compositor: `cage` (one full-screen app) with our shell as that app, or a small
  compositor of our own (e.g. on wlroots) so the dock and app windows are managed
  together.
- Shell toolkit: Qt/QML (as vBase Imager uses) or GTK.
- Browser: Chromium (broad site compatibility; large) or a WebKit-based browser (small).
- Email client: Thunderbird (complete; large) or something lighter.
- Updates: a delta format or whole images; where the update channel is hosted.
- Hardware to support first: a few common thin-client models (x86_64), then ARM64.
- Device management: enrolment with a vBase tenant, settings pushed from the console.

## Things to check early

Wi-Fi firmware and graphics on real thin clients; musl compatibility of the apps chosen;
USB redirection, printing and smart cards in desktop sessions; several monitors.
