---
title: "Change the Default Window Gap"
description: >
  Change the pixels between windows.
---

{{< hint danger >}}
NOTICE: This page was copied from the [Regolith 1.x website](https://regolith-linux.org) and has not been updated for Regolith 2.  It may contain out of date information.
{{< /hint >}}

Like most configuration in Regolith, the i3-gaps gap size can be tuned via `Xresources` ([See here]({{< ref "/docs/Reference/xresources.md" >}}) for all Xresource definitions).

1. Create or add the following value to your `~/.config/regolith/Xresources` file:

```console
i3-wm.gaps.inner.size: 20
```

In this example we're setting the default gap to 20 pixels.

2. Reload the `Xresources` configuration:

```console
$ regolith-look refresh
```

## Further Reading

See the [reference page for configurations]({{< ref "/docs/Reference/configurations.md" >}}) for more details about config files in Regolith.
