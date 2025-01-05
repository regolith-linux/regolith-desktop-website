---
title: "How to Hide i3-bar by default"
linkTitle: "How to Hide i3-bar by default"
description: >
  Hide i3-bar by default
---

{{< hint warning >}}
Regolith version 3.0 onward replaces "i3-wm" with "wm" in Xresource keys.  The content on this page has been updated for Regolith 3.0+.  If you are using an earlier version, use "i3-wm" instead of "wm" in the key names below.  For example `wm.foo.bar` changes to `i3-wm.foo.bar` for Regolith 1.x and 2.x.
{{< /hint >}}

Add the line
```
wm.bar.mode: hide
```
to `$HOME/.config/regolith3/Xresources` file.
The next time you log in the bar should be hidden by default.
