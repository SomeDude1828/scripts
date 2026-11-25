# autoclick-toggle

A lightweight Bash autoclicker for Linux using `ydotool`.

## Features

- Toggle automatic clicking on and off with one command.
- Clicks approximately 50 times per second.
- Sends desktop notifications when started or stopped.
- Stores its process ID in the runtime directory.

## Requirements

- Bash
- `ydotool`
- `libnotify` (`notify-send`)

Make sure `ydotool` is configured and working on your system.

## Installation

```bash
mkdir -p ~/.local/bin
cp autoclick-toggle/autoclick-toggle ~/.local/bin/
chmod +x ~/.local/bin/autoclick-toggle