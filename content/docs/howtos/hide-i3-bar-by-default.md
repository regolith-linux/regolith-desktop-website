---
title: "How to Hide i3-bar by default"
description: >
  Hide i3-bar by default
---

{{< hint danger >}}
NOTICE: This page was copied from the [Regolith 1.x website](https://regolith-linux.org) and has not been updated for Regolith 2.  It may contain out of date information.
{{< /hint >}}

Add the line
```
i3-wm.bar.mode: hide
```
to `$HOME/.config/regolith/Xresources` file.
The next time you log in the bar should be hidden by default.
