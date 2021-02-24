---
title: "Script Install & Config"
description: "Configuration and installation of MinerWrangler."
lead: "Configuring and installing the MinerWrangler scripts."
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

Open your equivalent of Terminal. I recommend [iTerm2](https://iterm2.com/) for MacOS users.

SSH into your rig:

{{< btn-copy text="ssh rigusr@rigip" >}}

```bash
ssh rigusr@ipaddress
```

Replace ***rigusr*** with the username of the server and the ***rigip*** with the ip of the rig.

Download and run the first *MinerWrangler* install script:

{{< btn-copy text="git clone https://github.com/NikolaiTeslovich/minerwrangler.git && cd minerwrangler && chmod +x install1.sh && sudo ./install1.sh" >}}

```bash
git clone https://github.com/NikolaiTeslovich/minerwrangler.git
&& cd minerwrangler && chmod +x install1.sh && sudo ./install1.sh
```

{{<figure src="/images/wrangler1.gif" alt="terminalgif" position="center" caption="" titlePosition="center" width="650">}}

After your rig reboots it will disconnect. SSH into it again and run the second install script. **Select lightdm as the default display manager**:

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

By default, the script is setup to mine at the [ethermine.org](https://ethermine.org/) pool.

## Overclocking, power & fan control

Almost there! Overclock, change the power limit and fan speeds of the graphics cards by using nano to modify the clockfan.sh script to your needs:

{{< btn-copy text="nano clockfan.sh" >}}

```bash
nano clockfan.sh
```
I recommend experimenting with the power limit, fan speeds, memory and core clock speeds to find the **highest hash rate**, **yet efficient and stable** settings. The default speeds of +1000Mhz (+500Mhz) memory and +150Mhz core are a good starting point.

Keep in mind that for different algorithms, different overclocks work best. For instance, as Ethash (ETH) is memory-intensive, so increasing memory rather than core yields better results. KawPoW (RVN) is more core intensive, so the opposite would be true.

After you are done making changes, exit with ***Ctrl-X*** followed by ***Y*** to save changes. *A script to overclock is in the works.*

## Start mining

At last, start mining with the mine.sh script. Don't forget to run the clockfan.sh script first to apply the overclock to the GPUs if you haven't done that already:

{{< btn-copy text="sudo ./clockfan.sh && ./mine.sh" >}}

```bash
sudo ./clockfan.sh && ./mine.sh
```

The clockfan script requires sudo permissions to overclock.

## If you have the ETHlargementPill

If you have the OhGodAnETHlargementPill installed for GDDR5X GPUs, you need to enter into that screen and type in your sudo password for the memory timings to take effect:

{{< btn-copy text="screen -R pill" >}}

```bash
screen -R pill
```

Again, exit the screen using ***Ctrl-A*** followed by ***D***.

## See that hashrate

I'm sure you want to see your hashrate (and some other GPU stats):

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

## Resources

[How To Use Linux Screen](https://linuxize.com/post/how-to-use-linux-screen/), [Screen User's Manual](https://www.gnu.org/software/screen/manual/screen.html), [How to Use Nano](https://linuxize.com/post/how-to-use-nano-text-editor/).
