---
layout: default
title: Quick Setup
---


# Quick Setup Guide

Want to get Birdsong set up in your server quick? Follow the two-step guide below and you'll be on your way.

## Step 1: Invite the bot

[Click here](https://discord.com/oauth2/authorize?client_id=817513543049674773&permissions=403041382&scope=bot) to invite Birdsong to your server. You'll need to be logged into Discord. Select your server, and then authorize the bot.

**IMPORTANT:** It is highly recommended that you do not change the default permissions preset; Birdsong may not function properly without certain permissions!

## Step 2: Enable developer mode

Discord's developer mode allows you to right-click on users, channels, roles, and guilds, and copy their internal ID. This ID can be passed to any commands that support them. Discord IDs are useful because they don't mention the role/user and they don't require the user to be a member of the server. **It is highly recommended that all moderators enable developer mode.**

1. Go to your user settings.
2. Click on the "Advanced" tab.
3. Enable the "Developer Mode" option.

[Read more about developer mode.](https://discordia.me/en/developer-mode)

## Step 3: Configure some settings

To configure Birdsong's settings in your guild, you will need to use the `$$set` command. This command can only be used by server administrators. To view your settings later, run `$$settings`.

```
$$set mod_role <role>
```

Set which role you'd like to have moderator permissions. **If you don't have a mod role set up, only server admins can run mod commands.** [Read more about moderator permissions.](/docs#access-level-mod)

```
$$set mute_role <role>
```

When a user gets muted, Birdsong will apply this role to them. **If you don't have a mute role set up, Birdsong will not be able to mute users in your server.**

```
$$set log_channel <channel>
```
When a guild moderator issues a punishment, Birdsong will send a short blurb about the punishment to this channel. This can be helpful for keeping track of moderator actions.

```
$$set appeal_link <link>
```

Set a link which users will be directed to appeal if they receive a permanent ban. If you're a server with your own dedicated appeal form, this option is up your alley.

```
$$set decay_rate <int>
```

Set the rate of point decay, in days. This defaults to 7 (one week). Every `n` days without receiving a punishment, a user will decay one point. This rate can be as low as 3 days or as high as 14 days.

## Step 4: Learn how to punish

Birdsong was created as an infraction point system to punish users. The syntax for giving infraction points is:

```
$$point <user> <points> <reason?>
```

In the command, `<user>` can be a user mention or ID, and `<reason>` is optional (but recommended). A complete example would be:

```
$$point @miike 1 spamming in #general
```

If you make a mistake, you can reverse a punishment by giving the user negative points:

```
$$point @miike -1 mistake; was not spam
```

You can view the punishment history of a user with the `$$logs` command; the syntax is:

```
$$logs <user> <page?>
```

Modlogs are limited to six entries per page; to view more pages, simply add the next page number to the end of the command:

```
$$logs @miike 3
```

# Step 5: Set up your point configuration

A "point configuration" is what Birdsong uses to correlate an amount of points to a punishment; an example would be 2 points equals a 30 minute mute. We understand figuring this out can be a little daunting for users, so if you choose not to set up this option, your server will inherit the default point config. [Click here to view the default point config](/default-point-config).

For those who want to go above and beyond, we support customizing this configuration! To help you out, we've created an interactive tool to guide you through this process; simply create your configuration and then press "Export". You can go back later and edit your configuration with the same link, accessed by running `$$settings point_config`.

**[Click here to view the point configuration tool](/config)**. *Note that this tool is in beta mode and all bugs should be reported on the Discord server.*

Not sure what configuration to use? [View an example](/config?AAQPUBUDoBoDgAA)!

## All done! 🎉

Congratulations! You've finished setting up Birdsong in your server, and you know how to give punishments to users. Other helpful pages you may want to read:

- [Commands Documentation](/docs)
- [Point Configuration Tool](/config)

Still stuck? [Join our Discord server!](https://discord.gg/4EzY2hmrTF)
