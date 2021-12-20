---
title: "Basic Usage"
weight: 3
description: >
  Learn the most important parts of Regolith first.
---

While we'll cover everything in greater detail in other areas of the documentation, this page covers the very basics.

## The Super Key

Most keybindings you'll be using with Regolith start with the {{< keys "super" >}} key. This key typically says "WIN" or has a MS Windows logo on it. On a Mac it is the Command {{< keys "⌘" >}} key. Going forward, this key will simply be referred to as {{< keys "super" >}} but keep in mind that you can change which physical button {{< keys "super" >}} maps to in your configuration if you choose to.

## Launchers

Regolith provides several launchers as the primary way of interacting with your system. Each of these launchers has a consistent look and feel but provides access to a specific entity. Default launchers are provided for applications {{< keys "super,space" >}}, commands {{< keys "super,shift,space" >}}, notifications {{< keys "super,n" >}}, windows {{< keys "super,ctrl,space" >}}, and files {{< keys "super,alt,space" >}}.

### Launch an Application

After logging in, you'll be at a blank screen with the bar at the bottom and some keyboard shortcuts on the right. To launch an application, press {{< keys "super,space" >}} and a menu will be presented with all of the applications installed on the system. If you begin typing the name of the application you wish to launch, the list will filter down to only matching names. You can also scroll through the list with the arrow keys.

![](/regolith-ilia-apps.png)

### Navigate to a Window

To focus on a running application, the {{< keys "super,ctrl,space" >}} keybinding can be used to show a dialog of all running windows. Simply select the desired window and the system will move to the window's containing workspace and set its focus.

![](/regolith-ilia-windows.png)

### Create a new Workspace

Workspaces (also known as virtual desktops in some desktop environments) are the primary way by which windows can be managed. Each workspace provides a screen for an independent set of windows. To create a workspace, {{< keys "super,`" >}} will create and move to a new workspace. {{< keys "super,0-9" >}} allows for navigation to specific workspaces.

### Find and Launch a File

Searching your local computer for a specific file can be achieved in a variety of ways. Regolith provides a file search dialog via {{< keys "super,alt,space" >}} to quickly seek and optionally load a file with its default application. If the file path exceeds the width of the dialog, {{< keys "alt,." >}} will toggle text justification. Pressing enter on a selection will cause the file to be invoked with the `xdg-open` command.

![](/regolith-ilia-files.png)

### Terminal

The terminal is a special application that has its own keybinding, {{< keys "super,enter" >}}.

### Browser

The preferred browser is also special and can be launched with {{< keys "super,shift,enter" >}}.

## Quit an Application

{{< keys "super,shift,q" >}} will quit the focused application. For misbehaving apps, {{< keys "super,alt,q" >}} will force quit the focused application, but note that any unsaved data will likely be lost.

## Switching Workspaces

A primary way of managing how applications occupy the screen is by the usage of workspaces. A workspace is in essence a group of zero or more applications that all present windows on the same virtual display. Users can switch workspaces to "gain" more space for applications to occupy. Windows can be moved across workspaces. Workspaces can be tied to physical display or be moved to other displays as needed. To switch workspaces, hold down the {{< keys "super" >}} key and press one of the number keys. This will navigate to that workspace. If any windows exist in a given workspace, it will show in the bar as being active. Thus, by referring to the bar the user can know in which workspaces active applications live.

Workspaces can also be paged forward and backward via {{< keys "super,tab" >}} and {{< keys "super,shift,tab" >}}.

## Configuring the System

The Settings app (also known as `gnome-control-center`) is the primary interface for common configuration tasks, such as changing the desktop wallpaper, configuring WiFi and Bluetooth, configuring app associations and setting up users. The app can be launched via the {{< keys "super,c" >}} keybinding or from the launcher via the Settings app.

![](/regolith-gnome-settings.png)

## View Keybindings

All keybindings used by the Regolith desktop can be viewed, sorted, and executed by `ilia`.  This dialog is launched with {{< keys "super,shift,?" >}}.

![](/regolith-ilia-keybindings.png)
