---
title: "Change Workspace Icons and Labels"
description: >
  Learn how to customize each workspace in the bar
---

{{< hint danger >}}
NOTICE: This page was copied from the [Regolith 1.x website](https://regolith-linux.org) and has not been updated for Regolith 2.  It may contain out of date information.
{{< /hint >}}

Adding icons to workspaces can give your desktop a nice and functional look.

### Finding icons

Icons are actually characters from fonts installed by Regolith looks. Each look comes with a specific icon font. The icon font is defined in the `typeface_bar` variable in the `typeface` config file. For example, the look "Cahuella" uses the _Material Design Icons_ font (see file `/etc/regolith/styles/cahuella/typeface`).

You can browse the icon font using the [Gnome Character Map](https://wiki.gnome.org/action/show/Apps/Gucharmap?action=show&redirect=Gucharmap) application from the `gucharmap` package:

1. Open "Gnome Character Map".
2. Select your icon font in the top left combo.
3. In the _script_ pane select _Common_.
4. Scroll down the characters pane until you find the icons.
5. Double click on the icon you are looking to use and press the _Copy_ button (bottom right).

**Tip:** the icons are ordered alphabetically.

### Changing Icons

Follow these steps to override the default workspace label with your own:

1. Find the character you want to use and copy to the clipboard. This example will use the Sigma glyph from Material Design Icons font ().
2. Add a line to your `Xresources` overrides file with the workspace number and character you wish to use:

```console
$ echo "i3-wm.workspace.06.name: 6:" >> ~/.config/regolith/Xresources
```

3. Refresh your UI:

```console
$ regolith-look refresh
```

In i3, workspace labels are only updated when a workspace is created. Ensure you're creating an new workspace 6 if following the example above:

{{< img "images/regolith-bar-icon.png" "Icons on the i3 bar" >}}

### Changing Labels

The same approach can be used to specify textual descriptions of your workspaces. For example, adding the following lines to your `~/.config/regolith/Xresources` file will change the first three workspaces:

```
i3-wm.workspace.01.name: 1: Terminal
i3-wm.workspace.02.name: 2: Web
i3-wm.workspace.03.name: 3: Chat
```

### Adding support for icon fonts in text editors

#### Atom

- Append the name of the icon font to `Settings > Editor > Font Familly`.
- Example: `Menlo, Consolas, DejaVu Sans Mono, monospace, Material Design Icons`

# Further Reading

See the [reference page for configurations]({{< ref "/docs/Reference/configurations.md" >}}) for more details about config files in Regolith.
