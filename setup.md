---
layout: default
display_name: Quick Setup
---


# Quick Setup Guide

Want to get Birdsong set up in your server quick? Follow this short guide and you'll be on your way.

## Step 1: Invite the bot

[Click here](https://discord.com/oauth2/authorize?client_id=817513543049674773&permissions=403041382&scope=bot) to invite Birdsong to your server. You'll need to be logged into Discord. Select your server, and then authorize the bot.

**IMPORTANT:** It is highly recommended that you do not change the default permissions preset; Birdsong may not function properly without certain permissions!

## Step 2: Enable developer mode

Discord's developer mode allows you to right-click on users, channels, roles, and servers, and copy their internal ID. This ID can be passed to any commands that support them. Discord IDs are useful because they don't mention the role/user and they don't require the user to be a member of the server. **It is highly recommended that all moderators enable developer mode.**

1. Go to your user settings.
2. Click on the "Advanced" tab.
3. Enable the "Developer Mode" option.

## Step 3: Configure some settings

The `/settings` command shows a menu with your server's configurable options. To configure these settings, you will use the `/set` command. This is a brief overview of these settings:

```
/set mod_role <role>
```

Set which role you'd like to have moderator permissions. **If you don't have a mod role set up, only server admins can run mod commands.** [Read more about moderator permissions.](/docs#access-level-mod)

```
/set mute_role <role>
```

When a user gets muted, Birdsong will apply this role to them. Make sure you remove "send messages" permissions on this role. **If you don't have a mute role set up, Birdsong will not be able to mute users in your server.**

```
/set log_channel <channel>
```
When a server moderator issues a punishment, Birdsong will send a short blurb about the punishment to this channel. This can be helpful for keeping track of moderator actions.

```
/set appeal_link <link>
```

Set a link which users will be directed to appeal if they receive a permanent ban. This option is for servers with their own dedicated appeal forms.

```
/set decay_rate <int>
```

Set the rate of point decay, in days. This defaults to 7 (one week). Every `n` days without receiving a punishment, a user will decay one point. This rate can be as low as 3 days or as high as 14 days.

## Step 4: Learn how to punish

Birdsong was created as an infraction point system to punish users. The syntax for giving infraction points is:

```
/point <user> <points> <reason>
```

In the command, `<user>` can be a user mention or ID, `<points>` is a number between -99 and 99, and `<reason>` is a brief description of the punishment. A complete example would be:

```
/point @miike 1 spamming in #general
```

If you make a mistake, you can reverse a punishment by giving the user negative points:

```
/point @miike -1 mistake; was not spam
```

You can view the punishment history of a user with the `/logs` command; the syntax is:

```
/logs <user> <page?>
```

Modlogs are limited to four entries per page. Navigate between pages using the buttons on the logs menu. This example will skip to page 3:

```
/logs @miike 3
```

## Step 5: Set up your point configuration

A "point configuration" is what Birdsong uses to correlate an amount of points to a punishment; an example would be 2 points equals a 30 minute mute. We understand figuring this out can be a little daunting for users, so if you choose not to set up this option, your server will inherit the default point config. [View this default point configuration](/default-point-config).

For those who want to go above and beyond, we support customizing this configuration! To help you out, we've created an interactive tool to guide you through this process; simply create your configuration and then press "Export". You can go back later and edit your configuration with the same link, accessed by running `/settings` and selecting "Point Config".

**[Click here to view the point configuration tool](/config)**. *This tool is in beta mode and all bugs should be reported on the Discord server.*

Not sure what configuration to use? [Check out an example](/config?AAQPUBUDoBoDgAA)!

## All done! 🎉

Congratulations! You've finished setting up Birdsong in your server, and you know how to give punishments to users. Other helpful pages you may want to read:

- [Full command documentation](/docs)
- [Point configuration tool](/config)

Still stuck? [Join our Discord server!](https://discord.gg/4EzY2hmrTF)
