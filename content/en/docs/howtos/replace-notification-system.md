---
title: "Change Notification Systems"
description: >
  Disable Rofication and add another notification system
---

{{< alert icon="👉" >}}
NOTICE: This page was copied from the [Regolith 1.x website](https://regolith-linux.org) and has not been updated for Regolith 2.  It may contain out of date information.
{{< /alert >}}

Regolith ships with a notification system called [Rofication](https://github.com/DaveDavenport/Rofication). It is designed to work in the background and not use pop-ups as a way of alerting the user to a new notification. Rather, a small bar item displays the current number of unread notifications and a dialog can activated to interact with the content of the current notifications. This page describes a way to install an alternative notification system which works in a more traditional way.

We will use [dunst](https://dunst-project.org/) as an example but similar steps can be used with pretty much any other notification component.

1. Replace `rofication` with `dunst`:

```console
$ sudo apt install dunst
$ sudo apt purge regolith-rofication
```

2. Log out and back in.
3. Test your notifications with `notify-send test123`. You should see a pop-up notification from `dunst`.
