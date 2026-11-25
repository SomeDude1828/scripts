# clean-downloads

A small script that automatically cleans up your Downloads directory.

## Features

- Deletes files older than seven days.
- Searches recursively through subdirectories.
- Removes empty directories afterward.
- Runs daily using a systemd user timer.
- Uses `xdg-user-dir` to locate the Downloads directory.

**Warning:** Deleted files are permanently removed. There is no recycle bin or recovery step.

## Requirements

- Bash
- `find`
- `xdg-user-dir` (usually provided by `xdg-user-dirs`)
- systemd user services

## Installation

```bash
mkdir -p ~/.local/bin ~/.config/systemd/user
cp clean-downloads/clean-downloads ~/.local/bin/
cp clean-downloads/clean-downloads.service clean-downloads/clean-downloads.timer ~/.config/systemd/user/
chmod +x ~/.local/bin/clean-downloads
systemctl --user daemon-reload
systemctl --user enable --now clean-downloads.timer
```

## Usage

Run manually with `clean-downloads`.

Check the timer with:

```bash
systemctl --user status clean-downloads.timer
systemctl --user list-timers clean-downloads.timer
```

The script uses file modification time (`mtime`), deleting files older than seven full 24-hour periods.
