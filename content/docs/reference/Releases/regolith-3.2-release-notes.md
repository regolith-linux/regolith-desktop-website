---
title: "3.2 Release Notes (Beta 2)"
linkTitle: "3.2 Release Notes"
weight: 1
description: >
  Release notes for Regolith 3.2
---

## Regolith 3.2 Beta 2 Release Notes

Regolith 3.2 is a minor release focusing on Ubuntu 24.04 support, init system overhaul, and bug fixes.

### Features

* Ubuntu 24.04 (Noble) support
* `regolith-control-center` rebased from GNOME 46 (for supported releases)
* Sway session promoted from `beta` to `stable` status
* Overhaul of X11 and Wayland session initialization

### Deprecations

* Deprecating support for Ubuntu Focal and Debian Bullseye

### Installation Instructions

Follow the standard installation instructions, but substitute `testing` instead of `release-3_1`.  For example, this is the `apt` line for Ubuntu 24.04 (Noble):

```shell
echo deb "[arch=amd64 signed-by=/usr/share/keyrings/regolith-archive-keyring.gpg] \
https://regolith-desktop.org/testing-ubuntu-noble-amd64 noble main" | \
sudo tee /etc/apt/sources.list.d/regolith.list
```

After `apt upgrade` is complete, verify that Regolith 3.2 is installed by:

```shell
$ cat /etc/regolith/version 
REGOLITH_VERSION=3.2
```

A reboot is required for the new version to load.

### Changes since Regolith 3.1

#### Changes in `regolith-session`

```git
c79e188 feat: migrate sessions to systemd
```

#### Changes in `regolith-wm-config`

```git
56a6e8d fix: use systemd to init xdg-desktop-portal
ef17348 fix: import dbus activation ennvironment before other config partials
24e8795 fix: remove redunant call to dbus-update-activation-environment
a2832ce fix: specify 'no-startup-id' to avoid waiting mouse cursor in X11, unclear of effect in sway, adding for consistency.
08cc043 feat: notify systemd about successful session activation
6d1ba64 Fix Mediakeys binding to support muting the mic
e81a80a feat: add package for running mate polkit under xwayland
a0e3c3c fix: mate polkit binary location is distribution dependant
```

#### Changes in `regolith-desktop`

```git
5ce67ee chore: version bump to 3.2
```

#### Changes in `i3status-rs`

```git
db13009 fix: disable battery to avoid global error on bar on targets without batteries on Ubuntu 22.04
```

#### Changes in `xdg-desktop-portal-regolith`

```git
08cd870 fix: explicitly assign problematic portal interfaces (that fallback to GNOME) to regolith portal
```

### Changes since Regolith 3.2 beta 1

#### Changes in `regolith-displayd`

```git
b89ac56 amend version based on recent change
bd474a5 fix: use systemd to synchronize startup for displayd and kanshi (#5)
```

#### Changes in `regolith-inputd`

```git
34cb76c feat: add systemd service
8bbbee3 fix: rename var delay -> sources
```

#### Changes in `regolith-powerd`

```git
05afc0a feat: prevent logind actions for power key and lid
4f57160 feat: add systemd service
```

#### Changes in `regolith-session`

```git
2109934 fix: dont start session service starting targets
ab43221 chore: rename sway bin based on changes in sway-regolith package
```

#### Changes in `regolith-wm-config`

```git
25c83a2 fix: add exec flag to fix spinner mouse cursor not present upon desktop load on x11
21774ac feat: restart regolith-init-kanshi service as user
9f68d28 feat: Update package dependencies version
148a376 feat: remove manual startup of gsd-integrations
3004ebe chore: manually start regolith-wayland.target if session doesnt use systemd
8b25827 feat: add keybindings to cycle between keyboard layouts
ba7841a chore: add packages for dbus-activation configs to Depends to ensure they're always installed with the session
5bc7cea fix: import XDG_CURRENT_DESKTOP into systemd_environment to ensure correct portal config is selected
```

#### Changes in `sway-regolith`

```git
5ef388bf fix: remove desktop session file
b1857f95 fix: declare incompat w/ upstream
88b5271a fix: clean up package metadata
e88844b2 chore: update patches to use upstream bin name
6bcc07b7 chore: cleanup unrequired deps from the sway-regolith package (#22)
```
