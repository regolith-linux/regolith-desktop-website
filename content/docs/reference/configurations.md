---
title: "Config Files"
linkTitle: "Config Files"
weight: 2
description: >
  General information about the config files that Regolith uses
---

| **Component**              | **Default Config**                                               | **User Config**                                                                                                                              | **Notes**                                                                                                       |
| -------------------------- | ---------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------- |
| i3 / i3-gaps                    | `/etc/regolith/i3/config`     | `~/.config/regolith2/i3/config`           | i3 config partials live in `/usr/share/regolith/i3/config.d`                                       |
| Xresources                 | `/usr/share/regolith-look/default`   | `~/.config/regolith2/Xresources` | `~/.Xresources` is also loaded but intended for properties that may also be required in other desktop sessions. |
| Bar status indicators      | `/usr/share/i3xrocks/conf.d/` | `~/.config/regolith2/i3xrocks/conf.d`  | Each block has it's own file. Filename determines ordering.               |
| Picom (Compton) Compositor | `/etc/regolith/picom/config`                                     | `~/.config/regolith2/picom/config`                                                                                                            |     |
