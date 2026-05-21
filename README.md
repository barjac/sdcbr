# sdcbr
# SD Card Backup and Restore

Backs up an SD card or Flash drive interactively as a compressed image.

Restores a previously backed up compressed image to a device large enough for the data.
The data and target device are compared and restore not started if the data is too large
for the target device in use. This means that data backed up from a 64GB SD card for example
may restore to a 32GB card if the original media was only half full.

The compression used is now zst but sdcbr is backward compatible with the earlier version
backups.

Suitable for backing up Raspberry Pi and similar operating system cards.

## Distro support

sdcbr detects the running distribution via `/etc/os-release` and automatically
selects the appropriate package manager for dependency checking and installation.

The following distributions are explicitly supported:

| Distribution | Package manager |
|---|---|
| Mageia | urpmi |
| Fedora (< 42) | dnf |
| Fedora (>= 42) | dnf5 |
| openSUSE Tumbleweed / Leap | zypper |
| Debian / Ubuntu / Linux Mint / LMDE | apt-get |
| Arch / Manjaro / Garuda / EndeavourOS and other Arch derivatives | pacman |
| PCLinuxOS | apt-get |
| Gentoo | emerge |

Distributions not in the above list but based on a recognised family (Debian,
Fedora/RHEL, SUSE, or Arch) will be detected via the `ID_LIKE` field in
`/etc/os-release` and handled with the appropriate package manager.

## Usage

Make the script executable:

```
chmod +x sdcbr
```

Run as root and follow the prompts:

```
sudo ./sdcbr
```

