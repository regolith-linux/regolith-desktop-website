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

## Installation Instructions

Follow the standard installation instructions, but substitue `testing` instead of `release-3_0`.  For example, this is the `apt` line for Ubuntu Manic:

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

## Changelog Delta from Regolith 3.1


## Changes in `regolith-session`:
```
8f5da99 fix: set XDG_CURRENT_DESKTOP for wayland session (fixes screencasting)
```


## Changes in `regolith-wm-config`:
```
8e47c87 Merge pull request #10 from regolith-linux/fix-rofication-dep
9b1706d Move default-style to soft dep for both sessions.  demote 3 more for sway session to soft per PR feedback
d21c32c fix: remove (redundant) hard dependency from sway session to rofication. Soft dependency comes via regolith-wm-config.
```

## Changes in `sway-audio-idle-inhibit`:
```
162c01f chore: bump libwlroots dependency version
```

