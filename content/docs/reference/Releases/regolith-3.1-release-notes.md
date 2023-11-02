---
title: "3.1 Release Notes"
linkTitle: "3.1 Release Notes"
weight: 2
description: >
  Release notes for Regolith 3.1
---

# Regolith 3.1 Release Notes

[Regolith 3.1](https://github.com/orgs/regolith-linux/projects/26) is a minor release focusing on Ubuntu 23.10 support.

## New Major Features

* Ubuntu 23.10 (manic) support
* `i3-next-workspace` [ported to Sway](https://github.com/regolith-linux/childe)
* `regolith-control-center` rebased from GNOME 45

## Installation Instructions

Follow the standard installation instructions, but substitute `testing` instead of `release-3_0`.  For example, this is the `apt` line for Ubuntu Manic:

```
echo deb "[arch=amd64 signed-by=/usr/share/keyrings/regolith-archive-keyring.gpg] \
https://regolith-desktop.org/testing-ubuntu-manic-amd64 manic main" | \
sudo tee /etc/apt/sources.list.d/regolith.list
```

After `apt upgrade` is complete, verify that Regolith 3.1 is installed by:

```
$ cat /etc/regolith/version 
REGOLITH_VERSION=3.1
```

A reboot is required for the new version to load.

## Changelog Delta from Regolith 3.0

### Changes in `regolith-displayd`:
```
aa3d572 fix: cannot reenable monitors
c4ebc88 fix: disabled monitors should reflect in mointors instead of logical_monitors
5cdb6df feat: add support for builtin monitor
```


### Changes in `regolith-i3xrocks-config`:
```
320980c fix: relax dependency on control center.
```

### Changes in `regolith-session`:
```
8f5da99 fix: set XDG_CURRENT_DESKTOP for wayland session (fixes screencasting)
```


### Changes in `regolith-wm-config`:
```
8e47c87 Merge pull request #10 from regolith-linux/fix-rofication-dep
9b1706d Move default-style to soft dep for both sessions.  demote 3 more for sway session to soft per PR feedback
d21c32c fix: remove (redundant) hard dependency from sway session to rofication. Soft dependency comes via regolith-wm-config.
```

### Changes in `sway-audio-idle-inhibit`:
```
162c01f chore: bump libwlroots dependency version
```

### Changes in `regolith-wm-config`:
```
db38632 fix: force removal of deprecated ilia integration package
7f1bae9 fix: enable carry mode in childe
b9d42e8 fix: prevent broken legacy package from remaining installed for next-workspace
6992986 fix: properly segment i3 and say versions of next-workspace partial
b36e821 feat: add next-workspace feature to sway session, copied from x11 i3-next-workspace
6356077 [15_base_launchers] add vm.program.browser
a777246 [15_base_launchers] add vm.program.terminal
```

### Changes in `trawl`:
```
dfcabfb chore: pin zvariant version to 3.4.1
```
