---
author: "Ken Gilmer"
date: 2022-2-05
linktitle: Announcing Regolith 2
title: Announcing Regolith 2
weight: 1
---

## Introduction

Regolith 1.6 is the end of the line for the existing Regolith desktop. The new major version 2 provides for a simplification of Regolith as a whole, with some new features as well.  This upgrade will not be backwards compatible with any custom configuration files in the 1.x series.  A number of changes made this major version bump a requirement, such as:

* Enable the ability to use `i3` or `i3-gaps` interchangeably
* Simplify the loading of Xresources, discovery and management of looks
* Support for i3 config partials, allowing for safer and richer extension capabilities
* Provide a package topography necessary for future changes including alternative sessions and backends
* Debian support
* New desktop executor: Ilia

However it should be noted that Regolith 2 is not radically different than the previous major version. This major version
bump is to allow for users to upgrade on their own schedules.  As such, the 1.x package repository (PPA) will not be used for Regolith 2 packages.

## Release Status

We're currently in pre-alpha phase of the development process. The environment is generally stable for day to day work, however because we're reserving the right to make big changes still, using it in a production context is not recommended at this time.

## Shipped Changes

* Convert i3 config to [partials](https://github.com/i3/i3/issues/4192)
* `conf.d` style Xresource discovery
* Migration from `rofi` to [`ilia`](https://github.com/regolith-linux/ilia) as the desktop executor
* Migration to [`nerdfonts`](https://www.nerdfonts.com/) for looks to simplify and enhance font icons
* A [new build system](https://github.com/regolith-linux/voulage) decoupled from `launchpad.net` facilitating easier and more consistent distro development
* Port of looks `lascaille` and `nord` from the 1.x looks

## Changes in Development
* New website (this one!)
* [Polish](https://github.com/regolith-linux/ilia/issues) for `ilia`
* Bugs in wallpaper handling (gnome/dotfiles)
* Better HiDPI support out of the box
* Better first time user experience
* Porting most existing looks to new Xresource schema
* Rebranding from "Regolith Linux" to "Regolith Desktop Environment"

## Expected Release Date

Due to the volunteer nature of the Regolith project, it's simply not possible to a promise ship date.  However, we would like to have something usable by the time of the next LTS version of Ubuntu is released, in April 2022.

## Learn More

[See here for details](http://regolith-desktop.com/#get-regolith-20) on how to install the current pre-release version of Regolith 2, and [here for information on how you can provide feedback or contribute](http://regolith-desktop.com/#get-regolith-20).
