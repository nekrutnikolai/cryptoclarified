---
title: "Tutorial"
description: "An in-depth MinerWrangler tutorial for Linux novices."
lead: "An in-depth MinerWrangler tutorial for Linux novices."
date: 2021-02-10T17:15:46-05:00
lastmod: 2021-02-10T17:15:46-05:00
draft: false
images: []
menu:
  docs:
    parent: "minerwrangler"
weight: 999
toc: true
---

# Still in Progress

## Preliminary setup

- Static ip set for the rig.
- Rig's bios updated to the latest version (found this [this to be helpful](https://askubuntu.com/questions/46886/how-to-create-a-bootable-usb-stick-to-flash-a-bios) for an old computer).
- Have a USB drive handy.

## Installing and configuring Ubuntu Server

Download the latest version of [Ubuntu Server LTS](https://ubuntu.com/download/server).

Create an installation disk with the Ubuntu Server image. I recommend using [balenaEtcher](https://www.balena.io/etcher/).

{{<figure src="/images/thumb1.jpeg" alt="Hello Friend" position="center" caption="" titlePosition="center" width="640">}}

After it finishes, eject it out of your the computer, and plug it into your rig.

Turn on the rig, and boot into bootloader mode, usually f10 or f12 for a Dell motherboard. Select USB device, and boot from that.

The USB will check it's integrity, which may take a few minutes.

A series of menus will appear. Use the arrow keys and enter key to navigate. Leave everything as default until   and ask you your language, hit enter. Next, the keyboard layout, proceed to the next screen by pressing enter.

Skip through the **Network connections**, **Configure Proxy menus** and **Configure Ubuntu archive mirror** by proceeding with enter. For the Guided storage configuration, unless you plan to do something else with your rig, leave the defaults and use the arrow keys to reach the Done button. Press enter. Skip through the **Storage configuration** menu. Select continue at the **Confirm destructive action** prompt.

Next, set up the **Profile setup**. I just called mine miner for my name, server's name, and username. Be sure to pick a *secure* password. Not the same one that you use for everything else.

At the **SSH Setup**, make sure that the Install OpenSSH server is checked. Leave the rest at default. I don't import my SSH identity.

**Featured Server Snaps** leave all of these blank.

Finally, you will be greeted at the **Installing system** menu. Go on a walk, grab a cup of tea, or check out another article on this website while you wait for it to install. **Check out my photo gallery while you're at it** It'll take a while, typically 10-15 minutes on my rigs. Press reboot now.

- [ ] It will give you a prompt in scary red letters: [FAILED] Failed unmounting /cdrom. Remove the flash drive, **AND THE DISPLAY CABLE FROM THE GPU** and press enter to reboot.

Give it a minute, or two, or three to set up everything. It is it's first boot, afterall.

Now you can get rid of that pesky mouse, keyboard, and monitor, and put the computer in a place to heat your house. I have mine in the garage and office.

## Remote setup and installation

Open your equivalent of the Terminal. I recommend iTerm for mac users, but the plain Terminal should work just fine.

Paste this into the terminal:

{{< btn-copy text="ssh <usr>@<ip>" >}}

```bash
ssh <usr>@<ip>
```

In the terminal, type.

If it prompts you about if you actually want to connect to it, type yes.

Type in your rig's passwd to connect.

Next, while connected to your rig, paste in this piece of code and hit enter:

{{< btn-copy text="git clone https://github.com/NikolaiTeslovich/minerwrangler.git && cd minerwrangler && chmod +x install1.sh && sudo ./install1.sh" >}}

```bash
git clone https://github.com/NikolaiTeslovich/minerwrangler.git
&& cd minerwrangler && chmod +x install1.sh && sudo ./install1.sh
```

Trouble-shooting: `ps aux | grep auth`

`cd minerwrangler && sudo ./install2.sh`

`cd minerwrangler && sudo ./config.sh`

This thread was very helpful aswell: https://gist.github.com/bsodmike/369f8a202c5a5c97cfbd481264d549e9
