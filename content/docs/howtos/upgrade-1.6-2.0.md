---
title: "Upgrade Regolith from 1.6 to 2.0"
description: >
  Instructions for upgrading Regolith to the 2.0 version
---

This page describes how to upgrade Regolith to 2.0. The general process is to remove the 1.6 packages and then install the 2.0 packages.

## Ubuntu Upgrade

If updating Regolith is part of a distro upgrade process, first upgrade the distro.  Once the distro upgrade is complete and is working with it's default session, proceed with Regolith 2.  The distro upgrade process will automatically remove the Regolith 1.x PPA from your system.

## Clean up Regolith 1.x

First we remove the Regolith 1.x packages from the system:

```console
$ sudo apt purge regolith-*
$ sudo apt purge i3xrocks-*
$ sudo apt autoremove
```

## Install Regolith 2.0

Now that the 1.x packages have been removed, follow the directions on [regolith-desktop.com](regolith-desktop.com) to add the 2.x package repository and install packages.

## Note on Changes in 2.x

Some file locations have changed.  User configuration files for Regolith 2 live in `~/.config/regolith2`.  Any older Regolith 1.x user configuration files will still be in `~/.config/regolith`.  As part of the upgrade process, you'll need to decide which configurations should be copied over to 2.0.  The default Regolith i3 config partials and i3xrocks configuration moved from `/etc/regolith` to `/usr/share/regolith..`.  This was done to side-step file issues that result in `apt`s policy of not removing config files when packages are removed.
