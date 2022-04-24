---
title: "Wallpaper Configuration"
description: >
  Change wallpaper via GNOME or Xresources
---

This page describes how to configure the wallpaper in Regolith, which can be set via `Xresources` overrides.

## Xresources

The way of setting the wallpaper is by specifying a file path to the image in the `Xresources` key `gnome.wallpaper`. Upon session load, wallpaper will be set if a image file is specified at this key. For example, here is how to specify an override to set the wallpaper to the default Ubuntu wallpaper:

```console
$ echo "gnome.wallpaper: /usr/share/backgrounds/warty-final-ubuntu.png" >> ~/.config/regolith2/Xresources
```

## Disable all Wallpaper Handling

Regolith can be configured to ignore wallpaper.  To do this set the `gnome.wallpaper` Xresource value to empty as specified above and then configure `gnome-flashback` to not manage the desktop:

```console
$ echo "gnome.wallpaper:" >> ~/.config/regolith2/Xresources
$ gsettings set org.gnome.gnome-flashback.desktop draw-background false
```
