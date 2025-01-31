---
title: "Minimal Ubuntu Install"
linkTitle: "Minimal Ubuntu Install"
description: >
  Install Regolith on Ubuntu Server
---

# Minimal Ubuntu Install

This page describes how to install the Regolith Desktop into Ubuntu Server.  This approach produces a minimal setup as many of the standard GNOME desktop packages present in a desktop install will be avoided.

# Steps

## 1. Install Ubuntu Server

Follow online instructions for installing a fresh copy of Ubuntu Server versions either 20.04 or 22.04.

## 2. Add Regolith's package key and apt repository

Once Ubuntu Server has been installed, log into a terminal session.  Use the following URLs to download the installation directions as a text file:

Ubuntu 24.10: https://regolith-desktop.com/install-release-ubuntu-24.10-amd64.txt  
Ubuntu 24.04: https://regolith-desktop.com/install-release-ubuntu-24.04-amd64.txt  
Ubuntu 22.04: https://regolith-desktop.com/install-release-ubuntu-22.04-amd64.txt  
Ubuntu 20.04: https://regolith-desktop.com/install-release-ubuntu-20.04-amd64.txt  

Debian 12: https://regolith-desktop.com/install-release-debian-12-amd64.txt  
Debian 11: https://regolith-desktop.com/install-release-debian-11-amd64.txt  

Example:

```console
wget https://regolith-desktop.com/install-release-ubuntu-22.04-amd64.txt
cat install-release-ubuntu-22.04-amd64.txt
```

Manually execute each step in the text file, or source the file if you're feeling adventurous.  Once complete, the Regolith Desktop package repositories are installed into the new system.

## 3. Install the Regolith Ubuntu System

There is a special package that is used in the ISO that can also be used in a minimal install such as this: `regolith-system-ubuntu`.  This package includes extra branding not used in typical desktop installs which may share multiple desktop environments.  Run the following command to install Regolith Desktop and all of it's dependencies:

```console
sudo apt install regolith-system-ubuntu
```

## 4. Reboot

Once the system boots back up, the `lightdm` login manager will allow you to log into your new Regolith environment.
