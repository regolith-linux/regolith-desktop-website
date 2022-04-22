---
title: "Wallpaper Configuration"
description: >
  Change wallpaper via GNOME or Xresources
---

{{< hint danger >}}
NOTICE: This page was copied from the [Regolith 1.x website](https://regolith-linux.org) and has not been updated for Regolith 2.  It may contain out of date information.
{{< /hint >}}

This page describes how to configure the wallpaper in Regolith, which can either be set via the GNOME Settings, or in dotfiles via `Xresources` overrides.

## GNOME settings

As is mentioned in the Getting Started section, wallpaper can be set using GNOME Settings. Some Looks specific specific wallpaper that is set to go along with the color theme and other style changes. An `Xresources` value can be set to tell Regolith to ignore Look settings and keep which ever wallpaper has been selected via GNOME Settings. The following command will set the `gnome.wallpaper` `Xresources` key to an empty value, which will prevent Regolith from making any changes:

```console
$ echo "gnome.wallpaper: " >> ~/.config/regolith2/Xresources
```

## Xresources

Another way of setting the wallpaper is by specifying a file path to the image in the `Xresources` key `gnome.wallpaper`. Upon session load, wallpaper will be set if a image file is specified at this key. For example, here is how to specify an override to set the wallpaper to the default Ubuntu wallpaper:

```console
$ echo "gnome.wallpaper: /usr/share/backgrounds/warty-final-ubuntu.png" >> ~/.config/regolith2/Xresources
```

## Disable all Wallpaper Handling

Regolith can be configured to ignore wallpaper.  To do this set the `gnome.wallpaper` Xresource value to empty as specified above and then configure `gnome-flashback` to not manage the desktop:

```console
$ gsettings set org.gnome.gnome-flashback.desktop draw-background false
```
