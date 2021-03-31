---
layout: default
title: Quick Setup
---


# Quick Setup Guide

Want to get Birdsong set up in your server quick? Follow the two-step guide below and you'll be on your way.

## Step 1: Invite the bot

[Click here](https://discord.com/oauth2/authorize?client_id=817513543049674773&permissions=403041382&scope=bot) to invite Birdsong to your server. You'll need to be logged into Discord. Select your server, and then authorize the bot.

**IMPORTANT:** It is highly recommended that you do not change the default permissions preset; Birdsong may not function properly without certain permissions!

## Step 2: Configure some settings

To configure Birdsong's settings in your guild, you will need to use the `>>set` command. This command can only be used by the server owner.

```
>>set mod_role <role>
```

Set which role you'd like to have moderator permissions. Users with moderator permissions can issue punishments and read modlogs. Until you set this setting, only the owner can run mod-level commands. [Read more about moderator permissions.](/docs#access-level-all)

```
$$set mute_role <role>
```

When a user gets muted, Birdsong will apply this role to them. IMPORTANT: If you don't have this set up, Birdsong will not be able to mute users in your server!

```
$$set log_channel <channel>
```
When a guild moderator issues a punishment, Birdsong will send a short blurb about the punishment to this channel. This can be helpful for keeping track of moderator actions.

```
$$set appeal_link <link>
```

Set a link which users will be directed to appeal if they receive a permanent ban. If you're a server who wants to give users a second chance, this option is for you.

## Step 3: Learn how to punish

> **IMPORTANT:** Birdsong uses a default key to associate points with punishments; you can read about it [here](/pkey). In the future, the bot will support custom punishment values per guild.

Birdsong was created as an infraction point system to punish users. The syntax for giving infraction points is:

```
$$point <user> <points> <reason?>
```

In the command, `<user>` can be a user mention or ID, and `<reason>` is optional (but recommended). A complete example would be:

```
$$point @miike 1 spamming in #general
```

Once you run this command, the user will be given points and punished based on their prior point value.

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

## All done! 🎉

Congratulations! You've finished setting up Birdsong in your server, and you know how to give punishments to users. Other helpful pages you may want to read:

- [Commands Documentation](/docs)
- [Punishment Key](/pkey)
- [Frequently Asked Questions](/faq)
