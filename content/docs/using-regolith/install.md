---
title: "Install"
linkTitle: "Install"
weight: 1
description: >
  Install Regolith
---

# Get Regolith 3.2

If you're upgrading from an earlier version of Regolith, you may be interested in reading [the release notes](/docs/reference/Releases/regolith-3.2-release-notes) and if coming from 2.x, the [migration guide](/docs/reference/Releases/regolith-3.0-release-notes/#migration-guide).

## Supported Operating Systems

### Ubuntu

{{< tabs "ubuntu-tabs" >}}
{{< tab "Ubuntu 24.10" >}}

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
   https://regolith-desktop.org/release-3_2-ubuntu-oracular-amd64 oracular main" | \
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
{{< tab "Ubuntu 24.04" >}}

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
   https://regolith-desktop.org/release-3_2-ubuntu-noble-amd64 noble main" | \
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
   https://regolith-desktop.org/release-3_2-ubuntu-jammy-amd64 jammy main" | \
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
{{< /tabs >}}

### Debian

{{< tabs "debian-tabs" >}}

{{< tab "Debian Testing" >}}

For Debian users that use the "Testing" release, Regolith can be installed, however there is no "release" version due to the nature of Debian Testing.  In order to install Regolith into a Debian Testing instance, the `apt` line contains `testing` instead of a `release` string.  For example:

   ```console
   echo deb "[arch=amd64 signed-by=/usr/share/keyrings/regolith-archive-keyring.gpg] \
   https://regolith-desktop.org/testing-debian-testing-amd64 testing main" | \
   sudo tee /etc/apt/sources.list.d/regolith.list
   ```

Otherwise the installation steps are the same as an official Debian release.  Note that broken dependencies or components will occur from time to time.  If stability is important, consider installing into an officially released version of Debian or Ubuntu.

{{< /tab >}}

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
   https://regolith-desktop.org/release-3_2-debian-bookworm-amd64 bookworm main" | \
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

{{< /tabs >}}

## Packages Specified at Install Time

Starting with Regolith 3.0 it is now possible to select from multiple sessions (X11: `regolith-session-flashback`, Wayland: `regolith-session-sway`). Due to this, when installing Regolith 3.2 also specify one or both sessions that you wish to use. Additionally, it's now possible to specify the Regolith Look at install time, which saves a setup of having to configure it later.  Here is the recommended base install for X11 on Debian-based systems:

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

## Anatomy of the Regolith `apt` URL Path

```console
https://regolith-desktop.org/testing-debian-testing-amd64
                             |       |      |       |
                             |       |      |       * Architecture
                             |       |      * Distro Version/Codename
                             |       * Distro Name
                             * Regolith Stage
```

### Regolith Stages

|Stage|URL String|Description|
|---|---|---|
|Experimental|`experimental`|Stage for testing experiments|
|Unstable|`unstable`|Stage for early development testing|
|Testing|`testing`|Stage for late development testing|
|Release X.Y|`release-X_Y`|Stage for specific official release|
|Current Release|`release-current` |Stage for latest release (floating from release to release)|

### Distro Names

|Name | Description |
|---|---|
|`ubuntu`| The Ubuntu Linux Distribution|
|`debian`| The Debian Linux Distribution|

### Distro Version/Codename

These labels are determined by their respective upstream communities.  Examples are `noble`, `bookworm`, `focal`.

### Architecture

|Name | Description |
|---|---|
|`amd64`| The 64-bit x86 architecture |
|`arm64`| The 64-bit Arm architecture |


### Examples

|Description | URL |
|---|---|
|The 3.2 release of Regolith on Ubuntu Jammy for `amd64`|`https://regolith-desktop.org/release-3_2-ubuntu-jammy-amd64`|
|The latest release of Regolith on Debian Bookworm for `amd64`|`https://regolith-desktop.org/release-current-debian-bookworm-amd64`|
|Testing repo for Regolith on Debian Testing for `arm64`|`https://regolith-desktop.org/testing-debian-testing-arm64`|

## Release Change Policy

From Regolith 3.0 onward, all releases will use unique names in the package repo URL.  This means that users will be in full control of when they wish to upgrade to a new release.  Users wishing to have their package manager always install the latest version, a special stage called `release-current` is provided.