---
title: "Configuration"
linkTitle: "Configuration"
weight: 4
description: >
  Make changes to the way Regolith looks and behaves.
---

{{< hint danger >}}
NOTICE: This page was copied from the [Regolith 1.x website](https://regolith-linux.org) and has not been updated for Regolith 2.  It may contain out of date information.
{{< /hint >}}

## Wallpaper

The wallpaper can be changed via Settings, or {{< keys "super,c" >}}, by going to the Background tab and selecting the preferred image or color.

{{< img "images/regolith-screenshot-settings-wallpaper.png" "The background selection in the Settings app">}}

Wallpaper can also be set via [dotfiles](https://en.wikipedia.org/wiki/Hidden_file_and_hidden_directory) for those that prefer file-based configuration management over GSettings.

Regardless of which style you prefer, you can refer to the [more extensive documentation]({{< ref "/docs/howtos/configure-wallpaper.md" >}}) for additional details.

## Status Bar Indicators

Status indicators such as CPU load, date and time, notifications, weather, and other system info can be added or removed by installing packages. For example, to show a status indicator for your laptop battery, simply run `sudo apt install i3xrocks-battery` and then refresh the session using `regolith-look refresh`. To find what indicators are available, run `apt search ^i3xrocks-` or search for `i3xrocks-` in your favorite package manager GUI, such as [Synaptic](https://help.ubuntu.com/community/SynapticHowto). There is [more documentation available]({{< ref "/docs/howtos/add-remove-blocklets.md" >}}) for configuring status indicators, also called "blocklets".

{{< img "images/regolith-screenshot-synaptic-search.png" "Searching for blocklets in Synaptics" >}}

## Looks

Colors, wallpaper, window and bar layouts and other visual factors are bundled together in Regolith and called "looks". Looks provide a simple way of changing the entire look of the desktop with a few commands. Like status bar indicators, looks are packaged and are installed and removed like any other software package. By convention, Look packages use the following naming format `regolith-look-<name>`. `apt` or a GUI package manager can be used to search for available looks. The tool `regolith-look` can be used to change looks and refresh the active session with the selected look. Here's an example that switches to the `cahuella` look that shipped by default in Regolith 1.3:

```console
$ apt search ^regolith-look-
[...]
regolith-look-cahuella/bionic,now 2.4.9 amd64
[...]
$ sudo apt install regolith-look-cahuella
$ regolith-look set cahuella
$ regolith-look refresh
```

Installed Looks may also be set via the Look Dialog, activated via {{< keys "super,alt,l" >}}.

## Keybindings

The most common keybinding change is the {{< keys "super" >}} key. Regolith uses `Xresources` as the canonical source of truth for settings, which are read by various UI components. The table of `Xresources` keys open to user configuration [is available elsewhere]({{< ref "xresources" >}}). To change the default {{< keys "super" >}} binding from the "windows" key to "alt", add the following line to the file `~/.config/regolith/Xresources`:

```toml
i3-wm.mod: Mod1
i3-wm.alt: Mod4
```

To change other, more advanced keybindings, creating a user copy of the i3 config file is necessary. We call this process ["staging"]({{< ref "/docs/howtos/stage-configs" >}}).

**Note**: GNOME also has it's own set of keybindings. When the Regolith session is first initialized, the conflicting GNOME keybindings are removed from the user settings. GNOME keybindings can be managed in the Settings app.

{{< img "images/regolith-screenshot-settings-keybindings.png" "GNOME keybindings in the settings dialog">}}

## Window Behavior

Regolith uses an i3 window manager variant called [`i3-gaps`](https://github.com/Airblader/i3). It controls how windows are drawn, how keybindings are configured, some start-up applications and other details. By default, the Regolith configuration file for i3 is located at `/etc/regolith/i3/config`.

## Almost Everything Else

The Settings app, or `gnome-control-center` as it's also known, is the tool to configure locale, date, displays, networking and various other settings. Launch it via the app launcher with {{< keys "super,space" >}}, type `settings`, and hit enter to launch the app. The direct keybinding is {{< keys "super,c" >}}.

## Further Reading

To dig deeper, find which [Howtos]({{< ref "howtos" >}}) are available, or read the [Xresources reference]({{< ref "docs/Reference/xresources.md" >}}). Become an i3 power user by reading their [user guide](https://i3wm.org/docs/userguide.html).
