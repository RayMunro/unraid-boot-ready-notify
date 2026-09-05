# Boot Ready Notify

Sends a **Warning-level Unraid notification** once the server has completed Unraid's native `started` event and the Docker daemon is responsive.

The notification is sent through Unraid's own notification subsystem and is limited to one successful notification per OS boot.

Version 2026.09.02f also verifies its Plugin Manager registration and custom PNG icon metadata after Unraid completes the native install registration step.
