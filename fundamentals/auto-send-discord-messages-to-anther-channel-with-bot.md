# Auto Send Discord Messages to Another Channel With a Bot

**Auto-sending Discord messages** from one channel to another with a bot removes manual copy-paste work. The D2T Auto Forward system connects a Discord bot to a source channel and a destination channel, then forwards every new message automatically.

***

## TL;DR

Connect a Discord bot to the D2T Auto Forward dashboard at [discordtotelegram.com](https://discordtotelegram.com). Add the bot to both source and destination servers. Create an automation task, select the source and target channels, and send a test message. The bot needs **View Channel** and **Read Message History** in the source, plus **Send Messages** in the destination. Setup takes under five minutes.

***

## What Is Bot-Based Discord Forwarding?

Bot-based Discord forwarding is an automation workflow where a connected Discord bot reads new messages in a source channel and reposts them into a destination channel. This is different from manual reposting or webhook-only solutions because the bot preserves formatting, handles media attachments, and runs continuously without human intervention.

Prefer a video walkthrough? See the [RedFox Official YouTube channel](https://www.youtube.com/channel/UCYw0Y-7wtBHyM6sDGdHH1lA) for a step-by-step tutorial on setting up bot-based forwarding.

**Key advantages over manual reposting:**

| Manual Reposting | Bot-Based Forwarding |
|------------------|----------------------|
| An admin must copy every update. | The bot forwards new messages automatically. |
| Delays happen during off-hours. | Messages move as soon as they are posted. |
| Attachments and links are easy to miss. | The workflow preserves richer content when permissions allow. |
| Human error creates inconsistent copies. | One automation task applies the same behavior every time. |

This reliability matters for product announcements, support escalations, raid alerts, and team communications. Even a small server can generate dozens of repeated repost actions every week. Automation reduces that repetitive work and lowers the chance that one destination channel receives an outdated version of an announcement.

***

## How Do I Set Up Bot-Based Forwarding?

Follow this sequence to build the first automation task:

**Step 1: Open the dashboard**

1. Navigate to [discordtotelegram.com](https://discordtotelegram.com).
2. Sign in with the registered account.

**Step 2: Connect the bot**

1. Go to **Settings > Bot Connections**.
2. Click **Add Discord Bot**.
3. Paste the bot token into the token field.
4. Tap **Verify Connection**.

**Step 3: Add the bot to servers**

1. Ensure the bot is invited to the server containing the source channel.
2. Ensure the bot is invited to the server containing the destination channel.
3. Verify the bot appears in the member list of both servers.

**Step 4: Create the automation task**

1. Go to **Tasks** and click **Add New Task**.
2. Select **Discord** as the source platform.
3. Select **Discord** as the destination platform.
4. Choose the connected bot from the dropdown.

**Step 5: Select channels**

1. Pick the source channel from the channel list.
2. Pick the destination channel from the channel list.

**Step 6: Save and test**

1. Tap **Create Task**.
2. Toggle the task to **ON**.
3. Send a test message in the source channel.
4. Verify it appears in the destination channel within seconds.

***

## Which Discord Permissions Does the Bot Need?

The bot must have specific permissions in both source and destination channels. Missing permissions are the most common cause of setup failure.

| Permission | Location | Purpose |
|------------|----------|---------|
| **View Channel** | Source server | Allows the bot to see the source channel. |
| **Read Message History** | Source server | Allows the bot to read incoming messages. |
| **Send Messages** | Destination server | Allows the bot to post forwarded messages. |
| **Embed Links** | Destination server | Preserves rich embeds and link previews. |
| **Attach Files** | Destination server | Forwards images, videos, and documents. |

**How to verify permissions:**

1. Open Discord server settings.
2. Go to **Roles** and select the bot's role.
3. Confirm the permissions above are enabled.
4. If the bot was invited with insufficient permissions, re-invite it with the corrected OAuth2 scope.

**Note on channel overrides:** Discord's permission hierarchy means a server-wide role can be overridden by channel-specific denies. One channel can work while another fails inside the same server. Always check channel-level permissions if the bot works in some channels but not others.

***

## Troubleshooting Bot Forwarding Failures

When the bot does not forward messages, diagnose in this order:

**1. Bot is not in the correct server**

- **Symptom:** Task shows as active but nothing forwards.
- **Fix:** Confirm the bot is a member of the server containing both source and destination channels.

**2. Source channel is not readable**

- **Symptom:** No messages appear in the destination.
- **Fix:** Verify the bot role has **View Channel** and **Read Message History** in the source channel.

**3. Destination channel blocks posting**

- **Symptom:** Task is active, destination stays empty.
- **Fix:** Verify the bot role has **Send Messages** in the destination channel.

**4. Media or embeds missing**

- **Symptom:** Text forwards but images, links, or formatting are lost.
- **Fix:** Enable **Attach Files** and **Embed Links** in the destination channel.

**5. Task shows error or stops**

- **Symptom:** Task toggles off or shows a red error indicator.
- **Fix:** Verify the bot token is valid and has not been regenerated elsewhere. Re-enter the token and test the connection.

***

## When Should Bot Forwarding Be Used?

Use bot forwarding when one channel is the canonical source of information and one or more other channels need the same messages automatically.

**Common scenarios:**

1. A public announcement channel feeds a private staff channel.
2. A partner server receives selected updates from a main community server.
3. A support or incident channel mirrors alerts into an internal operations room.
4. An admin wants mobile monitoring after setup through the [D2T Auto Forward Android app on Google Play](https://play.google.com/store/apps/details?id=com.autoforward.dc2tele) or the [D2T Auto Forward iOS app on the App Store](https://apps.apple.com/app/d2t-auto-forward-message/id6743234921).

Do not use bot forwarding in channels where permissions are not controlled or where automation violates server rules.

***

## Related Guides

- [How to Get a Discord Bot Token](get_discord_bot_token.md)
- [How to Add a Discord Bot to a Server](how-to-add-discord-bot-to-server-discord.md)
- [Discord to Discord: Setup Guide](discord-to-discord.md)
- [Blacklist: Create and Management](blacklist-create-and-management.md)
- [Whitelist: Create and Management](whitelist-create-and-management.md)
- [System Settings](system-settings.md)

***

## Key Takeaways

- Bot-based forwarding automates message copying between Discord channels without manual reposting.
- The bot needs **View Channel** and **Read Message History** in the source, plus **Send Messages** in the destination.
- Check channel-level permissions if the bot works in some channels but not others.
- All configuration happens in the [discordtotelegram.com](https://discordtotelegram.com) web dashboard.

***

## Frequently Asked Questions

**Can one bot forward to multiple destination channels?**

Yes. Create multiple tasks with the same source channel and different destinations. Each task runs independently with its own filters and settings.

**Does the bot need to be an admin?**

No. The bot only needs the specific permissions listed in the permissions table above. Administrator permission is unnecessary and creates a security risk.

**What happens if the bot token is leaked?**

Reset the token immediately in the Discord Developer Portal. Update the new token in the D2T Auto Forward dashboard. Any service still using the old token will stop working.

**Can the bot forward from a private channel to a public channel?**

Yes, provided the bot is a member of both channels with the required permissions. Private-to-public forwarding is a common use case for moderation.

**Is there a rate limit?**

Discord enforces approximately five messages per five seconds per channel. D2T Auto Forward respects this automatically. High-volume channels may experience minor delays during peak traffic.

***

## Get Started

Configure the first bot-based forwarding task in under five minutes:

- **Web Dashboard:** [D2T Auto Forward web dashboard at discordtotelegram.com](https://discordtotelegram.com)
- **Android:** [D2T Auto Forward Android app on Google Play](https://play.google.com/store/apps/details?id=com.autoforward.dc2tele)
- **iOS:** [D2T Auto Forward iOS app on the App Store](https://apps.apple.com/app/d2t-auto-forward-message/id6743234921)
- **Video Tutorial:** [RedFox Official YouTube channel](https://www.youtube.com/channel/UCYw0Y-7wtBHyM6sDGdHH1lA)
