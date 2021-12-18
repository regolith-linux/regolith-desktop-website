---
title: "Manage a To-Do List"
description: >
  Create and manage a to-do list from status bar
---

{{< hint danger >}}
NOTICE: This page was copied from the [Regolith 1.x website](https://regolith-linux.org) and has not been updated for Regolith 2.  It may contain out of date information.
{{< /hint >}}

[`td-cli`](https://github.com/darrikonn/td-cli) is a command line todo manager written in Python3 for organizing todo lists across multiple projects.

Regolith includes a status bar blocklet for accessing `td-cli` directly from the bar. It can be installed as follows:

```console
sudo apt install i3xrocks-todo
```

After installing `td-cli` you can access it via command line using `td`. The full documentation of `td-cli`'s API can be found [online at their repository](https://github.com/darrikonn/td-cli/blob/master/API.md).
For example, let's create a todo list with a group name of Regolith, set it as the default project, and then add a new task to this group:

```console
td ag regolith
td g regolith p
td a "Write a Howto for td-cli"
```

Now, if you click on the `td-cli` blocklet (on the left of the time blocklet in the figure below) a floating terminal opens up with an interactive instance of `td-cli`:

{{< img "images/tdcli.png" "The td-cli indicator on the i3 bar">}}

{{< img "images/tdcli_window.png" "The td-cli pop-out window">}}

You can set this blocklet to only show number of uncompleted tasks in the bar by setting the following key in your `Xresource` file, for example, `~/.config/regolith/Xresources`:

```console
i3xrocks.todo.uncompleted: true
```

By default, this key is set to `false`. Moreover, you can add a keybinding for accessing `td-cli` via a floating terminal by adding the following line to your `i3` config file, for example, `~/.config/regolith/i3/config`:

```console
bindsym $mod+Ctrl+d exec --no-startup-id "/usr/bin/gnome-terminal --class=floating_window -e 'td --interactive'"
```

Alternatively, you add these lines to your `i3` config file, first:

```console
set_from_resource $i3-wm.bindsym.1 i3-wm.bindsym.1 :
set_from_resource $i3-wm.bindsym.program.1 i3-wm.bindsym.program.1 :
bindsym $mod+$i3-wm.bindsym.1 exec --no-startup-id "$i3-wm.bindsym.program.1"
```

Then, add the followings to your `Xresources` file:

```console
i3-wm.bindsym.1: Ctrl+d
i3-wm.bindsym.program.1: /usr/bin/gnome-terminal --class=floating_window -e 'td --interactive'
```
