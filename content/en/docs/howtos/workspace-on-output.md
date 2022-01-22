---
title: "Assign a workspace to a specific Output (Display)"
description: >
  Specify that a given workspace should always be displayed on a specific monitor
---

{{< alert icon="👉" >}}
NOTICE: This page was copied from the [Regolith 1.x website](https://regolith-linux.org) and has not been updated for Regolith 2.  It may contain out of date information.
{{< /alert >}}

In order to configure i3 to assign a workspace to a given monitor, first find the device name for the monitor you wish to use with `xrandr`:

```console
$ xrandr --listmonitors
Monitors: 1
 0: +*eDP-1 1920/309x1080/173+0+0  eDP-1
```

In this case, the output name is `eDP-1`. Next add a line like this into [a staged copy of your i3 config file]({{< ref "stage-configs">}}):

```
workspace "$ws1" output DP1
```

Log back in for the changes to take effect.
