---
title: "Config Files"
linkTitle: "Config Files"
weight: 2
description: >
  General information about the config files that Regolith uses
---

| **Component**              | **Default Config**                                           | **User Config**                       | **Notes**                                                                                                                             |
| -------------------------- | ------------------------------------------------------------ | ------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------- |
| i3 / i3-gaps               | `/etc/regolith/i3/config`, `/usr/share/regolith/i3/config.d` | `~/.config/regolith2/i3`              | *Extend* Regolith2 config by creating `config.d` and partials in the user config dir, or *globally override* it by creating `config`. |
| Xresources                 | `/usr/share/regolith-look/default`                           | `~/.config/regolith2/Xresources`      | `~/.Xresources` is also loaded but intended for properties that may also be required in other desktop sessions.                       |
| Bar status indicators      | `/usr/share/i3xrocks/conf.d/`                                | `~/.config/regolith2/i3xrocks/conf.d` | Each block has it's own file. Configs loaded in filename alphabetical order.                                                          |
| Picom (Compton) Compositor | `/etc/regolith/picom/config`                                 | `~/.config/regolith2/picom/config`    |                                                                                                                                       |

{{< hint warning >}}
NOTE: Adding an i3 config file in `~/.config/regolith2/i3/config` will essentially override all Regolith configuration including Xresources and looks.
{{< /hint >}}
