---
title: "Find and Install Packages"
linkTitle: "Find and Install Packages"
description: >
  Search for packages and install them on your system.
---

{{< callout type="error" >}}
NOTICE: This page was copied from the [Regolith 1.x website](https://regolith-linux.org) and has not been updated for Regolith 2.  It may contain out of date information.
{{< /callout >}}

Regolith is a Debian-based system. Debian packaging tools can be used to find and install packages.

# Find package via the command line

The `apt` command can be used to query installed or all packages:

```console
$ apt list --installed <package name> # finds installed packages
$ apt list <package name> # finds all packages
```

For example, to list all official Regolith looks that could be installed, run:

```console
$ apt list regolith-look-*
...
```

To see which status indicators are installed on your system, run:

```console
$ apt list --installed i3xrocks-*
```

# Install packages via the command line

To install packages via the command line, again we can us the `apt` command, but must use sudo to gain the rights necessary for installation:

```console
$ sudo apt install <package name>
```

To install the battery status indicator, run:

```console
$ sudo apt install i3xrocks-battery
```

# Find and Install Packages via GUI app

There are a number of apps that can provide a nice window interface on top of the apt packaging system, for example `synaptic`. Refer to the documentation for the tool of your choice to learn how to search for and install packages.
