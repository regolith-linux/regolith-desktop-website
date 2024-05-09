---
title: "3.2 Release Notes"
linkTitle: "3.2 Release Notes"
weight: 1
description: >
  Release notes for Regolith 3.2
---

# Regolith 3.2 Release Notes

Regolith 3.2 is a minor release focusing on Ubuntu 24.04 support and bug fixes.

## Features

* Ubuntu 24.04 (Noble) support
* `regolith-control-center` rebased from GNOME 46 (for supported disto releases)
* Sway session promoted from `beta` to `stable` status
* Overhaul of X11 and Wayland session initialization

## Installation Instructions

Follow the standard installation instructions, but substitute `testing` instead of `release-3_1`.  For example, this is the `apt` line for Ubuntu Mantic:

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

## Changelog Delta from Regolith 3.1
