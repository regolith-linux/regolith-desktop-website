---
title: "Change the Bar Date and Time Format"
linkTitle: "Change the Bar Date and Time Format"
description: >
  Change the date/time format used in the bar
---

{{< hint danger >}}
NOTICE: This page was copied from the [Regolith 1.x website](https://regolith-linux.org) and has not been updated for Regolith 2.  It may contain out of date information.
{{< /hint >}}

The time format (12 or 24 hour) can be specified in Settings:

{{< img "images/regolith-screenshot-settings-time-format.png" "">}}

The date format can be specified by selecting the appropriate region in Settings. A preview of the date format is provided, and logging back in is required for changes to take effect.

{{< img "images/regolith-screenshot-settings-region.png" "">}}

The date and time formats can also be explicitly set via `Xresources`. To do so, override the `i3xrocks.date.format2` `Xresource` key. The format specification for date is simply the arguments that would be passed to the `date` command on the command line. For example, to print the year in 4 digits, specify `+%Y`.

For example the following line can be added to use the `YYYY-MM-DD hh:mm` format:
`i3xrocks.date.format2: %Y-%m-%d %H:%M`

The complete format that is support is as follows:

-   `%Y` prints year as `YYYY`
-   `%y` prints year as `YY`
-   `%m` prints month as `MM`
-   `%m` prints minute as `mm`
-   `%H` prints hours in 24 hour format
-   `%I` prints hours in 12 hour format
