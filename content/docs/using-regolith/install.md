---
title: "Install"
linkTitle: "Install"
weight: 1
description: >
  Install Regolith
---

# Get Regolith 3.0

If you're upgrading from an earlier version of Regolith, you may be interested in reading [the release notes](/docs/reference/Releases/regolith-3.0-release-notes) and most specifically, the [migration guide](http://localhost:1313/docs/reference/Releases/regolith-3.0-release-notes/#migration-guide).

## Packages Specified at Install Time

In Regolith 3.0 it is now possible to select from multiple sessions (X11: `regolith-session-flashback`, Wayland: `regolith-session-sway`). Due to this, when installing Regolith 3.0 also specify one or both sessions that you wish to use. Additionally, it's now possible to specify the Regolith Look at install time, which saves a setup of having to configure it later.  Here is the recommended base install for X11 on Debian-based systems:

```console
sudo apt install regolith-desktop regolith-session-flashback regolith-look-lascaille
#                ^-- base package ^-- session                ^ -- look 
```

* For the session, you may chose one or both of: `regolith-session-flashback` (X11), `regolith-session-sway` (Wayland)
* For the look, you may chose *one* from any available look package:
```
regolith-look-ayu-dark
regolith-look-ayu-mirage
regolith-look-ayu
regolith-look-blackhole
regolith-look-default-loader
regolith-look-default
regolith-look-dracula
regolith-look-gruvbox
regolith-look-i3-default
regolith-look-lascaille
regolith-look-nevil
regolith-look-nord
regolith-look-solarized-dark
```

An an example and alternative to the recommendation above, here is the `apt` line to install the Sway session with the Nord Look:

```console
sudo apt install regolith-desktop regolith-session-sway regolith-look-nord
```

## Supported Operating Systems

Below are sections devoted to installing the Regolith Desktop on specific Linux-based operating systems.

### Ubuntu

{{< tabs "ubuntu-tabs" >}}
{{< tab "Ubuntu 23.04" >}}

Regolith can be installed as system packages.  This makes updating and removing easier and more consistent.  The following steps describe how
to configure your system to read packages from the Regolith package repository and install the desktop package.

1. Register the Regolith public key to your local `apt`:

   ```console
   wget -qO - https://regolith-desktop.org/regolith.key | \
   gpg --dearmor | sudo tee /usr/share/keyrings/regolith-archive-keyring.gpg > /dev/null
   ```

1. Add the repository URL to your local `apt`:

   ```console
   echo deb "[arch=amd64 signed-by=/usr/share/keyrings/regolith-archive-keyring.gpg] \
   https://regolith-desktop.org/release-3_0-ubuntu-lunar-amd64 lunar main" | \
   sudo tee /etc/apt/sources.list.d/regolith.list
   ```

1. Update `apt` and install Regolith

   ```console
   sudo apt update
   sudo apt install regolith-desktop regolith-session-flashback regolith-look-lascaille
   ```
1. System Restart

The login manager will need to be restarted for the new desktop session to be recognized. The easiest way of restarting it is to reboot your system.

{{< hint info >}}
Replace `amd64` with `arm64` in the two places in the above line to install on ARM-based systems.
{{< /hint >}}

{{< /tab >}}
{{< tab "Ubuntu 22.04" >}}

Regolith can be installed as system packages.  This makes updating and removing easier and more consistent.  The following steps (also available as a [downloadable script](/install-release-ubuntu-22.04-amd64.txt)) describe how
to configure your system to read packages from the Regolith package repository and install the desktop package.

1. Register the Regolith public key to your local `apt`:

   ```console
   wget -qO - https://regolith-desktop.org/regolith.key | \
   gpg --dearmor | sudo tee /usr/share/keyrings/regolith-archive-keyring.gpg > /dev/null
   ```

1. Add the repository URL to your local `apt`:

   ```console
   echo deb "[arch=amd64 signed-by=/usr/share/keyrings/regolith-archive-keyring.gpg] \
   https://regolith-desktop.org/release-3_0-ubuntu-jammy-amd64 jammy main" | \
   sudo tee /etc/apt/sources.list.d/regolith.list
   ```

1. Update `apt` and install Regolith

   ```console
   sudo apt update
   sudo apt install regolith-desktop regolith-session-flashback regolith-look-lascaille
   ```
1. System Restart

The login manager will need to be restarted for the new desktop session to be recognized. The easiest way of restarting it is to reboot your system.

{{< hint info >}}
Replace `amd64` with `arm64` in the two places in the above line to install on ARM-based systems.
{{< /hint >}}

{{< /tab >}}

{{< tab "Ubuntu 20.04" >}}

Regolith can be installed as system packages.  This makes updating and removing easier and more consistent.  The following steps (also available as a [downloadable script](/install-release-ubuntu-20.04-amd64.txt)) describe how
to configure your system to read packages from the Regolith package repository and install the desktop package.

1. Register the Regolith public key to your local `apt`:

   ```console
   wget -qO - https://regolith-desktop.org/regolith.key | sudo apt-key add -
   ```

1. Add the repository URL to your local `apt`:

   ```console
   echo deb "[arch=amd64] https://regolith-desktop.org/release-3_0-ubuntu-focal-amd64 focal main" | \
   sudo tee /etc/apt/sources.list.d/regolith.list
   ```

1. Update `apt` and install Regolith

   ```console
   sudo apt update
   sudo apt install regolith-desktop regolith-session-flashback regolith-look-lascaille
   ```

1. System Restart

The login manager will need to be restarted for the new desktop session to be recognized. The easiest way of restarting it is to reboot your system.

{{< hint info >}}
Replace `amd64` with `arm64` in the two places in the above line to install on ARM-based systems.
{{< /hint >}}

{{< /tab >}}

{{< tab "Regolith Linux 2.2 ISO" >}} 

Regolith Linux is the Regolith Desktop environment installed into a customized Ubuntu 22.10 installer image.  It allows one to boot from a USB drive to run Regolith without having to install it. It also allows to install the system onto a computer's drive.  Regolith Linux has the following features in addition to the Regolith Desktop:

* Regolith-branded boot and login screens
* Uses the `lightdm` display manager over `gdm3` to avoid unneeded dependencies
* The following packages are not installed: `gdm3`, `gnome-shell`, `ubuntu-session`, `evolution-data-server`, `snapd`.  These packages may be installed as needed by the user.

{{< button href="https://github.com/regolith-linux/regolith-ubuntu-iso-builder/releases/download/ubuntu-kinetic-2.2.0-20221211_050200/regolith-ubuntu-kinetic-2.2.0.zip" >}}Download Regolith Linux 2.2{{< /button >}}

See the [Regolith 2.2 release notes](docs/reference/Releases/regolith-2.2-release-notes) for more information.

The ISO can be written to a USB drive on Linux using [dd](https://www.man7.org/linux/man-pages/man1/dd.1.html), [GNOME Disk Utility](https://wiki.gnome.org/Apps/Disks), or the [KDE ISO Image Writer](https://community.kde.org/ISOImageWriter). On macOS, use [Etcher](https://www.balena.io/etcher/). On Windows, use [Rufus](https://rufus.ie/) and write in DD mode.

{{< /tab >}}
{{< /tabs >}}

### Debian

{{< tabs "debian-tabs" >}}

{{< tab "Debian Bookworm" >}}

Regolith can be installed as system packages.  This makes updating and removing easier and more consistent.  The following steps (also available as a [downloadable script](/install-release-debian-12-amd64.txt)) describe how
to configure your system to read packages from the Regolith package repository and install the desktop package.

1. Register the Regolith public key to your local `apt`:

   ```console
   wget -qO - https://regolith-desktop.org/regolith.key | \
   gpg --dearmor | sudo tee /usr/share/keyrings/regolith-archive-keyring.gpg > /dev/null
   ```

1. Add the repository URL to your local `apt`:

   ```console
   echo deb "[arch=amd64 signed-by=/usr/share/keyrings/regolith-archive-keyring.gpg] \
   https://regolith-desktop.org/release-3_0-debian-bookworm-amd64 bookworm main" | \
   sudo tee /etc/apt/sources.list.d/regolith.list
   ```

1. Update `apt` and install Regolith

   ```console
   sudo apt update
   sudo apt install regolith-desktop regolith-session-flashback regolith-look-lascaille
   ```
1. System Restart

The login manager will need to be restarted for the new desktop session to be recognized. The easiest way of restarting it is to reboot your system.

{{< hint info >}}
Replace `amd64` with `arm64` in the two places in the above line to install on ARM-based systems.
{{< /hint >}}

{{< hint info >}}
The `regolith-desktop` package installs a reasonable minimal configuration that should work on most hardware. To add additional package for a richer and more functional environment read [Recommended Packages for New Users](/docs/using-regolith/configuration/#recommended-packages-for-new-users).
{{< /hint >}}

{{< hint info >}}
The `regolith-compositor-picom-glx` compositor should work on most computers. If you experience driver or visual issues, [try another compositor](docs/howtos/customize-compositor).
{{< /hint >}}

{{< /tab >}}


{{< tab "Debian Bullseye" >}}

Regolith can be installed as system packages.  This makes updating and removing easier and more consistent.  The following steps (also available as a [downloadable script](/install-release-debian-11-amd64.txt)) describe how
to configure your system to read packages from the Regolith package repository and install the desktop package.

1. Register the Regolith public key to your local `apt`:

   ```console
   wget -qO - https://regolith-desktop.org/regolith.key | \
   gpg --dearmor | sudo tee /usr/share/keyrings/regolith-archive-keyring.gpg > /dev/null
   ```

1. Add the repository URL to your local `apt`:

   ```console
   echo deb "[arch=amd64 signed-by=/usr/share/keyrings/regolith-archive-keyring.gpg] \
   https://regolith-desktop.org/release-3_0-debian-bullseye-amd64 bullseye main" | \
   sudo tee /etc/apt/sources.list.d/regolith.list
   ```

1. Update `apt` and install Regolith

   ```console
   sudo apt update
   sudo apt install regolith-desktop regolith-compositor-picom-glx
   ```
1. System Restart

The login manager will need to be restarted for the new desktop session to be recognized. The easiest way of restarting it is to reboot your system.

{{< hint info >}}
Replace `amd64` with `arm64` in the two places in the above line to install on ARM-based systems.
{{< /hint >}}

{{< hint info >}}
The `regolith-desktop` package installs a reasonable minimal configuration that should work on most hardware. To add additional package for a richer and more functional environment read [Recommended Packages for New Users](/docs/using-regolith/configuration/#recommended-packages-for-new-users).
{{< /hint >}}

{{< hint info >}}
The `regolith-compositor-picom-glx` compositor should work on most computers. If you experience driver or visual issues, [try another compositor](docs/howtos/customize-compositor).
{{< /hint >}}

{{< /tab >}}

{{< /tabs >}}

## Release Change Policy

From Regolith 3.0 onward, all releases will use unique names in the package repo URL.  This means that users will be in full control of when they wish to upgrade to a new release.  Users wishing to have their package manager always install the latest version, a special stage called `release-current` is provided.