---
title: "Remove Duplicate Icons in Pop!_OS Applications overview"
date: "2022-08-20"
description: "How to fix it."
---

## Problem
I had an issue with icons showing twice. The affected applications were snaps which I installed via Snap Store.

Those icons are created based on `.desktop` files and I suspect that the Snap Store creates the extra icons for snaps while Pop Store has already created some.


## Solution
What I did to fix the issue:

The Desktop entries for Snaps are located under `/.local/share/applications/snap` which is a link to `/var/lib/snapd/desktop/applications/`.

- copy the file to `/.local/share/applications` (keep the entry created by Pop Shop)
- add `NoDisplay=true` to the file in the `/snap` folder
- force a refresh of GNOME (locking the screen worked for me)

## Ressources
- https://wiki.archlinux.org/title/desktop_entries
- https://wiki.ubuntuusers.de/.desktop-Dateien/