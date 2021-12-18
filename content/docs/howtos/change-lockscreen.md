---
title: "Change the lock screen program"
description: >
  Configure Regolith to use a lock screen other than `gnome-flashback`
---

{{< hint danger >}}
NOTICE: This page was copied from the [Regolith 1.x website](https://regolith-linux.org) and has not been updated for Regolith 2.  It may contain out of date information.
{{< /hint >}}

### 1. Configure `gnome-flashback` to Disable Built-in Lockscreen

By default `gnome-flashback` handles the lock screen for Regolith. This can be adjusted by modifying it's configuration via the `gsettings` command line program:

```console
$ gsettings set org.gnome.gnome-flashback screensaver false
```

### 2. Cause Your Lock screen program to Run from i3 Keybinding

Specify the following override line in your `~/.config/regolith/Xresources` file (substituting `your-script.sh` with the command you wish to use for the locking your screen):

```toml
i3-wm.program.lock: your-script.sh
```

For example, assuming you have `i3lock` installed:

```console
$ echo "i3-wm.program.lock: /usr/bin/i3lock" >> ~/.config/regolith/Xresources
```
