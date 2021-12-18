---
title: "Override Xresources"
description: >
  Learn how to stage user copies of Regolith configuration files
---

{{< hint danger >}}
NOTICE: This page was copied from the [Regolith 1.x website](https://regolith-linux.org) and has not been updated for Regolith 2.  It may contain out of date information.
{{< /hint >}}

Regolith relies on the [Xresources system](https://en.wikipedia.org/wiki/X_resources) to provide a consolidated interface configuration. By changing `Xresources` values, Regolith can be customized in ways such as updating the user interface, specifying custom behaviors, or defining a specific format for some of the blocklets on the bar.

{{< hint info >}}
In Regolith, `Xresources` values can be changed via two methods: supplying your own `Xresources` files, and overriding the existing `Xresources` values. The latter approach is strongly recommended, as it makes upgrading to newer versions of Regolith less likely to break your customizations. If you copy the `Xresources` tree completely you'll need to integrate any breaking changes in future versions manually.
{{< /hint >}}

## Initialization

When a Regolith session is started, Xresources are loaded in the following order:

| File                            | Optional | Notes                                                                             |
| ------------------------------- | -------- | --------------------------------------------------------------------------------- |
| `~/.Xresources`                 | Y        | Intended for non-Regolith settings                                                |
| `~/.Xresources-regolith`        | Y        | A global override to replace all Regolith settings                                |
| `/etc/regolith/styles/root`     | N        | The default Regolith `Xresources` file if `~/.Xresources-regolith` does not exist |
| `~/.config/regolith/Xresources` | Y        | Applies specific overrides to `Xresources` defaults                               |

It is recommended to use `~/.config/regolith/Xresources` for customization as it doesn't require the specification of redundant settings and is easier to maintain over time.

## Determining which values can be changed

The `xrdb` tool can be used to list the existing `Xresources` values. [There is a number of existing overrides]({{< ref "/docs/Reference/xresources.md" >}}) in the R1.4.1 release:

```console
$ xrdb -query
[...]
gnome.icon.theme:	Moka
gnome.terminal.font:	JetBrains Mono 12
gnome.terminal.scrollbar:	never
gnome.wallpaper:	/usr/share/backgrounds/ESP_016895_1525_desktop.jpg
gnome.wm.theme:	Ayu-Mirage-Dark
[...]
```

## Examples

Note that the commands presented below append text to a file, so running the command more than once will result in duplicate entires.

### Example - Update the UI for High DPI Screens

By using the `~/.config/regolith/Xresources` override file, we will only need to specify the values we wish to change. The `xrdb` tool can be used to determine what current values are set to.

1. Create or add the following value to your `~/.config/regolith/Xresources` file:

```console
Xft.dpi: 192
```

2. Reload the `Xresources` configuration:

```console
$ regolith-look refresh
```

3. Open a new terminal to see the change take effect.

`192` is just an example value, please adjust as needed.

### Example - Change i3 bar position

```console
$ xrdb -query | grep position
i3-wm.bar.position:	bottom
$ echo "i3-wm.bar.position:	top" >> ~/.config/regolith/Xresources
$ regolith-look refresh
```

### Example - Change GTK Theme

```console
$ xrdb -query | grep gtk
gnome.gtk.theme:	Ayu-Mirage-Dark
$ echo "gnome.gtk.theme:	Adwaita" >> ~/.config/regolith/Xresources
$ regolith-look refresh
```

### Example - Disable the System Tray

```console
$ echo "i3-wm.bar.trayoutput:	none" >> ~/.config/regolith/Xresources
$ regolith-look refresh
```

### Example - Use Alt instead of Win as Super

```console
$ echo "i3-wm.mod: Mod1" >> ~/.config/regolith/Xresources
$ echo "i3-wm.alt: Mod4" >> ~/.config/regolith/Xresources
```

Then Reload i3 for the change to take effect (on Regolith 1.5+ there is an active regression here with a [temporary fix in the issue](https://github.com/regolith-linux/regolith-desktop/issues/504))

### Example - Launch `nm-applet` when i3 starts

Some users prefer to use the `nm-applet` program to configure and manage their wireless network (from Regolith 1.5 onwards `nm-applet` is run by default in the background). i3 config file can be updated to launch any arbitrary program at start time. But, rather than copying the whole file, we can supply up to 3 programs via Xresources without having to change the i3 config file. For this to work, also make sure that the system tray is enabled (see above).

```console
$ echo "i3-wm.program.1: /usr/bin/nm-applet" >> ~/.config/regolith/Xresources
```

This change requires you to log back in before the change takes effect.

# Further Reading

See the [reference page for configurations]({{< ref "/docs/Reference/configurations.md" >}}) for more details about config files in Regolith.
