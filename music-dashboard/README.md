# music-dashboard

A terminal-based music dashboard for Hyprland, using Kitty, MPD and several terminal visualizers.

## Features

- Opens a collection of music-related terminal windows.
- Arranges and resizes them automatically using Hyprland.
- Starts MPD and the MPD-to-MPRIS bridge if they aren't already running.
- Supports switching to predefined workspaces before launching.
- Provides a companion script to close all dashboard windows.

## Components

- Cava — audio visualizer
- lyrics — MPD lyrics display
- lavat — audio visualizer
- unimatrix — terminal animation
- tty-clock — terminal clock
- ncmpcpp — MPD music player
- pipes.sh — terminal animation
- Fish — small terminal window

## Requirements

- Hyprland
- Kitty
- Bash
- jq
- MPD
- mpd-mpris
- Cava
- lyrics
- lavat
- unimatrix
- ncmpcpp
- tty-clock
- pipes.sh
- Fish

## Installation

From the repository root:

```bash
mkdir -p ~/.local/bin
cp music-dashboard/music-start ~/.local/bin/
cp music-dashboard/music-close ~/.local/bin/
chmod +x ~/.local/bin/music-start ~/.local/bin/music-close
```

## Usage

Start the dashboard:

```bash
music-start
```

Optional workspace arguments:

| Argument | Workspace |
|---|---|
| `c` | Communication |
| `m` | Music |
| `d` | Any special workspace |
| `r` | Todo |
| `2` | WS2 |

For example:

```bash
music-start m
```

Close the dashboard:

```bash
music-close
```

## Notes

Window sizes and positions are configured for a specific screen layout and may need adjusting on other displays.
