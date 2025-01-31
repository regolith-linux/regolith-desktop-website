---
title: "Minimal Ubuntu Install"
linkTitle: "Minimal Ubuntu Install"
description: >
  Install Regolith on Ubuntu Server
---

This page describes how to install the Regolith Desktop into Ubuntu Server.  This approach produces a minimal setup as many of the standard GNOME desktop packages present in a desktop install will be avoided.

## Steps

### Install Ubuntu Server

Follow online instructions for installing a fresh copy of Ubuntu Server versions either 20.04 or 22.04.

### Add Regolith's package key and apt repository

Once Ubuntu Server has been installed, log into a terminal session.  Use the following URLs to download the installation directions as a text file:

Ubuntu 22.04: https://regolith-desktop.com/install-release-ubuntu-22.04-amd64.txt

Ubuntu 20.04: https://regolith-desktop.com/install-release-ubuntu-20.04-amd64.txt

Example:

```bash
wget https://regolith-desktop.com/install-release-ubuntu-22.04-amd64.txt
cat install-release-ubuntu-22.04-amd64.txt
```

Manually execute each step in the text file, or source the file if you're feeling adventurous.  Once complete, the Regolith Desktop package repositories are installed into the new system.

### Install the Regolith Ubuntu System

There is a special package that is used in the ISO that can also be used in a minimal install such as this: `regolith-system-ubuntu`.  This package includes extra branding not used in typical desktop installs which may share multiple desktop environments.  Run the following command to install Regolith Desktop and all of it's dependencies:

```bash
sudo apt install regolith-system-ubuntu
```

### Reboot

Once the system boots back up, the `lightdm` login manager will allow you to log into your new Regolith environment.
