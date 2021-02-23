---
title: "Ubuntu Server Setup"
description: "Installing and configuring Ubuntu Server."
lead: "Installing and configuring Ubuntu Server."
date: 2021-02-10T17:15:46-05:00
lastmod: 2021-02-10T17:15:46-05:00
draft: false
images: []
menu:
  docs:
    parent: "minerwrangler"
weight: 900
toc: true
---

# Still in Progress

## Preliminary setup

- Static ip set for the rig on your router.
- Rig's bios updated to the latest version (found this [this to be helpful](https://askubuntu.com/questions/46886/how-to-create-a-bootable-usb-stick-to-flash-a-bios) for an old computer).
- Have a USB drive handy.

## Installing and configuring Ubuntu Server

Download the latest version of [Ubuntu Server LTS](https://ubuntu.com/download/server).

Create an installation disk with the Ubuntu Server image. I recommend using [balenaEtcher](https://www.balena.io/etcher/).

{{<figure src="/images/thumb1.jpeg" alt="Hello Friend" position="center" caption="" titlePosition="center" width="650">}}

After it finishes, eject it out of your the computer, and plug it into your rig.

Turn on the rig, and boot into bootloader mode, usually f10 or f12 for a Dell motherboard. Select USB device, and boot from that.

The USB will check it's integrity, which may take a few minutes.

{{<figure src="/images/tutorial/integritycheck.jpeg" alt="removetoboot" position="center" caption="" titlePosition="center" width="650">}}

A series of menus will appear. **Use the arrow keys and enter key to navigate.**

{{<figure src="/images/tutorial/serverwelcome.jpeg" alt="removetoboot" position="center" caption="" titlePosition="center" width="650">}}

Skip through the **Network connections**, **Configure Proxy menus** and **Configure Ubuntu archive mirror** by proceeding with enter. For the **Guided storage configuration**, unless you plan to do something else with your rig, leave the defaults and use the arrow keys to reach the Done button. Press enter.

{{<figure src="/images/tutorial/guidedstorage.jpeg" alt="removetoboot" position="center" caption="" titlePosition="center" width="650">}}

Skip through the **Storage configuration** menu. Select continue at the **Confirm destructive action** prompt.

Next, set up the **Profile setup**. I just called mine miner for my name, server's name, and username. Be sure to pick a *secure* password. Not the same one that you use for everything else.

{{<figure src="/images/tutorial/profilesetup.jpeg" alt="removetoboot" position="center" caption="" titlePosition="center" width="650">}}

At the **SSH Setup**, make sure that the Install OpenSSH server is checked. Leave the rest at default. I don't import my SSH identity.

{{<figure src="/images/tutorial/sshsetup.jpeg" alt="removetoboot" position="center" caption="" titlePosition="center" width="650">}}

**Featured Server Snaps**, leave all of these blank.

Finally, you will be greeted at the **Installing system** menu. Go on a walk, grab a cup of tea, or check out another article on this website while you wait for it to install. **Check out my photo gallery while you're at it** It'll take a while, typically 10-15 minutes on my rigs. Press reboot now.

It will give you a prompt in scary red letters: [FAILED] Failed unmounting /cdrom. Remove the flash drive, **AND THE DISPLAY CABLE FROM THE GPU** and press enter to reboot.

{{<figure src="/images/tutorial/removetoboot.jpeg" alt="removetoboot" position="center" caption="" titlePosition="center" width="650">}}

Give it a minute, or two, or three to set up everything. It is it's first boot, afterall.

Now you can get rid of that pesky mouse, keyboard, and monitor, and put the computer in a place to heat your house. I have mine in the garage and office.
