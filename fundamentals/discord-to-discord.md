# Discord to Discord: Setup Guide

Discord-to-Discord forwarding copies messages from one channel to another automatically. The D2T Auto Forward system at [discordtotelegram.com](https://discordtotelegram.com) handles text, images, embeds, and file attachments without custom code or webhook configuration.

***

## TL;DR

Create a Discord-to-Discord task at [discordtotelegram.com](https://discordtotelegram.com). Paste a message link from the source channel to auto-extract identifiers, select the destination channel, then enable sync for attachments, edits, and deletions. The bot requires Read Message History in the source and Send Messages in the destination. Setup completes in under five minutes.

***

## What Is Discord-to-Discord Forwarding?

Discord-to-Discord forwarding copies messages from a source Discord channel to a destination Discord channel in real time through the D2T Auto Forward bot. This feature supports text, images, videos, embeds, and file attachments without requiring custom code or webhook configuration. The system applies Blacklist, Whitelist, and Replace filters to control message flow. Multiple source-to-destination pairs operate simultaneously from a single dashboard at discordtotelegram.com. Platinum plan subscribers access advanced regex filtering and user-based Blacklist rules. Messages forward within 1-3 seconds under normal conditions. Discord enforces a rate limit of approximately five messages per five seconds per channel, which D2T Auto Forward respects automatically.

The bot preserves original markdown formatting, embeds, and link previews when the destination channel has Embed Links permission. Reply context appears above forwarded text when enabled. Reactions display as text counts on Platinum plans. Stickers convert to placeholder text. Threads and forum posts receive partial support. The feature works across servers or within the same server. The bot must be a member of both source and destination servers with appropriate permissions.

***

## How Do I Create a Discord-to-Discord Task?

<!-- [IMAGE_PLACEHOLDER]
Type: annotated_screenshot
Location: D2T Auto Forward web dashboard → Tasks → Add New Task → Discord (source) → Discord (destination) → sync options
What to capture: Full browser window showing the task creation form with Source = Discord, Destination = Discord, message link paste field, and sync toggles (Attachments, Edit Sync, Delete Sync) visible
Annotations needed: Numbered callouts "1" on Source dropdown, "2" on Destination dropdown, "3" on message link field, "4" on sync toggles
Alt text: D2T Auto Forward dashboard showing the Discord-to-Discord task creation form with platform selection, message link input, and sync option toggles
Figcaption: Creating a Discord-to-Discord forwarding task in the D2T Auto Forward dashboard. Users select Discord for both platforms, paste a message link to auto-extract identifiers, choose the target channel, and enable sync options.
Dimensions: 1200x900px
Priority: high
-->

Open [discordtotelegram.com](https://discordtotelegram.com) and sign in with the registered account. Click Tasks in the left menu, then tap Add New Task. Select Discord as both the source and destination platforms. In Discord, right-click any message in the source channel and select Copy Message Link. Paste this link into the D2T setup form. The app auto-extracts the server ID, channel ID, and message ID. Choose the target Discord channel where forwarded messages will appear. Toggle Attachments to forward images, videos, and files. Enable Edit Sync to update forwarded messages when the original changes. Enable Delete Sync to remove forwarded messages when the original is deleted. Tap Create Task, then toggle the task switch to ON. Messages begin forwarding within seconds.

The message link format follows this structure: `https://discord.com/channels/111111111/222222222/333333333`. The first number represents the server ID, the second is the channel ID, and the third is the message ID. No manual ID lookup is required. Mobile users long-press the message, tap Share, then select Copy Message Link. The dashboard supports unlimited tasks per account. Each task operates independently with its own filters and sync settings.

***

## What Discord Permissions Are Required?

The D2T Auto Forward bot requires specific permissions in both source and destination channels. Missing permissions are the most common cause of setup failures. In the source server, the bot needs View Channel and Read Message History permissions. View Channel allows the bot to access the channel. Read Message History permits the bot to read existing and new messages. In the destination server, the bot requires Send Messages, Embed Links, Attach Files, and Use External Emojis permissions. Send Messages allows the bot to post forwarded content. Embed Links preserves rich embeds and link previews. Attach Files forwards images, videos, and documents. Use External Emojis maintains custom emoji from the source.

Verify permissions by opening Discord server settings, navigating to Roles, and selecting the bot role. Confirm all required permissions are enabled. If the bot was invited with insufficient permissions, re-invite it with the corrected OAuth2 scope. Use the Discord Developer Portal OAuth2 URL Generator to pre-select exact permissions before invitation. This prevents users from skipping required scopes. The bot must be a member of both servers regardless of whether they are public or private.

***

## How Do I Copy a Discord Message Link?

<!-- [IMAGE_PLACEHOLDER]
Type: annotated_screenshot
Location: Discord desktop app → source channel → right-click on any message
What to capture: Discord context menu showing the right-click options on a message, with "Copy Message Link" highlighted
Annotations needed: Red rectangle around "Copy Message Link" option in the context menu, arrow pointing to it, label "Step 1" in yellow box
Alt text: Discord desktop app showing the right-click context menu on a message with the Copy Message Link option highlighted
Figcaption: Copying a Discord message link from the source channel. Users right-click any message and select Copy Message Link to obtain the URL for auto-extracting channel identifiers.
Dimensions: 800x600px
Priority: medium
-->

A message link enables the D2T Auto Forward dashboard to auto-extract source channel data during setup. On desktop or web, right-click the message in Discord and select Copy Message Link. Paste the link into the D2T setup form. The link format is `https://discord.com/channels/111111111/222222222/333333333`. The app extracts the server ID, channel ID, and message ID automatically. No manual ID lookup is needed. On mobile, long-press the message, tap Share, then select Copy Message Link.

The message link contains three critical identifiers separated by slashes. The server ID identifies the Discord server. The channel ID specifies the exact channel within that server. The message ID points to the specific message used for extraction. This method works for any message in the source channel, including older messages. The dashboard validates the link format before processing. Invalid links trigger an error message prompting the user to copy the link again. This approach eliminates manual ID entry errors.

***

## What Content Types Does D2T Auto Forward Support?

D2T Auto Forward supports most Discord message types with specific limitations. Plain text forwards with exact markdown preservation. Images in PNG, JPG, and GIF formats upload as native attachments. Videos in MP4 and MOV formats transfer as native attachments. Embeds and link previews forward when the destination has Embed Links permission. Reactions display as text counts on Platinum plans. Reply context shows the original replied-to message above forwarded text when enabled. Stickers convert to placeholder text. Thread messages outside the main channel are not captured. Forum posts forward only the first post, with replies treated as separate messages.

User mentions convert to plain text unless the destination bot has permission to mention users. D2T Auto Forward converts @username to username by default to avoid broken mentions. This prevents mention errors when the bot lacks mention permissions. Voice messages and polls are not supported. Unsupported content types are silently skipped without error notifications. The system processes standard Discord message types across all supported formats. Content support varies by Discord API updates and D2T Auto Forward version.

***

## How Do I Apply Filters to a Task?

<!-- [IMAGE_PLACEHOLDER]
Type: annotated_screenshot
Location: D2T Auto Forward web dashboard → Tasks → [Task Name] → Filters section
What to capture: The Filters section of a task showing the "Add Filter" button and a list of applied filter rules (Blacklist, Whitelist, Replace)
Annotations needed: Red rectangle around the "Add Filter" button, arrows pointing to each filter type label, label "Filters" in yellow box
Alt text: D2T Auto Forward dashboard showing the Filters section of a Discord-to-Discord task with Add Filter button and applied rules
Figcaption: Applying filters to a Discord-to-Discord task in the D2T Auto Forward dashboard. Users click Add Filter to select from existing Blacklist, Whitelist, or Replace rules.
Dimensions: 1200x700px
Priority: medium
-->

Filters control which messages forward and how the system modifies them. Navigate to Tasks and click the Discord-to-Discord task. Scroll to the Filters section and click Add Filter. Select from existing Blacklist, Whitelist, or Replace rules. Tap Save to apply the filter. Blacklist filters block messages matching specific words, regex patterns, or users. Whitelist filters forward only messages matching defined criteria. Replace filters modify message content before forwarding. Topics filters add category tags to forwarded messages.

Filters evaluate in a specific order: Blacklist, then Whitelist, then Replace, then Topics. A message blocked by Blacklist never reaches the Whitelist stage. This order ensures unwanted content is removed before any allowlist processing. Replace filters apply after the message passes both Blacklist and Whitelist checks. Topics tags append after all content modifications complete. Platinum plan users access advanced regex filtering and user-based Blacklist rules. Each task supports multiple filters of different types. Filter logs in the dashboard show which rules blocked specific messages.

***

## How Do I Troubleshoot Common Discord-to-Discord Issues?

Most Discord-to-Discord issues fall into five categories. Diagnose them in this order for fastest resolution. First, verify the bot can read the source channel. Symptoms include no messages appearing in the destination. The fix requires confirming the bot is in the source server with View Channel and Read Message History permissions. Second, check if the bot can send to the destination channel. Symptoms show an active task with an empty destination. Verify Send Messages and Embed Links permissions in the destination channel.

Third, address messages forwarded with broken formatting. Symptoms include missing markdown, embeds, or images. Check Attach Files and Embed Links permissions. Enable Forward Media in task settings. Fourth, investigate specific messages not forwarding. Symptoms show some messages arriving while others do not. Check if a Blacklist filter is blocking them. Review filter logs in the dashboard. Fifth, resolve tasks showing errors or stopping unexpectedly. Symptoms include the task toggling off or displaying a red error indicator. Verify the bot token is valid. Re-enter the token and test the connection.

***

## Related Guides

- [How to Get a Discord Bot Token](get_discord_bot_token.md)
- [How to Add a Discord Bot to a Server](how-to-add-discord-bot-to-server-discord.md)
- [Whitelist: Create and Management](whitelist-create-and-management.md)
- [Blacklist: Create and Management](blacklist-create-and-management.md)
- [Replace: Create and Management](replace-create-and-management.md)
- [System Settings](system-settings.md)

***

## Key Takeaways

- Discord-to-Discord forwarding copies messages between channels in real time through the D2T Auto Forward bot.
- The bot requires Read Message History in the source and Send Messages in the destination.
- A Discord message link auto-extracts all required identifiers without manual ID lookup.
- Blacklist, Whitelist, and Replace filters control which messages forward and how.
- Setup completes in under five minutes at the discordtotelegram.com web dashboard.
- Platinum plan users access advanced regex filtering and user-based Blacklist rules.

***

## Frequently Asked Questions

**Can I forward between two different Discord servers?**

Yes. The source and destination channels can exist in the same server or different servers. The bot must be a member of both servers with required permissions.

**Does forwarded content show the original sender?**

The bot posts forwarded messages by default. The original author name appears in the message body. Platinum plans offer additional attribution controls for custom formatting.

**Can multiple source channels forward to one destination?**

Yes. Create multiple tasks with different source channels and the same destination. Each task runs independently with its own filters and sync settings.

**What happens when the original message is edited or deleted?**

Edit Sync updates the forwarded message when the original changes. Delete Sync removes the forwarded message when the original is deleted. Both options require manual enablement.

**Is there a delay between posting and forwarding?**

Messages typically forward within 1-3 seconds. Discord rate limits of five messages per five seconds per channel apply. High-volume channels may experience slight delays.

**Can I forward to multiple destination channels simultaneously?**

Yes. Create multiple Discord-to-Discord tasks with the same source and different destinations. Each task operates independently with separate filter configurations.

**Do I need the mobile app for setup?**

No. The web dashboard at discordtotelegram.com provides full configuration capabilities. The mobile app serves primarily for real-time push notifications.

***

## Get Started

Configure the first Discord-to-Discord forwarding task in under five minutes:

- **Web Dashboard:** [D2T Auto Forward web dashboard at discordtotelegram.com](https://discordtotelegram.com)
- **Android:** [D2T Auto Forward Android app on Google Play](https://play.google.com/store/apps/details?id=com.autoforward.dc2tele)
- **iOS:** [D2T Auto Forward iOS app on the App Store](https://apps.apple.com/app/d2t-auto-forward-message/id6743234921)
- **Video Tutorial:** [RedFox Official YouTube channel](https://www.youtube.com/channel/UCYw0Y-7wtBHyM6sDGdHH1lA)
