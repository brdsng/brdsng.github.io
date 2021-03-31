---
layout: default
title: Commands
---

# Command Reference

There are three access levels to keep in mind when working with Birdsong commands:

- **All:** All users can run these commands.
- **Mod:** Users with the designated moderator role in a guild can run these commands in that guild.
- **Owner:** The owner of a guild can run these commands in their guild.

# Access Level: **All**

## `$$points`

**Requires permissions:**

- Channel: `add_reactions`

Returns the user's current point value in a DM. If the user has private messages turned off, the command will fail.


## `$$help`

**Aliases:** `$$info`, `$$about`

**Requires permissions:**

- Channel: `add_reactions`

Sends an informational message about the bot in a DM. If the user has private messages turned off, the command will fail.


# Access Level: **Mod**

## `$$point <user> <points> <reason?>`

Requires permissions:

-

Arguments:

- `points`: Integer between -100 and 100
- `user`: User ID or mention
- `reason`: Short description of the punishment (<256 characters) (opt.)

Issue the user a certain a punishment including a certain number of points, and an optional reason.

- If `<points>` is positive, issue a punishment.
- If `<points>` is negative, issue no punishment.

The command will always cancel any active punishment the user may have had, and will note if it does so.

# Access Level: **Owner**
