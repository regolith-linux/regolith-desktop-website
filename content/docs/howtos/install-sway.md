---
title: "Install the Sway Compositor"
description: >
  Upgrade to the Wayland-based Regolith session
---

To install the wayland session, follow these steps:

1. Install the `regolith-session-wayland` package and it's dependencies. 
2. Reboot
3. Select "Regolith on Wayland" session in the login panel

## Notes

1. The wayland session uses [`i3status-rs`](https://github.com/greshake/i3status-rust) rather than `i3xrocks`.  `i3status-rs` provides a crisper and more resource-efficient approach to system monitoring.  However at this time the i3xrocks packages for status indicators are not integrated with i3status-rs.  You must configure it using the [upstream project documentation](https://docs.rs/i3status-rs/latest/i3status_rs/blocks/index.html).