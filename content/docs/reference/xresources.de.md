---
title: "Xresources"
linkTitle: "Xresources"
weight: 7
description: >
  All Regolith `Xresources` key definitions
---

| `Xresources` Key                                   | Description                                                                                                         |
| -------------------------------------------------- | ------------------------------------------------------------------- |
| gtk.theme_name                                     | GTK Theme   |
| gtk.icon_theme_name                                | GTK Icon Theme  |
| gnome.terminal.audible-bell                        | Enables audible bell in gnome-terminal (`true / false`)                       |
| gtk.document_font_name                             | GTK Document Font Name |
| gtk.font_name                                      | General purpose font for GTK apps and the desktop |
| gtk.monospace_font_name                            | Font for monospace areas such as i3bar and the terminal 
| gnome.terminal.background-transparency-percent     | Background transparency value for gnome-terminal (`0 - 100`). See also `gnome.terminal.use-transparent-background`. |
| gnome.terminal.font                                | Font definition for gnome-terminal                                                                                  |
| gnome.terminal.scrollbar                           | Flag to enable/disable scrollbar (`never / always`)                                                            |
| gnome.terminal.use-transparent-background          | Enables transparent background in gnome-terminal (`true / false`). See also `gnome.terminal.background-transparency-percent`. |
| gnome.wallpaper                                    | GNOME Wallpaper (can be overridden in Settings)                                                                     |
| gnome.wm.theme                                     | GNOME Window Manager Theme (unused)                                                                                 |
| i3-wm.alt                                          | Key mapping for Alt key. See the [i3 User Guide](https://i3wm.org/docs/userguide.html#_using_i3) for details.       |
| i3-wm.bar.background.color                         | Bar Background Color                                                                                                |
| i3-wm.bar.position                                 | Bar Screen Position                                                                                                 |
| i3-wm.bar.separator.color                          | Color of seperator between blocks                                                                                   |
| i3-wm.bar.statusline.color                         |                                                                                                                     |
| i3-wm.bar.trayoutput                               | Enable or disable the [app tray](https://i3wm.org/docs/userguide.html#_tray_output) in i3bar                        |
| i3-wm.bar.workspace.active.background.color        |                                                                                                                     |
| i3-wm.bar.workspace.active.border.color            |                                                                                                                     |
| i3-wm.bar.workspace.active.text.color              |                                                                                                                     |
| i3-wm.bar.workspace.focused.background.color       |                                                                                                                     |
| i3-wm.bar.workspace.focused.border.color           |                                                                                                                     |
| i3-wm.bar.workspace.focused.text.color             |                                                                                                                     |
| i3-wm.bar.workspace.inactive.background.color      |                                                                                                                     |
| i3-wm.bar.workspace.inactive.border.color          |                                                                                                                     |
| i3-wm.bar.workspace.inactive.text.color            |                                                                                                                     |
| i3-wm.bar.workspace.urgent.background.color        |                                                                                                                     |
| i3-wm.bar.workspace.urgent.border.color            |                                                                                                                     |
| i3-wm.bar.workspace.urgent.text.color              |                                                                                                                     |
| i3-wm.client.focused.color.background              |                                                                                                                     |
| i3-wm.client.focused.color.border                  |                                                                                                                     |
| i3-wm.client.focused.color.child_border            |                                                                                                                     |
| i3-wm.client.focused.color.indicator               |                                                                                                                     |
| i3-wm.client.focused.color.text                    |                                                                                                                     |
| i3-wm.client.focused_inactive.color.background     |                                                                                                                     |
| i3-wm.client.focused_inactive.color.border         |                                                                                                                     |
| i3-wm.client.focused_inactive.color.child_border   |                                                                                                                     |
| i3-wm.client.focused_inactive.color.indicator      |                                                                                                                     |
| i3-wm.client.focused_inactive.color.text           |                                                                                                                     |
| i3-wm.client.unfocused.color.background            |                                                                                                                     |
| i3-wm.client.unfocused.color.border                |                                                                                                                     |
| i3-wm.client.unfocused.color.child_border          |                                                                                                                     |
| i3-wm.client.unfocused.color.indicator             |                                                                                                                     |
| i3-wm.client.unfocused.color.text                  |                                                                                                                     |
| i3-wm.client.urgent.color.background               |                                                                                                                     |
| i3-wm.client.urgent.color.border                   |                                                                                                                     |
| i3-wm.client.urgent.color.child_border             |                                                                                                                     |
| i3-wm.client.urgent.color.indicator                |                                                                                                                     |
| i3-wm.client.urgent.color.text                     |                                                                                                                     |
| i3-wm.floatingwindow.border.size                   | Window border size in pixels for floating windows                                                                   |
| i3-wm.font                                         | Window manager font                                                                                                 |
| i3-wm.gaps.inner.size                              | Default gap size between windows in pixels                                                                          |
| i3-wm.gaps.outer.size                              | Default gap size at screen edge in pixels                                                                           |
| i3-wm.mod                                          | Key mapping for Super key. See the [i3 User Guide](https://i3wm.org/docs/userguide.html#_using_i3) for details.     |
| i3-wm.window.border.size                           | Default border size in pixels                                                                                       |
| i3-wm.workspace.01.name .. i3-wm.workspace.19.name | Workspace Labels                                                                                                    |
| i3-wm.workspace.01.key .. i3-wm.workspace.10.key   | Workspace Shortucts                                                                                                 |
| i3xrocks.action.volume.left                        | Command to execute when volume indicator is left clicked (default: none)                                            |
| i3xrocks.action.volume.middle                      | Command to execute when volume indicator is middle clicked (default: none)                                          |
| i3xrocks.action.volume.right                       | Command to execute when volume indicator is right clicked (default: mute through amixer)                            |
| i3xrocks.action.volume.scrollup                    | Command to execute when scroll wheel up is used on volume indicator (default: increase volume through amixer)       |
| i3xrocks.action.volume.scrolldn                    | Command to execute when scroll wheel down is used on volume indicator (default: decrease volume through amixer)     |
| i3xrocks.error.color                               | Color for bar module in error mode                                                                                  |
| i3xrocks.label.battery0                            | Bar icon glyph                                                                                                      |
| i3xrocks.label.battery100                          | Bar icon glyph                                                                                                      |
| i3xrocks.label.battery20                           | Bar icon glyph                                                                                                      |
| i3xrocks.label.battery50                           | Bar icon glyph                                                                                                      |
| i3xrocks.label.battery80                           | Bar icon glyph                                                                                                      |
| i3xrocks.label.batteryac                           | Bar icon glyph                                                                                                      |
| i3xrocks.label.batterycharging                     | Bar icon glyph                                                                                                      |
| i3xrocks.label.batteryunknown                      | Bar icon glyph                                                                                                      |
| i3xrocks.label.capslock                            | Bar icon glyph                                                                                                      |
| i3xrocks.label.color                               | Bar icon glyph                                                                                                      |
| i3xrocks.label.cpu                                 | Bar icon glyph                                                                                                      |
| i3xrocks.label.disk                                | Bar icon glyph                                                                                                      |
| i3xrocks.label.dn                                  | Bar icon glyph                                                                                                      |
| i3xrocks.label.help                                | Bar icon glyph                                                                                                      |
| i3xrocks.label.mediapaused                         | Bar icon glyph                                                                                                      |
| i3xrocks.label.mediaplaying                        | Bar icon glyph                                                                                                      |
| i3xrocks.label.memory                              | Bar icon glyph                                                                                                      |
| i3xrocks.label.mute                                | Bar icon glyph                                                                                                      |
| i3xrocks.label.notify.error                        | Bar icon glyph                                                                                                      |
| i3xrocks.label.notify.none                         | Bar icon glyph                                                                                                      |
| i3xrocks.label.notify.some                         | Bar icon glyph                                                                                                      |
| i3xrocks.label.numlock                             | Bar icon glyph                                                                                                      |
| i3xrocks.label.off                                 | Bar icon glyph                                                                                                      |
| i3xrocks.label.on                                  | Bar icon glyph                                                                                                      |
| i3xrocks.label.sound                               | Bar icon glyph                                                                                                      |
| i3xrocks.label.thermometer                         | Bar icon glyph                                                                                                      |
| i3xrocks.label.time                                | Bar icon glyph                                                                                                      |
| i3xrocks.label.up                                  | Bar icon glyph                                                                                                      |
| i3xrocks.label.wifi                                | Bar icon glyph                                                                                                      |
| i3xrocks.label.wired                               | Bar icon glyph                                                                                                      |
| i3xrocks.nominal                                   | Default bar icon color                                                                                              |
| i3xrocks.value.color                               | Color of numerical value in bar module                                                                              |
| i3xrocks.value.font                                | Font for numerical value in bar module                                                                              |
| i3xrocks.warning                                   | Warning color for bar module                                                                                        |

# Optional `Xresources` keys

The following `Xresources` keys are undefined by default but can be used by users to change behavior as desired.

| `Xresources` Key                  | Description                                                                                                                                                                                         |
| --------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| i3-wm.gaps.focus_follows_mouse    | The window under the mouse has focus if enabled                                                                                                                                                     |
| i3-wm.program.launcher.app        | Command i3 executes from the app launcher keybinding                                                                                                                                                |
| i3-wm.program.launcher.cmd        | Command i3 executes from the command launcher keybinding                                                                                                                                            |
| i3-wm.program.launcher.window     | Command i3 executes for the window navigation keybinding                                                                                                                                            |
| i3-wm.program.help                | Command to launch from the help keybinding                                                                                                                                                          |
| i3-wm.program.file_search         | Command to launch from the file search keybinding                                                                                                                                                   |
| i3-wm.program.refresh_ui          | Command to launch from the session refresh keybinding                                                                                                                                               |
| i3-wm.program.logout              | Command to launch from the logout keybinding                                                                                                                                                        |
| i3-wm.program.reboot              | Command to launch from the reboot keybinding                                                                                                                                                        |
| i3-wm.program.shutdown            | Command to launch from the shutdown keybinding                                                                                                                                                      |
| i3-wm.program.lock                | Command to launch from the lock screen keybinding                                                                                                                                                   |
| i3-wm.program.sleep               | Command to launch from the sleep keybinding                                                                                                                                                         |
| i3-wm.program.settings            | Command to launch from the Control Panel keybinding                                                                                                                                                 |
| i3-wm.program.display             | Command to launch from the Display Settings keybinding                                                                                                                                              |
| i3-wm.program.wifi                | Command to launch from the Wifi Settings keybinding                                                                                                                                                 |
| i3-wm.program.bluetooth           | Command to launch from the Bluetooth Settings keybinding                                                                                                                                            |
| i3-wm.program.files               | Command to launch from the file browser keybinding                                                                                                                                                  |
| i3-wm.program.notification_ui     | Command to launch from the notification UI keybinding                                                                                                                                               |
| i3-wm.program.1...i3-wm.program.3 | Optional programs to start with i3                                                                                                                                                                  |
| i3xrocks.media-player.player-args | Optional arguments used by the `media-player` i3xrocks block. These arguments are fed straight into `playerctl`, eg. setting this value to `-p spotify` only makes the bar display/control spotify. |
| i3xrocks.action.mic.left | Optional command to run on left button click of microphone status indicator. |
| i3xrocks.action.mic.middle | Optional command to run on middle button click of microphone status indicator. |
| i3xrocks.action.mic.right | Override command to run on right button click of microphone status indicator. |
| i3xrocks.action.mic.scrollup | Override command to run on scroll up of microphone status indicator. |
| i3xrocks.action.mic.scrolldn | Override command to run on scroll down of microphone status indicator. |
| i3xrocks.action.volume.left | Optional command to run on left button click of microphone status indicator. |
| i3xrocks.action.volume.middle | Optional command to run on middle button click of microphone status indicator. |
| i3xrocks.action.volume.right | Override command to run on right button click of microphone status indicator. |
| i3xrocks.action.volume.scrollup | Override command to run on scroll up of microphone status indicator. |
| i3xrocks.action.volume.scrolldn | Override command to run on scroll down of microphone status indicator. |
| i3xrocks.action.disk-capacity | Override command to run on disk capacity status indicator. |
| i3xrocks.action.cpu-usage | Override command to run on cpu usage status indicator. |
| i3xrocks.action.memory | Override command to run on memory status indicator. |
| i3xrocks.action.wifi | Override command to run on wifi status indicator. |
| i3xrocks.action.weather | Override command to run on weather status indicator. |
| i3xrocks.action.media-player.left | Optional command to run on left button click of media player status indicator. |
| i3xrocks.action.media-player.middle | Optional command to run on middle button click of media player status indicator. |
| i3xrocks.action.media-player.right | Override command to run on right button click of media player status indicator. |
| i3xrocks.action.time | Override command to run on date time status indicator. |
| i3xrocks.action.battery | Override command to run on battery status indicator. |
