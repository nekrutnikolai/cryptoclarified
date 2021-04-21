---
title: "2. Ubuntu Server Install"
description: "Installing and configuring Ubuntu Server."
lead: "Installing and configuring Ubuntu Server."
date: 2021-02-10T17:15:46-05:00
lastmod: 2021-02-10T17:15:46-05:00
draft: false
images: []
menu:
  minerwrangler:
    parent: "minerwrangler"
weight: 900
toc: true
---

## Preliminary setup

- Static ip set for the rig on your router.
- Rig's bios updated to the latest version (found this [this to be helpful](https://askubuntu.com/questions/46886/how-to-create-a-bootable-usb-stick-to-flash-a-bios) for an old computer).
- Have a USB drive, keyboard, monitor, and maybe mouse handy.

## Installing to a removable media

Download the latest version of [Ubuntu Server LTS](https://ubuntu.com/download/server).

Create an installation disk with the Ubuntu Server image. I recommend using [balenaEtcher](https://www.balena.io/etcher/).

{{< img src="thumb1.jpeg" alt="thumb drive" caption="<em></em>" class="border-0" >}}

After it finishes, eject it out of your the computer, and plug it into your rig.

## Installing to the rig

Turn on the rig, and boot into bootloader mode, usually f10 or f12 for a Dell motherboard. Select USB device, and boot from that.

The USB will check it's integrity, which may take a few minutes.

{{< img src="integritycheck.jpeg" alt="integrity check" caption="" class="border-0" >}}

A series of menus will appear. **Use the arrow keys and enter key to navigate.**

{{< img src="serverwelcome.jpeg" alt="welcome screen" caption="" class="border-0" >}}

Skip through the ***Network connections***, ***Configure Proxy menus*** and ***Configure Ubuntu archive mirror*** by proceeding with enter. This will leave everything at default.

For the ***Guided storage configuration***, unless you plan to do something else with your rig, leave the defaults and use the arrow keys to reach the Done button, pressing enter to proceed.

{{< img src="guidedstorage.jpeg" alt="guided storage" caption="" class="border-0" >}}

Skip through the ***Storage configuration*** menu. Select continue at the ***Confirm destructive action*** prompt.

Next, set up the ***Profile setup***. I just called mine miner for my name, server's name, and username. Be sure to pick a *secure* password. Not the same one that you use for everything else.

{{< img src="profilesetup.jpeg" alt="profile setup" caption="" class="border-0" >}}

At the ***SSH Setup***, make sure that the Install OpenSSH server is checked. Leave the rest at default. I don't import my SSH identity.

{{< img src="sshsetup.jpeg" alt="ssh setup" caption="" class="border-0" >}}

***Featured Server Snaps***, leave all of these blank.

Finally, you will be greeted at the ***Installing system*** menu. It'll take a while, typically 10-15 minutes on my rigs, so go on a walk, grab a cup of tea, or check out [my photo gallery](https://nnekrut.netlify.app/gallery/).

Press ***reboot now*** to finish the installation. It will give you a prompt in scary red letters: ***[FAILED] Failed unmounting /cdrom.*** Remove the flash drive, **AND THE DISPLAY CABLE FROM THE GPU** and press enter to reboot.

{{< img src="removetoboot.jpeg" alt="remove to boot" caption="" class="border-0" >}}

Give it a minute, or two, or three to set up everything. It is its first boot after all.

Now you can get rid of that pesky keyboard and monitor, and put the computer in a place to heat your house, or garage.
