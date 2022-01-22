---
title: "Stage Config Files"
description: >
  Learn how to stage user copies of Regolith configuration files.
---

{{< hint danger >}}
NOTICE: This page was copied from the [Regolith 1.x website](https://regolith-linux.org) and has not been updated for Regolith 2.  It may contain out of date information.
{{< /hint >}}

{{< hint info >}}
If you only wish to override or provide new `Xresources` values, staging configs is not required and not recommended. Overriding `Xresources` value is described in a [separate article]({{< ref "override-xres" >}}).
{{< /hint >}}

Regolith uses a number of files in `/etc/regolith` to determine the behavior and look of various components. While it's possible to simply edit these files directly, users who do so run the risk of having their configurations overwritten upon future updates. The Debian packaging system should ask users if they wish to take updates or keep the existing files, but this may have unintended side effects if users take partial updates of files. As such Regolith, upon login, will look for user-staged version of configuration files and load those _instead of the defaults_ if they exist. This is recommended over editing the files in `/etc/regolith` directly as it gives the user more control over their configuration. This page describes how to create these files.

Depending on what you wish to change, you may need your own copy if the i3 config file, `Xresources`, or both. If you're looking to change the way Regolith looks, `Xresources` may be all you need. If you want to update or add keybindings or swap out components, you'll most likely need to stage the i3 config file.

## i3 Config

1. Copy the default Regolith i3 config file into your home directory:

```
$ mkdir -p ~/.config/regolith/i3
$ cp /etc/regolith/i3/config ~/.config/regolith/i3/config
```

2. Log out and back in. The Regolith session will automatically detect your user-staged file and use that over the default in `/etc/regolith/i3`.

### Verify the Change

1. Verify by running `i3 --moreversion` and noting the config file that is printed as a result. It should be the copy you just created. If not, be sure the path is correct. It must exactly be `~/.config/regolith/i3/config` for Regolith to load it.

## Regolith Styles

1. Copy the root Regolith `Xresources` file into your home directory:

```
$ cp /etc/regolith/styles/root ~/.Xresources-regolith
```

2. Log out and back in. The Regolith session will automatically detect your user-staged file and use that over the default in `/etc/regolith/styles`.

Note that this root file is simply a reference to other styles that are broken down by the thing they are designed to style. For example, if you wish to customize the look of i3, you will need to also copy `/etc/regolith/styles/i3-wm` into your user directory and then update the reference to the new file in your `~/.Xresources-regolith`.
