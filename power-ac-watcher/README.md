# power-ac-watcher

A user-level systemd service that automatically adjusts power settings when AC power is connected or disconnected.

## Features

When AC power is connected:
- Sets the power profile to `balanced`.
- Enables Caelestia's idle inhibitor.

When AC power is disconnected:
- Sets the power profile to `power-saver`.
- Disables Caelestia's idle inhibitor.

The watcher applies the current power state when it starts and reacts to subsequent AC adapter events. It does not continually override manual changes.

## Requirements

- Bash
- systemd user services
- `udevadm`
- `power-profiles-daemon` (`powerprofilesctl`)
- Caelestia shell CLI

The service expects the AC adapter to be exposed at `/sys/class/power_supply/AC/online`.

## Installation

```bash
mkdir -p ~/.local/bin ~/.config/systemd/user
cp power-ac-watcher/power-ac-watcher ~/.local/bin/
cp power-ac-watcher/power-ac-watcher.service ~/.config/systemd/user/
chmod +x ~/.local/bin/power-ac-watcher
systemctl --user daemon-reload
systemctl --user enable --now power-ac-watcher.service
```

## Usage

Check the service:
```bash
systemctl --user status power-ac-watcher.service
```

View its logs:
```bash
journalctl --user -u power-ac-watcher.service
```

Stop or disable it:
```bash
systemctl --user disable --now power-ac-watcher.service
```
