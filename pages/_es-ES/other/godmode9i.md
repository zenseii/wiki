---
lang: es-ES
layout: wiki
section: other
title: GodMode9i
description: Acerca de GodMode9i
---

[GodMode9i](https://github.com/DS-Homebrew/GodMode9i/) is an open source file browser for the Nintendo DS ecosystem, taking inspiration from GodMode9 for the Nintendo 3DS. GodMode9i has the ability to dump games, manage SD card files, browse NitroFS, calculate the SHA1 hash of files, edit binary files with a hex editor, and more.

## Dumping functionality

To dump games, select the drive in the drives list and follow the on-screen prompts.
- On the Nintendo DS and Nintendo DS Lite, GodMode9i can dump Slot-2 cartridges if running from Slot-1 flashcard, or Slot-1 Game Cards if GodMode9i is running from a Slot-2 flashcart
- On the Nintendo DSi family of systems, Unlaunch is required for dumping Slot-1 games to the SD card
   - Follow [dsi.cfw.guide](https://dsi.cfw.guide/) for instructions on how to install Unlaunch
- On the Nintendo 3DS family of systems, a modern CFW environment is required to launch GodMode9i
   - Follow [3ds.hacks.guide](https://3ds.hacks.guide/) for instructions on how to install Luma3DS + boot9strap

## Troubleshooting and FAQ

#### How do I get past the "mounting drive(s)" screen while starting it up?
This happens when you launch GodMode9i from [hiyaCFW](../hiyacfw). You can hold <kbd class="face">X</kbd> while launching GodMode9i to skip NAND mounting. Alternatively, you can launch GodMode9i directly from Unlaunch to be able to mount the NAND.

#### Why can't I add, remove, or edit files on the NAND?
Editing files on the DSi NAND is not safe and can easily lead to a brick, so GodMode9i intentionally lacks this capability.

#### Why can't I view NDS file info for some DSiWare?
Some DSiWare, specifically those located in the `0003000f` folder, contain system data and do not have a valid banner.

#### Should I use the NDS version or the DSi version? What's the difference?
These are functionally the same, but they have specific purposes.
- If you are using GodMode9i with a flashcard, use the NDS version
- If you are installing GodMode9i to your hiyaCFW SDNAND, use the DSi version
- If you are starting GodMode9i via TWiLight Menu++, both versions will work identically
- If you are installing GodMode9i to your 3DS HOME Menu, use the CIA version
