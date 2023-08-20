---
title: Introduction
type: docs
bookToc: false
---

# The Regolith Desktop Environment

![](/regolith-empty.png)

{{< columns >}}

### Productivity First

Regolith runs [i3](https://i3wm.org/): a popular, fast, and configurable tiling window manager which
is great for fast keyboard-driven workflows.  Regolith integrates i3 with other desktop components such as 
`i3bar`, `rofication`, `gnome-flashback`, and [`ilia`](https://github.com/regolith-linux/ilia#readme) to provide a complete desktop interface.

<--->

### GNOME System Management

By providing a gnome session with [`gnome-flashback`](https://wiki.gnome.org/Projects/GnomeFlashback), Regolith sidesteps
much of the complexity of a typical `gnome-shell` based environment while providing
simple and consistent system management capabilities.

{{< /columns >}}

***

# Get Regolith 2.2

{{< hint warning >}}
UPDATE: The Regolith repository key has changed. Update it by re-running the first step for your distro/version from below. [More Details](https://github.com/orgs/regolith-linux/discussions/888)
{{< /hint >}}

{{< tabs "uniqueid" >}}
{{< tab "Ubuntu 22.10" >}}

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
   https://regolith-desktop.org/release-ubuntu-kinetic-amd64 kinetic main" | \
   sudo tee /etc/apt/sources.list.d/regolith.list
   ```

1. Update `apt` and install Regolith

   ```console
   sudo apt update
   sudo apt install regolith-desktop regolith-compositor-picom-glx
   sudo apt upgrade
   ```
1. System Restart

The login manager will need to be restarted for the new desktop session to be recognized. The easiest way of restarting it is to reboot your system.

{{< hint info >}}
Substitute `arm64` for `amd64` in the two places in the above line to install on ARM-based systems.
{{< /hint >}}

{{< hint info >}}
The `regolith-desktop` package installs a reasonable minimal configuration that should work on most hardware. To add additional package for a richer and more functional environment read [Recommended Packages for New Users](/docs/using-regolith/configuration/#recommended-packages-for-new-users).
{{< /hint >}}

{{< hint info >}}
The `regolith-compositor-picom-glx` compositor should work on most computers. If you experience driver or visual issues, [try another compositor](docs/howtos/customize-compositor).
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
   https://regolith-desktop.org/release-ubuntu-jammy-amd64 jammy main" | \
   sudo tee /etc/apt/sources.list.d/regolith.list
   ```

1. Update `apt` and install Regolith

   ```console
   sudo apt update
   sudo apt install regolith-desktop regolith-compositor-picom-glx
   sudo apt upgrade
   ```
1. System Restart

The login manager will need to be restarted for the new desktop session to be recognized. The easiest way of restarting it is to reboot your system.

{{< hint info >}}
Substitute `arm64` for `amd64` in the two places in the above line to install on ARM-based systems.
{{< /hint >}}

{{< hint info >}}
The `regolith-desktop` package installs a reasonable minimal configuration that should work on most hardware. To add additional package for a richer and more functional environment read [Recommended Packages for New Users](/docs/using-regolith/configuration/#recommended-packages-for-new-users).
{{< /hint >}}

{{< hint info >}}
The `regolith-compositor-picom-glx` compositor should work on most computers. If you experience driver or visual issues, [try another compositor](docs/howtos/customize-compositor).
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
   echo deb "[arch=amd64] https://regolith-desktop.org/release-ubuntu-focal-amd64 focal main" | \
   sudo tee /etc/apt/sources.list.d/regolith.list
   ```

1. Update `apt` and install Regolith

   ```console
   sudo apt update
   sudo apt install regolith-desktop regolith-compositor-picom-glx
   sudo apt upgrade
   ```

1. System Restart

The login manager will need to be restarted for the new desktop session to be recognized. The easiest way of restarting it is to reboot your system.

{{< hint info >}}
Substitute `arm64` for `amd64` in the two places in the above line to install on ARM-based systems.
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
   https://regolith-desktop.org/release-debian-bullseye-amd64 bullseye main" | \
   sudo tee /etc/apt/sources.list.d/regolith.list
   ```

1. Update `apt` and install Regolith

   ```console
   sudo apt update
   sudo apt install regolith-desktop regolith-compositor-picom-glx
   sudo apt upgrade
   ```
1. System Restart

The login manager will need to be restarted for the new desktop session to be recognized. The easiest way of restarting it is to reboot your system.

{{< hint info >}}
Substitute `arm64` for `amd64` in the two places in the above line to install on ARM-based systems.
{{< /hint >}}

{{< hint info >}}
The `regolith-desktop` package installs a reasonable minimal configuration that should work on most hardware. To add additional package for a richer and more functional environment read [Recommended Packages for New Users](/docs/using-regolith/configuration/#recommended-packages-for-new-users).
{{< /hint >}}

{{< hint info >}}
The `regolith-compositor-picom-glx` compositor should work on most computers. If you experience driver or visual issues, [try another compositor](docs/howtos/customize-compositor).
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


## Visual Tour
***

{{< columns >}}

[![](/regolith-ilia-keybindings.png)](/regolith-ilia-keybindings.png)
Upon first login, an overlay (toggled anytime via <span class="text-nowrap"><span class="badge badge-warning">super</span> <span class="badge badge-warning">?</span></span>) presents the most important keybindings used with i3-wm.

<--->

[![](/regolith-floating-terminal.png)](/regolith-floating-terminal.png)
For those that work in the terminal, pressing <span class="text-nowrap"><span class="badge badge-warning">super</span> <span class="badge badge-warning">enter</span></span> is all it takes to get to business.

{{< /columns >}}

{{< columns >}}

[![](/regolith-ilia-apps.png)]((/regolith-ilia-apps.png))
A single global app launcher is instantly available from anywhere to run your programs via <span class="text-nowrap"><span class="badge badge-warning">super</span> <span class="badge badge-warning">space</span></span>.</p>

<--->

[![](/regolith-desktop-terminals.png)](/regolith-desktop-terminals.png)
Need more terminals?  Create layouts on the fly by toggling between horizontal and vertical modes with <span class="text-nowrap"><span class="badge badge-warning">super</span> <span class="badge badge-warning">backspace</span></span> followed by <span class="text-nowrap"><span class="badge badge-warning">super</span> <span class="badge badge-warning">enter</span></span>.  Navigate to windows positionally with <span class="text-nowrap"><span class="badge badge-warning">super</span> <span class="badge badge-warning">h</span> <span class="badge badge-warning">j</span> <span class="badge badge-warning">k</span> <span class="badge badge-warning">l</span></span>.

{{< /columns >}}

{{< columns >}}

[![](/regolith-floating-windows.png)](/regolith-floating-windows.png)
Toggle floating window mode with <span class="text-nowrap"><span class="badge badge-warning">super</span> <span class="badge badge-warning">F</span></span>.  Resize windows with <span class="text-nowrap"><span class="badge badge-warning">super</span> <span class="badge badge-warning">r</span></span> and move them around with the mouse by pressing <span class="badge badge-warning">super</span>.

<--->

[![](/regolith-gnome-flashback.png)](/regolith-gnome-flashback.png)
Gnome Flashback provides consistent and simple system management. Tweak your UI, auto mount your USB drives, connect to wireless networks. Launch the control panel with <span class="text-nowrap"><span class="badge badge-warning">super</span> <span class="badge badge-warning">c</span></span>.

{{< /columns >}}

{{< columns >}}

[![](/regolith-screenshot-look-selector.png)](/regolith-screenshot-look-selector.png)
Easily switch to <a href="https://ethanschoonover.com/solarized">Solarized</a> or other looks with the <code>regolith-look</code> command. Because <b>looks</b> utilize the package manager, you only store theme resources that you're using.

<--->

[![](/regolith-ilia-windows.png)](/regolith-ilia-windows.png)
Got a lot going on?  Quickly find the window you're looking for via <span class="text-nowrap"><span class="badge badge-warning">super</span> <span class="badge badge-warning">ctrl</span> <span class="badge badge-warning">space</span></span> or navigate over workspaces with <span class="text-nowrap"><span class="badge badge-warning">super</span> <span class="badge badge-warning">[0 - 19]</span></span>.

{{< /columns >}}

{{< columns >}}

[![](/regolith-many-windows.png)](/regolith-many-windows.png)
Waste no space on frivolous UI and take advantage of every pixel without micro-managing your window layouts.

<--->

[![](/regolith-ilia-notifications.png)](/regolith-ilia-notifications.png)
Desktop notifications do not compete for your attention, but rather can be managed via an on-screen dialog by pressing <span class="text-nowrap"><span class="badge badge-warning">super</span> <span class="badge badge-warning">n</span></span>.

{{< /columns >}}

# Interaction

{{< columns >}}

### Announcements

* [Subscribe to the mailing list for release announcements](https://www.freelists.org/list/regolith-linux)

<--->

### Discussion and Help

* Join us on [GitHub Discussions](https://github.com/orgs/regolith-linux/discussions) for help and discussion
* Search from [existing issues or create a new issue](https://github.com/regolith-linux/regolith-desktop/issues) for bugs and feature requests
<--->

### Development

* The [Regolith GitHub org](https://github.com/regolith-linux) is where development happens.

{{< /columns >}}
