---
title: "1. Introduction"
description: "Summary of MinerWrangler"
lead: "A headless driver installer & crypto miner configurator"
date: 2020-11-16T13:59:39+01:00
lastmod: 2020-11-16T13:59:39+01:00
draft: false
images: []
menu:
  docs:
    parent: "minerwrangler"
weight: 110
toc: true
---

{{< img src="minerwrangler.png" alt="MinerWrangler logo" caption="<em>Get it? It's headless!</em>" class="border-0" >}}

MinerWrangler is the ultimate bundle of bash scripts to ease your way into cryptocurrency mining that is open-source and gives you full control over your rigs—by default. No monitor, keyboard, or mouse required. Only NVIDIA support for now.

## Features

- [x] Simple and intuitive to use
- [x] One line to install
- [x] Full control over your rig(s)
- [x] Truly headless
- [x] Integrated with 💊 [OhGodAnETHlargementPill](https://github.com/admin-ipfs/OhGodAnETHlargementPill) (GTX 1080, GTX 1080Ti & TITAN Xp—GDDR5X GPUs)
> "ED (Ethereum Dysfunction) affects 1 in 10 NVIDIA GPUs in North America"

- [x] Support for the latest & greatest version of Ubuntu Server LTS
- [x] Firewall is enabled by default
- [x] Command-line interface

## Preface

NVIDIA drivers on Linux are rather finicky and do not like being overclocked without a monitor connected to them, so I had to trick them using a combination of **lightdm** and some other commands.

After countless hours, probably even days of banging my head against the monitor in despair to have my rigs work headlessly, and be **actually be overclockable**, I wanted to find a way that was simple, yet have the code and process be open-source. In contrast to operating systems like HiveOS, or NHOS, using *MinerWrangler* in conjunction with Ubuntu Server, you can actually understand each step of the process and have full control over your rigs as providers of the blockchain.
