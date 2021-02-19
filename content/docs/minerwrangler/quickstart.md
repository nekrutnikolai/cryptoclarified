---
title: "Quick Start"
description: "brief tutorial on installing and configuring MinerWrangler."
lead: "For users experienced with Linux."
date: 2021-02-10T17:07:23-05:00
lastmod: 2021-02-10T17:07:23-05:00
draft: false
images: []
menu:
  docs:
    parent: "minerwrangler"
weight: 999
toc: true
---

## Installation and configuration

SSH into your rig:

{{< btn-copy text="ssh rigusr@rigip" >}}

```bash
ssh rigusr@ipaddress
```

Obviously replace ***rigusr*** with the username of the server and the ***rigip*** with the ip of the rig.

Download and run the first installation script:

{{< btn-copy text="git clone https://github.com/NikolaiTeslovich/minerwrangler.git && cd minerwrangler && chmod +x install1.sh && sudo ./install1.sh" >}}

```bash
git clone https://github.com/NikolaiTeslovich/minerwrangler.git
&& cd minerwrangler && chmod +x install1.sh && sudo ./install1.sh
```

{{<figure src="/images/wrangler1.gif" alt="terminalgif" position="center" caption="" titlePosition="center" width="650">}}

After your rig reboots it will disconnect. SSH into it again and run the second installation script. **Select lightdm as the default display manager**:

{{< btn-copy text="cd minerwrangler && sudo ./install2.sh" >}}

```bash
cd minerwrangler && sudo ./install2.sh
```
{{<figure src="/images/wrangler2.gif" alt="terminalgif" position="center" caption="" titlePosition="center" width="650">}}

Then, after yet another reboot, run the configuration script:

{{< btn-copy text="cd minerwrangler && ./config.sh" >}}

```bash
cd minerwrangler && ./config.sh
```

{{<figure src="/images/wrangler3.gif" alt="terminalgif" position="center" caption="" titlePosition="center" width="650">}}

## Overclocking, power & fan control

Almost there! Overclock, change the power limit and fan speeds of the graphics cards by using nano to modify the clockfan.sh script to your needs:

{{< btn-copy text="nano clockfan.sh" >}}

```bash
nano clockfan.sh
```

After you are done making changes, exit with ***Ctrl-X*** followed by ***Y*** to save changes. A script to overclock is on the way.

## Start mining

At last, start mining with the mine.sh script. Don't forget to run the clockfan.sh script first to apply the overclock to the GPUs if you haven't done that already:

{{< btn-copy text="sudo ./clockfan.sh && ./mine.sh" >}}

```bash
sudo ./clockfan.sh && ./mine.sh
```

The clockfan script requires sudo permissions to overclock.

## If you have the ETHlargementPill

If you have the pill installed—*viagra* for the GTX 1080, GTX 1080Ti & TITAN Xp (GDDR5X)—you need to enter that screen and type in your sudo password (once the mine.sh script has already started):

{{< btn-copy text="screen -R pill" >}}

```bash
screen -R pill
```

Exit the screen using ***Ctrl-A*** followed by ***D***.

## See that hashrate

I'm sure you want to see your hashrate:

{{< btn-copy text="screen -R eth" >}}

```bash
screen -R eth
```

Exit the screen using ***Ctrl-A*** followed by ***D***.

## Let it be

Speaking words of wisdom, let it mine peacefully (exit the ssh session):

{{< btn-copy text="exit" >}}

```bash
exit
```

Some resources regarding screen: [How To Use Linux Screen](https://linuxize.com/post/how-to-use-linux-screen/), [Screen User's Manual](https://www.gnu.org/software/screen/manual/screen.html).
