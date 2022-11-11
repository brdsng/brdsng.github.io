---
layout: default
display_name: Commands
---

# Command Reference

**NOTE:** As of August 11th, 2022, Birdsong has switched to slash commands.

There are three levels of access for commands. Users with a higher level of access can still access lower-level commands; for instance, server admins can run "mod" and "everyone" commands.

- **Everyone:** All users can run these commands.
- **Mod:** Users with the server's moderator role can run these commands.
- **Admin:** Users with the "manage server" permission can run these commands.

# Access Level: **Everyone**

***

> ## `/info`

Shows the user information about Birdsong, including a help, invite, and support link.

***

> ## `/points`

Shows the user their current number of points, and when their next point decays.

# Access Level: **Mod**

***

> ## `/point <user> <points> <reason>`

**Arguments:**

- `user`: User's @mention or ID
- `points`: Integer between -99 and 99
- `reason`: Short description of the punishment (max 256 characters)

Issues the user a punishment based on the number of points provided. This will always override any previous active punishment the user had.

If a negative number of points is passed, the user's points will be subtracted, and if they had an active punishment, it will be cancelled.

***

> ## `/logs <user> <page?>`

**Arguments:**

- `user`: User @mention or ID
- `page`: Integer (default: first page)

Opens an interactive modlog menu displaying the user's punishment history. Up to four entries are shown per page. Pages can be scrolled through the associated arrow buttons.

The "user info" button displays some information about the user, including their account creation date and server join date. (This replaces the `$$userinfo` command.)


# Access Level: **Admin**

***

> ## `/configure` or `/settings`

Opens an interactive settings menu displaying the server's settings. A select menu is available to select and modify settings.

This menu is the only way to "clear" settings.

***

> ## `/set <setting> <value>`

**Arguments:**

- `setting`: A valid setting (see below)
- `value`: The value to set

Sets a server-wide configuration setting. The implications of these settings are explained below.

**List of settings:**

> `mod_role`: Role @mention or ID

Set the server's moderator role. When this is set, users that have the specific role will be able to run moderator commands.

**Note:** If this role is not set, only server admins will be able to run moderation commands.

> `mute_role`: Role @mention or ID

Set the server's mute role. When a user in the server is muted, the bot will automatically give them this role. This role should have restricted "send messages" permissions to work effectively.

**Note:** If this role is not set, any attempts to mute users in the server will fail.

> `point_config`: [Point configuration code](/config)

This option determines what punishment happens when a user receives a point in the server. Visit the online configuration wizard for further details. ([link: configuration wizard](/config))

**Note:** If this option is not set, a default configuration will be used. ([link: default configuration](/default-point-config))

> `log_channel`: Channel #mention or ID

Set the server's moderator log channel. When a moderator punishes a user, a short description of the punishment will be sent to this channel for logging purposes. This channel should be kept private and restricted to viewing for only moderators and server admins.

> `appeal_link`: Valid link

Set the server's appeal link (eg. a google form). When a user is permanently banned, if this option is set, the user will be sent this link to appeal their ban.

**Note:** All link inputs are parsed by a non-strict regex. If you are repeatedly getting an "invalid link" error, ensure that you have passed in a protocol (ex. `https://`) and there are no abnormal characters in the link.

> `decay_rate`: Integer between 3 and 14

Set the rate of point decay, in days. This rate is set at 7 days by default. Every `n` days without receiving a punishment, a user will decay one point. This rate can be as low as 3 days or as high as 14 days.
