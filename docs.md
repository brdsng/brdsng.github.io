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

***

> ## `$$points`

**Requires permissions:**

- Channel: `add_reactions`

Returns the user's current point value in a DM. If the user has private messages turned off, the command will fail.

***

> ## `$$help`

**Aliases:** `$$info`, `$$about`

**Requires permissions:**

- Channel: `add_reactions`

Sends an informational message about the bot in a DM. If the user has private messages turned off, the command will fail.


# Access Level: **Mod**

***

> ## `$$point <user> <points> <reason?>`

**Requires permissions:**

- Channel: `send_messages`
- Guild: `ban_members`, `manage_roles`

**Arguments:**

- `points`: Integer between -100 and 100
- `user`: User ID or mention
- `reason`: Short description of the punishment (<256 characters) (default: none)

Issue the user a certain a punishment including a certain number of points, and an optional reason.

- If `<points>` is positive, issue a punishment.
- If `<points>` is negative, issue no punishment.

The command will always cancel any active punishment the user may have had, and will note if it does so. This command does not require the target user to be in the guild.

***

> ## `$$logs <user> <page?>`

**Aliases:** `$$modlogs`

**Requires permissions:**

- Channel: `send_messages`

**Arguments:**

- `user`: User ID or mention
- `page`: Integer (default: 1)

View a specific page of a user's modlogs. Six entries will appear on each page, including the following information:

- Punishment ID (eight-character identifier),
- Punishment description (if any)
- Timestamp of the punishment
- Issuer of the punishment
- Action taken (warn / mute / ban)
- Amount of points the punishment was worth
- Link to the issuing message

The command will also show the user's active punishment (if any), and the user's current point value. This command does not require the target user to be in the guild.

***

> ## `$$who <user>`

**Aliases:** `$$whois`, `$$userinfo`

**Requires permissions:**

- Channel: `send_messages`

**Arguments:**

- `user`: User ID or mention

View information about a user, including the following:

- User ID
- Nickname
- Account registration date
- Guild join date
- Profile picture

This command will fail if the target user is not in the guild.

***

> ## `$$punishment <id>`

**Aliases:** `$$p`, `$$pinfo`

**Requires permissions:**

- Channel: `send_messages`

**Arguments:**

- `user`: Punishment ID (valid eight-character identifier from a modlog)

View information about a specific punishment, in a similar fashion as `$$logs`.

This command will fail if the target punishment ID does not exist.


# Access Level: **Owner**

***

> ## `$$set <setting> <value|none>`

**Requires permissions:**

- Channel: `send_messages`

**Arguments:**

- `setting`: A valid, alphanumeric setting (see below)
- `value`: The value to set, or "none" or "null" (see below for types)

Set a guild-wide configuration setting. Pass in "none" or "null" for any setting to reset that setting (may have unintended consequences, read below).

**List of settings:**

- `log_channel`: Channel ID or mention

Set the guild's moderator log channel. When a moderator punishes a user, a short description of the punishment will be sent to this channel for logging purposes. It is recommended you keep this channel private and restricted to viewing for only moderators and guild admins.

- `mod_role`: Role ID or mention

Set the guild's moderator role. When this is set, users that have the specific role will be able to run moderator commands.

Note: If this role is not set, only the guild owner will be able to run moderation commands.

- `mute_role`: Role ID or mention

Set the guild's mute role. When a user in the guild is muted, the bot will automatically give them this role. It is recommended you restrict sending and speaking permissions on this role so it functions as a proper mute.

Note: If this role is not set, any attempts to mute users in the guild will fail.

- `appeal_link`: Valid link

Set the guild's appeal link. When a user is permanently banned at 12 points, if the guild has an appeal link set, the user will be sent the appeal link in their ban message. This will allow for guilds to run their own appeal forms (typically through Google Forms).

Note: All link inputs are parsed by a non-strict regex. If you are repeatedly getting an "invalid link" error, ensure that you have passed in a protocol (ex. `https://`) and there are no abnormal characters in the link.

***

> ## `$$settings`

**Requires permissions:**

- Channel: `send_messages`

Returns all of the guild's currently set settings. Any setting that has not been set will read as "none set".

To set settings, use the `$$set` command.
