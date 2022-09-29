---
title: "Customize i3 Configuration"
linkTitle: "How to Customize i3 Configuration"
weight: 1
description: >
  How to make changes to the way i3 looks and behaves.
---

# How to work with Regolith 2's defaults

The default configurations are stored in `/usr/share/regolith/i3/config.d`. These are loaded alphabetically. Then user configurations in `~/.config/regolith2/i3/config.d` are loaded, also in alphabetical order. Regolith's default configuration is built to be customized by setting `Xresources` variables, adding user configuration, and adding or removing default configurations via `apt`. For this reason, there are several approaches to customization of i3 in Regolith that can be used separately or in combination to achieve your configuration cleanly:

- Use `Xresources` to override variables, e.g. keybindings, strings, program names, colors, etc.
- Add or remove Regolith default configuration files with `apt`
- Add your own user configuration files
- Replace Regolith's configuration wholesale

## How to set an `Xresources` variable

The following configuration example (from `/usr/share/regolith/i3/config.d/80_compositor`) can be customized to load whatever compositor you want, without editing or overriding the existing i3 configuration file, by setting `$i3-wm.program.compositor`.

```
set_from_resource $i3-wm.program.compositor i3-wm.program.compositor /usr/share/regolith-compositor/init
exec_always --no-startup-id $i3-wm.program.compositor
```

To do this, simply add a line to `~/.config/regolith2/Xresources` like:

```
# Use my own home-made compositor
i3-wm.program.compositor: /usr/local/bin/my-compositor
```

Similarly, you can override other i3 options with `Xresources` based on the variable names found in `/usr/share/regolith/i3/config.d` files:

```
## Gap configuration
i3-wm.gaps.inner.size: 1

## Border configuration
i3-wm.window.border.size: 3
i3-wm.client.focused.color.child_border: #AAD3E9

## Workspace names
i3-wm.workspace.01.name: 1:FOO
```

For more, please [read a more in-depth discussion on `Xresources`]({{< ref "docs/howtos/override-xres.md" >}})

## How to uninstall a default partial

If you want to wholly replace or remove settings provided by a default partial, you can use `apt` to remove the package which provides that partial.

To identify the name of the package that provides the partial you want to remove:

```console
dpkg -S /usr/share/doc/regolith-i3-workspace-config
```

The output contains the name of the package:

```
regolith-i3-workspace-config: /usr/share/doc/regolith-i3-workspace-config
```

Validate the full list of files provided by this package so you know what you're removing:

```console
dpkg -L regolith-i3-workspace-config
```

Remove the partial:

```console
sudo apt remove regolith-i3-workspace-config
```

## How to customize a default partial

{{< hint warning >}}
WARNING: To customize only one of Regolith's default partials, you must first
ensure that the file `~/.config/regolith2/i3/config` does **not** exist. This
overrides Regolith's defaults entirely, which is incompatible with this how-to.
{{< /hint >}}

First, ensure that a directory exists for user config partials.

```console
mkdir -p ~/.config/regolith2/i3/config.d
```

Then, copy the default configuration into your user configuration directory:

```console
cp /usr/share/regolith/i3/config.d/40_workspace-config ~/.config/regolith2/i3/config.d/
```

Make your desired changes:

```console
vim ~/.config/regolith2/i3/config.d/40_workspace-config
```

Clean up the package containing the defaults:

```console
sudo apt remove regolith-i3-workspace-config
```

Finally, **restart i3 or log out and back in**.

## How to replace Regolith's defaults wholesale

If you don't want to keep any of Regolith's defaults (for example, you're an
experienced `i3` user with a complete personal config you want to use), you can
either uninstall all of Regolith's config partials, and/or create your own root
config at `~/.config/regolith2/i3/config`.
