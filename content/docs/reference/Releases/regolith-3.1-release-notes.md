---
title: "3.1 Release Notes"
linkTitle: "3.1 Release Notes"
weight: 2
description: >
  Release notes for Regolith 3.1
---

# Regolith 3.0 Release Notes

[Regolith 3.0](https://github.com/orgs/regolith-linux/projects/26) is a minor release focusing on Ubuntu 23.10 support.

## New Major Features

* Ubuntu 23.10 (manic) support

## Changelog Delta from Regolith 3.0


## Changes in `regolith-session`:
```
8f5da99 fix: set XDG_CURRENT_DESKTOP for wayland session (fixes screencasting)
```


## Changes in `regolith-wm-config`:
```
8e47c87 Merge pull request #10 from regolith-linux/fix-rofication-dep
9b1706d Move default-style to soft dep for both sessions.  demote 3 more for sway session to soft per PR feedback
d21c32c fix: remove (redundant) hard dependency from sway session to rofication. Soft dependency comes via regolith-wm-config.
```

## Changes in `sway-audio-idle-inhibit`:
```
162c01f chore: bump libwlroots dependency version
```

