---
title: "Config Files"
linkTitle: "Config Files"
weight: 2
description: >
  General information about the config files that Regolith uses
---

# Config file quick reference

| **Component**              | **Default Config**                                           | **User Config**                       | **Notes**                                                                                                                             |
| -------------------------- | ------------------------------------------------------------ | ------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------- |
| i3 / i3-gaps               | `/etc/regolith/i3/config`, `/usr/share/regolith/i3/config.d` | `~/.config/regolith2/i3`              | *Extend* Regolith2 config by creating `config.d` and partials in the user config dir, or *globally override* it by creating `config`. |
| Xresources                 | `/usr/share/regolith-look/default`                           | `~/.config/regolith2/Xresources`      | `~/.Xresources` is also loaded but intended for properties that may also be required in other desktop sessions.                       |
| Bar status indicators      | `/usr/share/i3xrocks/conf.d/`                                | `~/.config/regolith2/i3xrocks/conf.d` | Each block has it's own file. Configs loaded in filename alphabetical order.                                                          |
| Picom (Compton) Compositor | `/etc/regolith/picom/config`                                 | `~/.config/regolith2/picom/config`    |                                                                                                                                       |

{{< hint warning >}}
WARNING: Adding an i3 config file in `~/.config/regolith2/i3/config` will essentially override all Regolith configuration including Xresources and looks.
{{< /hint >}}


# History

{{< hint info >}}
NOTE: Under the Diataxis documentation framework, I think this would be more of a "discussion". Is this site using Diataxis?
{{< /hint >}}

## Config partials

Regolith 2.0 adds support for config partials, as this feature only came to `i3` itself recently in [4.20](https://i3wm.org/downloads/RELEASE-NOTES-4.20.txt). This is done by [includes](https://i3wm.org/docs/userguide.html#include). The root Regolith configuration file at `/etc/regolith/i3/config` loads partials like so:

```
# Include any regolith i3 partials
include /usr/share/regolith/i3/config.d/*

# Include any user i3 partials
include $HOME/.config/regolith2/i3/config.d/*
```

This support for partials enables Regolith 2.0's use of the package manager to add or remove default configurations.  By installing and removing packages, i3 configuration can be customized for specific preferences while still allowing to track upstream changes for aspects of the configuration that need not vary.
