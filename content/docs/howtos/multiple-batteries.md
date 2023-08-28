---
title: "Support Multiple Batteries"
description: >
  Display status of the batteries per instance
---

{{< hint danger >}}
NOTICE: This page was copied from the [Regolith 1.x website](https://regolith-linux.org) and has not been updated for Regolith 2.  It may contain out of date information.
{{< /hint >}}

Out of the box the primary battery status will be displayed in the i3-bar. For some laptops that have multiple batteries, e.g. ThinkPads, you want to have both batteries displayed:

1. [Stage your i3xrocks configuration files]({{< ref "add-remove-blocklets#customize-bar" >}}), then open `~/.config/regolith3/i3xrocks/conf.d/80_battery` in your editor of choice.
2. Find the line that pertains to the battery blocklet:

```conf
# Battery indicator
#
# Displays total percentage charge left of specified battery.
[battery]
interval=30
# instance=BAT0
```

3. List all the battery instances running on your machine by running:

```sh
ls /sys/class/power_supply/

# AC BAT0 BAT1
```

4. Update the staged config file to have a new blocklet as such:

```conf
...
# Battery indicator
#
# Displays total percentage charge left of specified battery.
[battery]
interval=30
instance=BAT0

[battery]
interval=30
instance=BAT1
```

## Further Reading

See the [reference page for configurations]({{< ref "/docs/Reference/configurations.md" >}}) for more details about config files in Regolith.
