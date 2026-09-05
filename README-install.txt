Boot Ready Notify 2026.09.02f
=============================

Internal plugin ID: boot.ready.warning
Canonical Unraid filename: boot.ready.warning.plg
Notification severity: Warning
Trigger: Unraid native started event
Docker readiness gate: docker info

The custom icon is installed at:
  /usr/local/emhttp/plugins/boot.ready.warning/images/boot.ready.warning.png

The persistent plugin definition is:
  /boot/config/plugins/boot.ready.warning.plg

The Plugin Manager registration is:
  /var/log/plugins/boot.ready.warning.plg -> /boot/config/plugins/boot.ready.warning.plg

2026.09.02f adds a delayed post-install verification step. Unraid executes a
plugin's install payload before it copies/registers the new .plg, so the
verification runs just afterwards and confirms the PNG icon metadata and
canonical registration. It also moves duplicate persistent definitions for the
same internal plugin to /boot/config/plugins-stale so an old copy cannot be
reinstalled at the next boot.

IMPORTANT WHEN DOWNLOADING ON A MAC:
The distributed installer has a versioned filename so repeated browser downloads
cannot silently leave you copying an older unversioned file. Copy it to Unraid
while renaming the destination to /tmp/boot.ready.warning.plg.
