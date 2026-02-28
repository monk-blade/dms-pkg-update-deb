# DMS Package Updates

A [DankMaterialShell](https://github.com/AvengeMedia/DankMaterialShell) widget that checks for pending **system package** updates (**APT** or **DNF**) and **Flatpak** updates, then lets you run them directly from the bar.

![Screenshot](https://raw.githubusercontent.com/rahulmysore23/dms-pkg-update/main/screenshot.png)

## Features

- Shows total pending update count in the bar pill
- Lists available system package updates (APT/DNF) with version numbers
- Lists available Flatpak app updates with remote origin
- **Update Packages** button — opens a terminal and runs:
	- `sudo apt update && sudo apt upgrade -y` (APT backend)
	- `sudo dnf upgrade -y` (DNF backend)
- **Update Flatpak** button — opens a terminal and runs `flatpak update -y`
- Configurable refresh interval
- Configurable terminal application
- Configurable package backend mode (`auto`, `apt`, `dnf`)

## Installation

### From Plugin Registry (Recommended)

```bash
dms plugins install pkgUpdate
# or use the Plugins tab in DMS Settings
```

### Manual

```bash
cp -r pkgUpdate ~/.config/DankMaterialShell/plugins/
```

Then enable the widget in the DMS Plugins tab and add it to DankBar.

## Configuration

| Setting | Default | Description |
|---|---|---|
| Terminal Application | `alacritty` | Terminal used to run updates (`kitty`, `foot`, `ghostty`, etc.) |
| Refresh Interval | `60` min | How often to check for updates (5–240 min) |
| Package Backend | `auto` | System package backend: `auto` (prefer APT, fallback DNF), `apt`, or `dnf` |
| Show Flatpak Updates | `true` | Toggle Flatpak section on/off |

## Requirements

- One system package manager:
	- `apt` (Ubuntu/Debian-based systems)
	- `dnf` (Fedora/RHEL-based systems)
- `flatpak` (optional, can be disabled in settings)
- A terminal emulator that accepts `-e` to run a command

## License

MIT

