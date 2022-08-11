---
layout: default
title: Slash Command Migration
---

# Migration to slash commands (v1.0.0)

**TL;DR: Use the forward slash (`/`) as your command prefix from now on.*

Birdsong is switching from text commands to slash commands, a new Discord feature empowering bots to do all sorts of cool things. **Most commands are exactly the same.**

## Prefixes are gone

This update renders your old prefixes obsolete. All commands will use the universal forward slash prefix (`/`). Trying to run commands with old prefixes will be met with a friendly migration message. On September 1st, 2022, text commands will be disabled completely.

## Command updates

> **`/settings` and `/logs` are now button menus**

The old static menus are gone and have been replaced with interactive menus. Select menus can be used to toggle between settings, and arrows can be used to navigate pages on logs. This UI change will make menu navigation much easier.

> **`/whois` and `/pinfo` mod commands were removed**

The functionality of `/whois` is re-implemented as a button under the `/logs` commands. The `/pinfo` command was rarely used; to search for information about a punishment, use Discord's search tool to find log entries.

> **The `<reason>` field for `/point` is now required**

It is important for a reason to be assigned to punishments for clarity and logging purposes. As such, this field is no longer optional.

***

If you spot any bugs in this update (it's a big one!), please report them on the [Discord server.](https://discord.gg/4EzY2hmrTF)
