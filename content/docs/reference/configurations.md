---
title: "Config Files"
linkTitle: "Config Files"
weight: 2
description: >
  General information about the config files that Regolith uses
---

{{< hint danger >}}
NOTICE: This page was copied from the [Regolith 1.x website](https://regolith-linux.org) and has not been updated for Regolith 2.  It may contain out of date information.
{{< /hint >}}

| **Component**              | **Default Config**                                               | **User Config**                                                                                                                              | **Notes**                                                                                                       |
| -------------------------- | ---------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------- |
| i3-gaps                    | `/etc/regolith/i3/config`                                        | `~/.config/regolith/i3/config`                                                                                                               | In Regolith versions prior to 1.2 this file was in another directory.                                           |
| Xresources                 | `/etc/regolith/styles/root`                                      | `~/.Xresources-regolith` (Global override)<br/>`~/.config/regolith2/Xresources` (Override)<br/>`~/.config/regolith2/Xresources.d` (User files) | `~/.Xresources` is also loaded but intended for properties that may also be required in other desktop sessions. |
| Rofi                       | `/etc/regolith/styles/lascaille/rofi.rasi`                       | Defined in the `theme` style file.                                                                                                           | This can also be overridden directly in the i3 file if preferred.                                               |
| Bar Workspace Labels       | `/etc/regolith/styles/i3-wm`                                     | User defined                                                                                                                                 |                                                                                                                 |
| Bar status indicators      | `/etc/regolith/i3xrocks/conf.d`                                  | `~/.config/regolith/i3xrocks/conf.d`                                                                                                         | Each block has it's own file. Filename determines ordering.                                                     |
| Picom (Compton) Compositor | `/etc/regolith/picom/config`                                     | `~/.config/regolith/picom/config`                                                                                                            | User config added in 1.5. Each compositor has it's own independent config file, but the default is `Picom`.     |
| LightDM GTK Greeter        | `/usr/share/lightdm/lightdm-gtk-greeter.conf.d/02_regolith.conf` | N/A                                                                                                                                          | This file only exists if the `regolith-lightdm-config` package is installed.                                    |

## Load Sequence

Upon session start, Regolith loads configuration files in the following order:

1. `/usr/bin/i3-gnome-flashback` executes after successful login
2. Load `Xresources` file `~/.Xresources` if it exists.
3. Load `Xresources` file `~/.Xresources-regolith` if it exists.
4. Merge any values from file `~/.config/regolith2/Xresources` if it exists.
5. If first time session has loaded, initialize system.
6. Compare current `Xresources` db against last saved hash, if different, reload GNOME settings from Xresources.
7. Execute i3 with first config file found from following list: `~/.config/regolith/i3/config`, `/etc/regolith/i3/config`, `/etc/i3/config`.
8. i3 executes the UI components [Rofi](https://github.com/davatorium/rofi), [i3xrocks](https://github.com/regolith-linux/i3xrocks), [unclutter](https://github.com/Airblader/unclutter-xfixes), regolith-compositor, [Rofication](), and [regolith-ftue](https://github.com/regolith-linux/regolith-ftue).
