# How to Add a Discord Bot to a Server

Add a Discord bot to a server by generating an OAuth2 invite URL from the Discord Developer Portal at discord.com/developers/applications. D2T Auto Forward requires this setup to connect Discord servers to Telegram. The process takes under three minutes with the correct permissions.

***

## TL;DR

Open the Discord Developer Portal at discord.com/developers/applications, navigate to OAuth2 URL Generator, select the bot scope, choose required permissions, copy the generated URL, open it in a browser, select the target server, and authorize. The user must own the server or have Manage Server permission. D2T Auto Forward works with any authorized bot.

***

## What Does Adding a Bot to a Server Mean?

Adding a Discord bot to a server means granting a Discord application permission to join one specific server and operate there under approved scopes. The bot becomes a server member and can only read, post, or manage content according to the scopes granted during installation. Creating a bot in the Developer Portal does not automatically place it inside any server. Explicit authorization is required for each target server. Bot authorization follows strict security protocols to prevent unauthorized access. The OAuth2 authorization flow ensures that server owners maintain control over which applications access their communities.

Prefer a video walkthrough? See the [RedFox Official YouTube channel](https://www.youtube.com/channel/UCYw0Y-7wtBHyM6sDGdHH1lA) for a beginner-friendly tutorial on adding bots to Discord servers.

**Key requirements:**

- The user adding the bot must own the server or have the **Manage Server** permission.
- The bot user must already exist inside the application.
- The generated OAuth2 URL must include the correct scopes and permissions.

***

## How Do I Add a Discord Bot Step by Step?

<!-- [IMAGE_PLACEHOLDER]
Type: annotated_screenshot
Location: Discord Developer Portal → Applications → [App Name] → OAuth2 → URL Generator
What to capture: Full browser window showing the URL Generator with the "bot" scope checkbox selected and Bot Permissions area visible
Annotations needed: Numbered callout "1" on the "bot" scope checkbox, "2" on Bot Permissions section, "3" on the generated URL copy button
Alt text: Discord Developer Portal OAuth2 URL Generator showing bot scope selection and permission configuration
Figcaption: Generating the Discord bot invite URL in the Developer Portal. Users select the bot scope, choose required permissions, and copy the generated URL.
Dimensions: 1200x900px
Priority: high
-->

Adding a Discord bot to a server requires six specific steps in the Discord Developer Portal. Navigate to discord.com/developers/applications, create or open an application, generate a bot user, configure OAuth2 scopes, select permissions, and authorize the bot through the generated URL. This process works for D2T Auto Forward and any custom bot. Incorrect scope selection or missing permissions are the most common causes of bot installation failure. The OAuth2 URL Generator provides a standardized interface for creating valid invite links that Discord accepts.

Follow this sequence to invite a bot into a server:

**Step 1: Open the Developer Portal**

1. Navigate to discord.com/developers/applications.
2. Sign in with the Discord account that owns the application.

**Step 2: Create or open the application**

1. Click **New Application** to create a new bot.
2. Or click an existing application to open it.

**Step 3: Create the bot user**

1. Go to the **Bot** section.
2. Click **Add Bot** if the application does not already have a bot user.

**Step 4: Generate the invite URL**

1. Go to **OAuth2** and then **URL Generator**.
2. In the **Scopes** section, select **bot**.
3. For slash command support, also select **applications.commands**.

**Step 5: Select permissions**

1. In the **Bot Permissions** area, choose only the permissions the bot actually needs.
2. Avoid **Administrator** unless the bot is in a disposable test server.

**Step 6: Invite the bot**

1. Copy the generated URL.
2. Open the URL in a browser.
3. Select the target Discord server from the dropdown.
4. Review the requested permissions.
5. Click **Authorize**.
6. Complete the verification prompt.

**Pre-install checklist:**

| Requirement | Why it matters |
|-------------|----------------|
| Server ownership or **Manage Server** | Discord only allows qualified users to add apps to a server. |
| Bot user already exists | The install flow is tied to the application's bot configuration. |
| Correct scopes selected | Missing scopes can break slash commands or bot presence. |
| Only needed permissions selected | Least-privilege setup reduces security risk. |
| Correct server targeted | Installing into the wrong server is a common beginner mistake. |

***

## Which OAuth2 Scopes and Permissions Should Be Selected?

<!-- [IMAGE_PLACEHOLDER]
Type: annotated_screenshot
Location: Discord Developer Portal → OAuth2 → URL Generator → Bot Permissions section
What to capture: The Bot Permissions grid showing checked boxes for View Channel, Send Messages, Read Message History, Embed Links, and Attach Files
Annotations needed: Green checkmarks on required permissions, red X on Administrator, label "Avoid" near Administrator checkbox
Alt text: Discord Developer Portal Bot Permissions grid showing required permissions checked for a forwarding bot
Figcaption: Required Discord bot permissions for D2T Auto Forward. The bot needs View Channel, Read Message History in the source server, and Send Messages, Embed Links, Attach Files in the destination server.
Dimensions: 1200x800px
Priority: medium
-->

Select the bot scope for all Discord bots that need to read or post messages in servers. The applications.commands scope enables slash commands, which Discord introduced in 2021. For D2T Auto Forward, the bot scope combined with View Channel, Send Messages, Read Message History, Embed Links, and Attach Files provides complete forwarding functionality. Bots with granular permissions experience fewer security incidents than those granted Administrator access. Discord's permission system includes 32 distinct permissions that control specific actions within servers.

**Recommended permission set for forwarding bots:**

| Permission | When it is needed |
|------------|-------------------|
| **View Channel** | The bot must see the channel before it can read or post there. |
| **Send Messages** | Required if the bot will post replies, logs, or forwarded content. |
| **Read Message History** | Useful for context, syncing, or message-based automations. |
| **Embed Links** | Needed when the bot should render rich link previews. |
| **Attach Files** | Needed for images, documents, or media forwarding. |
| **Manage Messages** | Needed for moderation bots that delete or clean messages. |

**Avoid Administrator permission in production.** Discord's role and channel system is detailed enough that most bots do not need full administrative power. A permission mistake in a live community can expose channels or allow unwanted actions.

***

## Why Does the Bot Join but Still Not Work?

A bot can join a server successfully and still fail because installation permission and channel permission are different layers. Channel-level settings decide whether a member or app can view a channel, read history, or send messages there. Most bot functionality issues stem from channel-level permission overrides rather than installation errors. The View Server As Role feature, introduced in 2022, allows administrators to audit exactly what any role can access. This tool reduces debugging time compared to manual permission checking.

**Common causes after successful join:**

1. The bot role is denied **View Channel** in the target channel.
2. The bot role lacks **Send Messages** in the target channel.
3. A channel-specific deny overrides a server-level allow.
4. Slash commands were not installed with the **applications.commands** scope.

**Debugging method:**

Discord's **View Server As Role** feature lets admins preview what a role can access. Open **Server Settings > Roles**, select the bot role, and click **View Server As Role** to see exactly which channels and actions are available.

***

## Which Method Should I Use: Developer Portal or App Directory?

Use the Developer Portal at discord.com/developers/applications for custom bots, test bots, private apps, and custom integrations. Use the App Directory for public apps with published Discord profiles. The Developer Portal method generates a custom invite URL with precise scopes and permissions, offering full control over permission selection. The App Directory method browses and installs public apps from inside Discord. Both methods end with an authorization flow. Custom bot installations typically use the Developer Portal OAuth2 URL Generator, while the App Directory handles public app installations. The Developer Portal supports advanced configurations including webhook endpoints and privileged intents.

| Method | Best For |
|--------|----------|
| **Developer Portal + OAuth2 URL Generator** | Custom bots, test bots, private apps, custom integrations |
| **App Directory** | Public apps with published Discord profiles |

***

## How Do I Confirm the Bot Was Added Correctly?

<!-- [IMAGE_PLACEHOLDER]
Type: annotated_screenshot
Location: Discord server → Server Settings → Integrations → Bots and Apps
What to capture: The Integrations page showing the bot listed under "Bots and Apps" with its icon and name visible
Annotations needed: Red rectangle around the bot entry in the list, arrow pointing to bot name, label "Verified" in green box
Alt text: Discord server Integrations page showing the added bot listed under Bots and Apps
Figcaption: Verifying the bot installation in Discord server settings. The bot appears in Server Settings > Integrations > Bots and Apps when added correctly.
Dimensions: 1200x700px
Priority: medium
-->

Verify the bot installation in three places: the member list, the integrations page, and through a test action. Confirm the bot appears in the server member list, check Server Settings > Integrations > Bots and Apps to verify the bot is listed, and send one test message in a channel the bot should access. Successful bot installations typically pass all three verification checks within minutes. If the bot appears in the member list and integrations page but does not respond, check channel-level permissions next. Discord's integration dashboard provides real-time status updates for all connected applications.

1. **Member list:** Confirm the bot appears in the server member list.
2. **Integrations page:** Go to **Server Settings > Integrations > Bots and Apps** and confirm the bot is listed.
3. **Test action:** Send one test message in a channel the bot should access, or run one basic slash command.

***

## Related Guides

- [How to Get a Discord Bot Token](get_discord_bot_token.md)
- [Auto Send Discord Messages to Another Channel With a Bot](auto-send-discord-messages-to-anther-channel-with-bot.md)
- [Discord to Discord: Setup Guide](discord-to-discord.md)
- [System Settings](system-settings.md)

***

## Key Takeaways

- Generate OAuth2 invite URL from Discord Developer Portal at discord.com/developers/applications.
- Server owner or Manage Server permission is required for bot authorization.
- Select only necessary permissions. Avoid Administrator in production environments.
- Channel-level permissions override server-level roles and can block bot functionality.
- Verify installation through member list, integrations page, and test action.

***

## Frequently Asked Questions

**Can a bot be added to multiple servers?**

Yes. The same bot application can be invited into any number of servers. Each installation is independent and requires a user with Manage Server permission on that specific server.

**What happens if the wrong permissions were selected?**

The bot must be kicked and re-invited with a new OAuth2 URL containing the corrected permissions. Discord does not allow editing permissions after installation without re-authorization.

**Can a bot be added without the Developer Portal?**

Public apps can be added through the Discord App Directory. Custom or private bots must use the Developer Portal OAuth2 URL Generator.

**Why does Discord ask for a CAPTCHA during authorization?**

Discord displays a CAPTCHA to verify the authorizing user is human. This is a standard security measure and does not indicate a problem with the bot.

**Can the bot be restricted to specific channels after joining?**

Yes. Use channel permission overrides to deny the bot role access to channels it should not see or post in. This is recommended for least-privilege security.

**How many servers can one bot join?**

Discord allows bots to join up to 100 servers by default. Verified bots can join up to 200 servers. Large bots with special verification can join unlimited servers.

**What is the difference between bot and user scopes?**

Bot scopes grant permissions to the bot application itself. User scopes grant permissions to the Discord account authorizing the bot. Most server bots require only the bot scope.

***

## Get Started

Add a Discord bot to a server and connect it to D2T Auto Forward in under three minutes:

- **Web Dashboard:** [D2T Auto Forward web dashboard at discordtotelegram.com](https://discordtotelegram.com)
- **Android:** [D2T Auto Forward Android app on Google Play](https://play.google.com/store/apps/details?id=com.autoforward.dc2tele)
- **iOS:** [D2T Auto Forward iOS app on the App Store](https://apps.apple.com/app/d2t-auto-forward-message/id6743234921)
- **Video Tutorial:** [RedFox Official YouTube channel](https://www.youtube.com/channel/UCYw0Y-7wtBHyM6sDGdHH1lA)
