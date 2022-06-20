---
title: "2.1 Release Notes"
linkTitle: "2.1 Release Notes"
weight: 1
description: >
  Release notes for Regolith 2.1
---

Regolith 2.1 is a minor release including several improvements, bug fixes, and optimizations.

## New Features

* Regolith Linux 2.1 (based from Ubuntu 22.04)
* User-contributed look `dracula` added
* Looks can be loaded from user directories (`~/.config/regolith2/looks`)

## Bug Fixes

* Ilia's file search dialog was broken on Jammy, this has been fixed
* `PtrSc` hotkeys working as in 1.6
* Numerous small fixes listed below

## Known Issues

* No localization for `ilia` 
* Inconsistent GTK theme in some dialogs

## Changelog Delta from Regolith Desktop 2.0 to 2.1 Beta 1

### Changes in `regolith-lightdm-config`:
```
0910bd8 Add all configuration items to slick-greeter file
e95bd47 move from gtk greeter to slick. Update background
```

### Changes in `regolith-session`:
```
d2bee02 Add ability to stage looks in user directory ~/.config/regolith2/looks
ac6eb70 Check if user's directory does not exist before appending
```

### Changes in `regolith-look-default`:
```
589b264 Specify glyph for app laucher. Better glyph for help
```

### Changes in `regolith-look-extra`:
```
a600730 Specify glyph for app laucher. Better glyph for help
b3e6295 Add dracula look by @jjsearle
92f844a s/nord/nevil in composer-init
```

### Changes in `regolith-i3xrocks-config`:
```
56ed590 move dynamic block window-name to the left-most position due to horizontal variance
ce6cebd Remove unneeded script for app launch action
86abc8c Load ilia over remontoire for help action
d400913 Adding a fix to not show anything on empty workspace (#129)
25fd18d Add support for bond interface in net-traffic (#128)
```

### Changes in `regolith-desktop`:
```
cdf0b4c Bump dist version
```

### Changes in `remontoire`:
```
ab00f14 Fix version returned by program to match package version
```

### Changes in `ilia`:
```
64943d8 Remove unused dependency, causing errors on ISO release
157df07 Remove default sorting of items from textlist page
```

### Changes in `plymouth-theme-regolith`:
```
b14a39f Use final logo image
```
