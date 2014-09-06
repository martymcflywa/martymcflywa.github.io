---
layout: post
title:  "Linux & HP UEFI"
date:   2014-09-06 19:29:00
categories:
- blog
---

HP UEFI didn't like having Linux as the only OS installed. It kept looping over HP's start up recovery trying to fix a Windows installation that didn't exist anymore.

To resolve the issue:

List the EFI boot order

``` bash
$ sudo efibootmgr
BootCurrent: 0004
Timeout: 2 seconds
BootOrder: 0002,3002,0004,2001,2002,2003
Boot0002* Windows Boot Manager
Boot0003* USB Hard Drive (UEFI) - ���(�
Boot0004* ubuntu
Boot2001* USB Drive (UEFI)
Boot3000* Internal Hard Disk or Solid State Disk
Boot3001* Internal Hard Disk or Solid State Disk
Boot3002* Internal Hard Disk or Solid State Disk
Boot3003* Internal Hard Disk or Solid State Disk
Boot3004* Internal Hard Disk or Solid State Disk
```

At the time, Windows Boot Manager had priority over the ubuntu EFI which was causing problems.

So to change the boot order:

``` bash
$ sudo efibootmgr -o 0004,3002,2001,2002,2003
```

<!--more-->

After a reboot, GRUB popped up off the bat and all was good. It even lists the recovery partition if I ever wanted to go back to Windows 8.1, which in all honesty is highly unlikely.

ECU offers students studying Computer and Security Science related courses a free laptop which is on loan for the first year, then becomes our property if re-enrolled for the second year.

These became available last week so I stopped by to pick one up on Wednesday. I was one of the lucky few that managed to snatch one since they only had 2 left when I swung through.

It's a HP Pavilion 11-e109au. Pretty decent atom-based netbook with 4GB ram. Not the fastest thing on the block so I was surprised to find Windows 8.1 x64 when I booted it up.

User experience in Win 8 on this little netbook was pretty horrible. CPU usage at times sat on 99% when idle. This was not acceptable so I decided to scrap Windows 8 and try Linux on this little laptop. It was also a good reason to ditch all the crappy bloatware that HP loves to force down your throat.

Thankfully, there's a recovery partition so I can restore back to factory if I stuff something up. Just as long as I leave that partition intact.

Linux Mint 17 XFCE was pretty straightforward to install. No hassles whatsoever with drivers. The only issue I came across was with HP's UEFI. It completely ignored GRUB and kept trying to boot back ito Windows, which didn't exist any more, and prompted HP's recovery to kick in. All it says was "attempting repair" and then asking me to shut down when it couldn't fix it. Probably because it couldn't write to the Ex4 partition.