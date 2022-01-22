---
title: "Update packages selectively"
description: >
  Install or upgrade packages selectively from the unstable PPA
---

{{< hint danger >}}
NOTICE: This page was copied from the [Regolith 1.x website](https://regolith-linux.org) and has not been updated for Regolith 2.  It may contain out of date information.
{{< /hint >}}

You can enable the Regolith unstable PPA by adding it to your `apt` sources:

```console
$ sudo add-apt-repository ppa:regolith-linux/unstable
```

## Selective upgrades {#selective-upgrades}

It is recommended that you enable selective upgrades from the unstable PPA. This can be done by configuring your apt preferences to only allow selective installs from this PPA:

```console
cat <<EOF >/etc/apt/preferences.d/regolith-unstable-updates
# Configure apt to allow selective installs of packages from regolith unstable
Package: *
Pin: release o=LP-PPA-regolith-linux-unstable
Pin-Priority: 400
EOF
```

`apt` will now use these preferences and not update packages from the unstable PPA unless explicitly done. This can be tested with:

`# apt upgrade -s`

Now, by default, installing a package will come from the primary PPA configured on the machine (usually, that's the `release` PPA). You can see via the command `apt policy <package-name>` whether there is a version of the package available in the `unstable` as well as the `release` PPA:

```console
$ apt-cache policy i3xrocks-weather
i3xrocks-weather:
  Installed: (none)
  Candidate: 3.0.21-1
  Version table:
     3.0.29-1 400
        400 http://ppa.launchpad.net/regolith-linux/unstable/ubuntu focal/main amd64 Packages
     3.0.21-1 500
        500 http://ppa.launchpad.net/regolith-linux/release/ubuntu focal/main amd64 Packages
        500 http://ppa.launchpad.net/regolith-linux/stable/ubuntu focal/main amd64 Packages
```

However, installing the package will pull from the release PPA when it isn't explicitly installed from unstable:

```console
$ apt install i3xrocks-weather
Reading package lists... Done
Building dependency tree
Reading state information... Done
The following NEW packages will be installed:
  i3xrocks-weather
0 upgraded, 1 newly installed, 0 to remove and 0 not upgraded.
Need to get 6,360 B of archives.
After this operation, 23.6 kB of additional disk space will be used.
Get:1 http://ppa.launchpad.net/regolith-linux/release/ubuntu focal/main amd64 i3xrocks-weather amd64 3.0.21-1 [6,360 B]
Fetched 6,360 B in 0s (14.0 kB/s)
Selecting previously unselected package i3xrocks-weather.
(Reading database ... 302563 files and directories currently installed.)
Preparing to unpack .../i3xrocks-weather_3.0.21-1_amd64.deb ...
Unpacking i3xrocks-weather (3.0.21-1) ...
Setting up i3xrocks-weather (3.0.21-1) ...
```

To install the version from the unstable PPA you will need to install it like:

```console
$ apt install -t focal i3xrocks-weather
Reading package lists... Done
Building dependency tree
Reading state information... Done
The following NEW packages will be installed:
  i3xrocks-weather
0 upgraded, 1 newly installed, 0 to remove and 42 not upgraded.
Need to get 6,920 B of archives.
After this operation, 22.5 kB of additional disk space will be used.
Get:1 http://ppa.launchpad.net/regolith-linux/unstable/ubuntu focal/main amd64 i3xrocks-weather amd64 3.0.29-1 [6,920 B]
Fetched 6,920 B in 1s (10.1 kB/s)
Selecting previously unselected package i3xrocks-weather.
(Reading database ... 302563 files and directories currently installed.)
Preparing to unpack .../i3xrocks-weather_3.0.29-1_amd64.deb ...
Unpacking i3xrocks-weather (3.0.29-1) ...
Setting up i3xrocks-weather (3.0.29-1) ...
```
