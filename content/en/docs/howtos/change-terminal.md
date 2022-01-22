---
title: "Change the Default Terminal"
description: >
  Change which terminal Regolith loads by default
---

{{< alert icon="👉" >}}
NOTICE: This page was copied from the [Regolith 1.x website](https://regolith-linux.org) and has not been updated for Regolith 2.  It may contain out of date information.
{{< /alert >}}

The default terminal that ships with Regolith R1.4 is `gnome-terminal`, but any X terminal emulator can be used. To update Regolith to use your already installed terminal of your choice, use `update-alternatives` to specify it as default:

1. Run `update-alternatives --config x-terminal-emulator` to see all available terminals installed on your system.
2. Select the terminal you prefer.
