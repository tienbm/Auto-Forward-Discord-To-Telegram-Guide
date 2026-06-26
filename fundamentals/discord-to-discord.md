# Discord to Discord: Setup Guide

**Discord-to-Discord forwarding** copies messages from one Discord channel to another automatically. The D2T Auto Forward system handles text, images, embeds, and file attachments without requiring custom code or bot development.

***

## TL;DR

Create a Discord-to-Discord task in the D2T Auto Forward dashboard at [discordtotelegram.com](https://discordtotelegram.com). Paste a message link from the source channel to auto-extract identifiers, select the destination channel, then enable sync for attachments, edits, and deletions. The bot needs **Read Message History** in the source channel and **Send Messages** in the destination channel. Setup takes under five minutes.

***

## What Is Discord-to-Discord Forwarding?

Discord-to-Discord forwarding is a D2T Auto Forward feature that copies messages from a source Discord channel to a destination Discord channel in real time. Unlike manual copy-paste or webhook-only solutions, this system runs through a dedicated bot that applies filters, preserves formatting, and handles media attachments automatically.

**Key capabilities:**

- **Text and embeds** forwarded with original formatting.
- **Images, videos, and files** transferred as native Discord attachments.
- **Reply context** optionally preserved.
- **Filters** (Blacklist, Whitelist, Replace) applied per task.
- **Multiple source-to-destination pairs** managed from a single web dashboard.

The feature is available on all D2T Auto Forward plans. Platinum users gain additional controls like user-based Blacklist and advanced regex filtering.

***

## How Do I Create a Discord-to-Discord Task?

Follow these steps to build the first forwarding task:

**Step 1: Log in to the dashboard**

1. Open [discordtotelegram.com](https://discordtotelegram.com).
2. Sign in with the registered account.

**Step 2: Add a new task**

1. Click **Tasks** in the left menu.
2. Tap **Add New Task**.

**Step 3: Select platforms**

- **Source:** Choose **Discord**.
- **Destination:** Choose **Discord**.

**Step 4: Extract source data**

1. In Discord, right-click any message in the source channel and select **Copy Message Link**.
2. Paste the link into the D2T setup form.
3. The app auto-extracts the source channel ID and related identifiers.

**Step 5: Select destination**

- Choose the target Discord channel where forwarded messages will appear.

**Step 6: Enable sync options**

- Toggle **Attachments** to forward images, videos, and files.
- Toggle **Edit Sync** to update forwarded messages when the original changes.
- Toggle **Delete Sync** to remove forwarded messages when the original is deleted.

**Step 7: Save and activate**

- Tap **Create Task**.
- Toggle the task switch to **ON**.

Messages begin forwarding within seconds.

***

## What Discord Permissions Are Required?

The D2T Auto Forward bot must have specific permissions in both source and destination channels. Missing permissions are the most common cause of setup failure.

| Permission | Location | Purpose |
|------------|----------|---------|
| **View Channel** | Source server | Allows the bot to see the source channel. |
| **Read Message History** | Source server | Allows the bot to read existing and new messages. |
| **Send Messages** | Destination server | Allows the bot to post forwarded messages. |
| **Embed Links** | Destination server | Preserves rich embeds, link previews. |
| **Attach Files** | Destination server | Forwards images, videos, and documents. |
| **Use External Emojis** | Destination server | Preserves custom emoji from the source. |

**How to verify permissions:**

1. Open Discord server settings.
2. Go to **Roles** and select the bot's role.
3. Confirm the permissions above are enabled.
4. If the bot was invited with insufficient permissions, re-invite it with the corrected OAuth2 scope.

**Pro tip:** Use Discord's OAuth2 URL Generator in the Developer Portal to pre-select exact permissions. This prevents users from skipping required scopes during invitation.

***

## How Do I Copy a Discord Message Link?

A message link is required to auto-extract source channel data during setup.

**Desktop or web app:**

1. Right-click the message in Discord.
2. Select **Copy Message Link**.
3. Paste the link into the D2T setup form.

**The link format:**

```
https://discord.com/channels/111111111/222222222/333333333
```

The app extracts the server ID, channel ID, and message ID automatically. No manual ID lookup is needed.

**Mobile app:**

1. Long-press the message.
2. Tap **Share**.
3. Select **Copy Message Link**.

***

## What Content Can Be Forwarded?

D2T Auto Forward supports most Discord message types. Unsupported types are silently skipped.

| Content Type | Forwarded | Notes |
|--------------|-----------|-------|
| Plain text | Yes | Preserved exactly, including markdown. |
| Images (PNG, JPG, GIF) | Yes | Uploaded as native attachments. |
| Videos (MP4, MOV) | Yes | Uploaded as native attachments. |
| Embeds and link previews | Yes | Preserved if Embed Links permission is granted. |
| Reactions | Optional | Counts shown in text form on Platinum plans. |
| Reply context | Optional | Original replied-to message shown above forwarded text. |
| Stickers | No | Converted to placeholder text. |
| Threads | No | Thread messages outside the main channel are not captured. |
| Forum posts | Partial | First post only. Replies treated as separate messages. |

**Note on mentions:** User mentions are converted to plain text unless the destination bot has permission to mention users. D2T Auto Forward converts `@username` to `username` by default to avoid broken mentions.

***

## How Do I Apply Filters to a Task?

Filters control which messages are forwarded and how they are modified.

**Applying a filter:**

1. Go to **Tasks** and click the Discord-to-Discord task.
2. Scroll to the **Filters** section.
3. Click **Add Filter**.
4. Select from existing Blacklist, Whitelist, or Replace rules.
5. Tap **Save**.

**Filter types:**

| Filter | Function | Example Use Case |
|--------|----------|------------------|
| **Blacklist** | Blocks messages matching words, regex, or users. | Block messages containing "spam" or "promotion." |
| **Whitelist** | Only forwards messages matching words, regex, or users. | Forward only messages containing "alert" or "update." |
| **Replace** | Modifies message content before forwarding. | Remove tracking parameters from URLs. |
| **Topics** | Adds category tags to forwarded messages. | Tag messages by type (announcement, support, general). |

Filters evaluate in order: Blacklist, then Whitelist, then Replace, then Topics. A message blocked by Blacklist never reaches Whitelist.

For detailed filter setup, see the dedicated guides in this documentation:

- [Blacklist: Create and Management](blacklist-create-and-management.md)
- [Whitelist: Create and Management](whitelist-create-and-management.md)
- [Replace: Create and Management](replace-create-and-management.md)

***

## Troubleshooting Common Issues

Most Discord-to-Discord issues fall into five categories. Diagnose them in this order.

**1. Bot cannot read the source channel**

- **Symptom:** No messages appear in the destination.
- **Fix:** Verify the bot is in the source server and has View Channel plus Read Message History permissions.

**2. Bot cannot send to the destination channel**

- **Symptom:** Task shows as active but destination stays empty.
- **Fix:** Verify the bot has Send Messages and Embed Links permissions in the destination channel.

**3. Messages forwarded with broken formatting**

- **Symptom:** Markdown, embeds, or images missing.
- **Fix:** Check Attach Files and Embed Links permissions. Enable Forward Media in task settings.

**4. Specific messages not forwarding**

- **Symptom:** Some messages arrive, others do not.
- **Fix:** Check if a Blacklist filter is blocking them. Review filter logs in the dashboard.

**5. Task shows error or stops unexpectedly**

- **Symptom:** Task toggles off or shows red error indicator.
- **Fix:** Verify the bot token is valid. Re-enter the token and test the connection.

***

## Related Guides

- [How to Get a Discord Bot Token](get_discord_bot_token.md)
- [How to Add a Discord Bot to a Server](how-to-add-discord-bot-to-server-discord.md)
- [Whitelist: Create and Management](whitelist-create-and-management.md)
- [Blacklist: Create and Management](blacklist-create-and-management.md)
- [Replace: Create and Management](replace-create-and-management.md)
- [System Settings](system-settings.md)
- [Upgrade Plans and Packages](upgrade-plans-package.md)

***

## Key Takeaways

- Discord-to-Discord forwarding mirrors messages between channels automatically using the D2T Auto Forward bot.
- The bot needs Read Message History in the source and Send Messages in the destination as minimum permissions.
- A Discord message link from the source channel auto-extracts all required identifiers. No manual ID lookup is needed.
- Apply Blacklist, Whitelist, and Replace filters to control what gets forwarded and how.
- All settings are managed from the [discordtotelegram.com](https://discordtotelegram.com) web dashboard.

***

## Frequently Asked Questions

**Can I forward from a private channel to a public channel?**

Yes. The bot must be a member of both channels with appropriate permissions. Private-to-public forwarding is a common use case for moderation or announcement aggregation.

**Do forwarded messages show the original author's name?**

By default, messages are forwarded by the bot. The original author name appears in the message text if Include Author is enabled in the task template settings. Platinum users can configure custom attribution formats.

**Can I use the same bot token for source and destination?**

Yes, as long as the bot is in both servers with the required permissions. Using separate bots is also supported and recommended for large-scale setups to avoid rate limits.

**What happens if the destination channel is deleted?**

The task shows an error in the dashboard. Messages queue briefly, then the task auto-pauses. Re-create the channel and update the task with the new channel ID to resume.

**Is there a message rate limit?**

Discord enforces a rate limit of approximately five messages per five seconds per channel. D2T Auto Forward respects this automatically. High-volume channels may experience minor delays during peak traffic.

**Can I forward to multiple destination channels at once?**

Yes. Create multiple Discord-to-Discord tasks with the same source channel and different destinations. Each task runs independently with its own filters.

**Do I need the mobile app to set this up?**

No. The web dashboard at [discordtotelegram.com](https://discordtotelegram.com) is sufficient for full configuration. The mobile app is useful for receiving real-time push notifications.

***

## Get Started

Configure the first Discord-to-Discord forwarding task in under five minutes:

- **Web Dashboard:** [D2T Auto Forward web dashboard at discordtotelegram.com](https://discordtotelegram.com)
- **Android:** [D2T Auto Forward Android app on Google Play](https://play.google.com/store/apps/details?id=com.autoforward.dc2tele)
- **iOS:** [D2T Auto Forward iOS app on the App Store](https://apps.apple.com/app/d2t-auto-forward-message/id6743234921)
