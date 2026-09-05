# Boot Ready Notify

Sends a **Warning-level Unraid notification** once the server has completed
Unraid's native `started` event and the Docker daemon is responsive.

The notification is sent through Unraid's own notification subsystem and is
limited to one successful notification per OS boot.

Copyright © 2026 Ray Munro. Licensed under the [GNU GPLv3](LICENSE).

## Installation

**Via Community Applications:** search for "Boot Ready Notify" in the Apps
tab and click Install.

**Manually:** in the Unraid webGUI go to **Plugins → Install Plugin** and
paste:

```
https://raw.githubusercontent.com/RayMunro/unraid-boot-ready-notify/main/boot.ready.warning.plg
```

or from the terminal:

```bash
plugin install https://raw.githubusercontent.com/RayMunro/unraid-boot-ready-notify/main/boot.ready.warning.plg
```

Everything the plugin needs is written by the `.plg` itself, so nothing else
needs to be downloaded or copied by hand.

## Details

- Internal plugin ID: `boot.ready.warning`
- Canonical Unraid filename: `boot.ready.warning.plg`
- Notification severity: Warning
- Trigger: Unraid's native `started` event
- Docker readiness gate: `docker info` must succeed
- Custom icon installed at `/usr/local/emhttp/plugins/boot.ready.warning/images/boot.ready.warning.png`

Because Unraid runs a plugin's install payload *before* it copies/registers
the new `.plg`, this plugin runs a delayed post-install verification step
that confirms the PNG icon metadata and canonical registration afterward,
and moves aside any duplicate persistent definition for the same internal
plugin ID so an old copy can't be reinstalled on the next boot.

## Uninstall

From Settings → Plugins, remove "boot.ready.warning" normally, or run:

```bash
plugin remove boot.ready.warning.plg
```
