---
title: Introduction
type: docs
bookToc: false
---

# The Regolith Desktop Environment

![](/regolith-empty.png)

{{< columns >}}
### For People Comfortable with PCs

Regolith is built for those with a working knowledge of using computers. It avoids the clutter
and ceremony that comes along with environments designed for familiarity with legacy interfaces.
Regolith runs [i3](https://i3wm.org/): a popular, fast, and configurable tiling window manager which
is great for keyboard-driven interaction.  Regolith integrates i3 with other desktop components such as 
`i3bar`, `rofication`, and `ilia` to provide a complete desktop interface.

<--->

### GNOME based System Management

By providing a gnome session with [`gnome-flashback`](https://wiki.gnome.org/Projects/GnomeFlashback), Regolith sidesteps
much of the complexity of a typical `gnome-shell` based environment while providing
simple and consistent system management capabilities via `gnome-settings`.

{{< /columns >}}

***

# Get Regolith 2.0

{{< hint danger >}}
Currently the Regolith 2.0 release is [in active development](https://github.com/orgs/regolith-linux/projects/16). For production use, [Regolith 1.6](https://regolith-linux.org) is recommended.
{{< /hint >}}

{{< tabs "uniqueid" >}}
{{< tab "Ubuntu 20.04" >}}

Regolith can be installed as system packages.  This makes updating and removing easy and consistent.  The following steps describe how
to configure your system to read packages from the Regolith package repository and install the desktop package.

1. Register the Regolith public key to your local `apt`:
```bash
wget -qO - https://regolith-linux.github.io/package-repo/regolith.key | sudo apt-key add -
```
2. Add the repository URL to your local `apt`:
```bash
echo deb "[arch=amd64] https://regolith-release-ubuntu-focal-amd64.s3.amazonaws.com focal main" | \
sudo tee /etc/apt/sources.list.d/regolith.list
```
3. Update `apt` and install Regolith
```bash
sudo apt update
sudo apt install regolith-desktop
```
4. System Restart

The login manager will need to be restarted for the new desktop session to be recognized. The easiest way of restarting it is to reboot your system.

{{< hint warning >}}
The Regolith Desktop is very different from common desktop environments. By default does not use docks, icon folders, or global drop-down menus.  See the [Getting Started guide]({{< ref "/docs/using-regolith/first-launch" >}}) for important details.
{{< /hint >}}

{{< /tab >}}
{{< tab "Ubuntu 21.10" >}}

Regolith can be installed as system packages.  This makes updating and removing easy and consistent.  The following steps describe how
to configure your system to read packages from the Regolith package repository and install the desktop package.

1. Register the Regolith public key to your local `apt`:
```bash
wget -qO - https://regolith-linux.github.io/package-repo/regolith.key | sudo apt-key add -
```
2. Add the repository URL to your local `apt`:
```bash
echo deb "[arch=amd64] https://regolith-release-ubuntu-impish-amd64.s3.amazonaws.com impish main" | \
sudo tee /etc/apt/sources.list.d/regolith.list
```
3. Update `apt` and install Regolith
```bash
sudo apt update
sudo apt install regolith-desktop
```
4. System Restart

The login manager will need to be restarted for the new desktop session to be recognized. The easiest way of restarting it is to reboot your system.

{{< hint warning >}}
The Regolith Desktop is very different from common desktop environments. By default does not use docks, icon folders, or global drop-down menus.  See the [Getting Started guide]({{< ref "/docs/using-regolith/first-launch" >}}) for important details.
{{< /hint >}}

{{< /tab >}}

{{< tab "Debian Bullseye" >}}

Regolith can be installed as system packages.  This makes updating and removing easy and consistent.  The following steps describe how
to configure your system to read packages from the Regolith package repository and install the desktop package.

1. Register the Regolith public key to your local `apt`:
```bash
wget -qO - https://regolith-linux.github.io/package-repo/regolith.key | sudo apt-key add -
```
2. Add the repository URL to your local `apt`:
```bash
echo deb "[arch=amd64] https://regolith-release-debian-bullseye-amd64.s3.amazonaws.com bullseye main" | \
sudo tee /etc/apt/sources.list.d/regolith.list
```
3. Update `apt` and install Regolith
```bash
sudo apt update
sudo apt install regolith-desktop
```
4. System Restart

The login manager will need to be restarted for the new desktop session to be recognized. The easiest way of restarting it is to reboot your system.

{{< hint warning >}}
The Regolith Desktop is very different from common desktop environments. By default it does not use docks, icon folders, or global drop-down menus.  See the [Getting Started guide]({{< ref "/docs/using-regolith/first-launch" >}}) for important details.
{{< /hint >}}

{{< /tab >}}
{{< tab "Other..." >}} 

Other options are available and documented in the [package repository for Regolith](https://github.com/regolith-linux/voulage), including support for `arm64` based systems.

{{< /tab >}}
{{< /tabs >}}

{{< columns >}}

![](/regolith-ilia-keybindings.png)
Upon first login, an overlay (toggled anytime via <span class="text-nowrap"><span class="badge badge-warning">super</span> <span class="badge badge-warning">?</span></span>) presents the most important keybindings used with i3-wm.

<--->

![](/regolith-floating-terminal.png)
For those that work in the terminal, pressing <span class="text-nowrap"><span class="badge badge-warning">super</span> <span class="badge badge-warning">enter</span></span> is all it takes to get to business.

{{< /columns >}}

{{< columns >}}

![](/regolith-ilia-apps.png)
A single global app launcher is instantly available from anywhere to run your programs via <span class="text-nowrap"><span class="badge badge-warning">super</span> <span class="badge badge-warning">space</span></span>.</p>

<--->

![](/regolith-desktop-terminals.png)
Need more terminals?  Create layouts on the fly by toggling between horizontal and vertical modes with <span class="text-nowrap"><span class="badge badge-warning">super</span> <span class="badge badge-warning">backspace</span></span> followed by <span class="text-nowrap"><span class="badge badge-warning">super</span> <span class="badge badge-warning">enter</span></span>.  Navigate to windows positionally with <span class="text-nowrap"><span class="badge badge-warning">super</span> <span class="badge badge-warning">h</span> <span class="badge badge-warning">j</span> <span class="badge badge-warning">k</span> <span class="badge badge-warning">l</span></span>.

{{< /columns >}}

{{< columns >}}

![](/regolith-floating-windows.png)
Toggle floating window mode with <span class="text-nowrap"><span class="badge badge-warning">super</span> <span class="badge badge-warning">F</span></span>.  Resize windows with <span class="text-nowrap"><span class="badge badge-warning">super</span> <span class="badge badge-warning">r</span></span> and move them around with the mouse by pressing <span class="badge badge-warning">super</span>.

<--->

![](/regolith-gnome-flashback.png)
Gnome Flashback provides consistent and simple system management. Tweak your UI, auto mount your USB drives, connect to wireless networks. Launch the control panel with <span class="text-nowrap"><span class="badge badge-warning">super</span> <span class="badge badge-warning">c</span></span>.

{{< /columns >}}

{{< columns >}}

![](/regolith-screenshot-intro.png)
Easily switch to <a href="https://ethanschoonover.com/solarized">Solarized</a> or other looks with the <code>regolith-look</code> command. Because <b>looks</b> utilize the package manager, you only store theme resources that you're using.

<--->

![](/regolith-ilia-windows.png)
Got a lot going on?  Quickly find the window you're looking for via <span class="text-nowrap"><span class="badge badge-warning">super</span> <span class="badge badge-warning">ctrl</span> <span class="badge badge-warning">space</span></span> or navigate over workspaces with <span class="text-nowrap"><span class="badge badge-warning">super</span> <span class="badge badge-warning">[0 - 19]</span></span>.

{{< /columns >}}

{{< columns >}}

![](/regolith-many-windows.png)
Waste no space on frivolous UI and take advantage of every pixel without micro-managing your window layouts.

<--->

![](/regolith-ilia-notifications.png)
Desktop notifications do not compete for your attention, but rather can be managed via an on-screen dialog by pressing <span class="text-nowrap"><span class="badge badge-warning">super</span> <span class="badge badge-warning">n</span></span>.

{{< /columns >}}



# Interaction

{{< columns >}}

### Announcements

* [Follow us on Twitter to get the latest news](https://twitter.com/RegolithL)
* [Follow us on Mastodon to get the latest news](https://fosstodon.org/@regolith)
* [Subscribe to the mailing list for release annoucements](https://www.freelists.org/list/regolith-linux)

<--->

### Discussion and Help
* Join us on [Slack](https://regolith-linux.herokuapp.com/) for help and discussion
* Search from [existing issues or create a new issue](https://github.com/regolith-linux/regolith-desktop/issues) for bugs and feature requests
<--->

### Development
* The [Regolith GitHub org](https://github.com/regolith-linux) is where development happens.

{{< /columns >}}