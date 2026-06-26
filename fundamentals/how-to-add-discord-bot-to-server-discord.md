# How to Add a Discord Bot to a Server

Adding a Discord bot to a server authorizes an application to join that server and operate under approved permissions. The bot becomes a server member and can only read, post, or manage content according to the scopes granted during installation.

***

## TL;DR

Create or open the bot in the Discord Developer Portal at discord.com/developers/applications. Go to **OAuth2 > URL Generator**, select the **bot** scope, choose only the permissions the bot actually needs, copy the generated URL, open it in a browser, select the target server, and click **Authorize**. The user performing this step must own the server or have the **Manage Server** permission.

***

## What Does Adding a Bot to a Server Mean?

Adding a Discord bot to a server means granting a Discord application permission to join one specific server and operate there under approved scopes. Creating a bot in the Developer Portal does not automatically place it inside any server. Explicit authorization is required for each target server.

Prefer a video walkthrough? See the [RedFox Official YouTube channel](https://www.youtube.com/channel/UCYw0Y-7wtBHyM6sDGdHH1lA) for a beginner-friendly tutorial on adding bots to Discord servers.

**Key requirements:**

- The user adding the bot must own the server or have the **Manage Server** permission.
- The bot user must already exist inside the application.
- The generated OAuth2 URL must include the correct scopes and permissions.

***

## How Do I Add a Discord Bot Step by Step?

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

For a typical server bot, the main OAuth2 scope is **bot**. Many modern bots also need **applications.commands** so slash commands work correctly.

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

A bot can join a server successfully and still fail because installation permission and channel permission are different layers. Channel-level settings decide whether a member or app can view a channel, read history, or send messages there.

**Common causes after successful join:**

1. The bot role is denied **View Channel** in the target channel.
2. The bot role lacks **Send Messages** in the target channel.
3. A channel-specific deny overrides a server-level allow.
4. Slash commands were not installed with the **applications.commands** scope.

**Debugging method:**

Discord's **View Server As Role** feature lets admins preview what a role can access. Open **Server Settings > Roles**, select the bot role, and click **View Server As Role** to see exactly which channels and actions are available.

***

## Developer Portal vs App Directory

| Method | Best For |
|--------|----------|
| **Developer Portal + OAuth2 URL Generator** | Custom bots, test bots, private apps, custom integrations |
| **App Directory** | Public apps with published Discord profiles |

The Developer Portal method generates a custom invite URL with precise scopes and permissions. The App Directory method browses and installs public apps from inside Discord. Both methods end with an authorization flow, but the Developer Portal offers full control over permission selection.

***

## How Do I Confirm the Bot Was Added Correctly?

Verify the bot installation in three places:

1. **Member list:** Confirm the bot appears in the server member list.
2. **Integrations page:** Go to **Server Settings > Integrations > Bots and Apps** and confirm the bot is listed.
3. **Test action:** Send one test message in a channel the bot should access, or run one basic slash command.

If the bot appears in the member list and integrations page but does not respond, check channel-level permissions next.

***

## Related Guides

- [How to Get a Discord Bot Token](get_discord_bot_token.md)
- [Auto Send Discord Messages to Another Channel With a Bot](auto-send-discord-messages-to-anther-channel-with-bot.md)
- [Discord to Discord: Setup Guide](discord-to-discord.md)
- [System Settings](system-settings.md)

***

## Key Takeaways

- Adding a bot requires generating an OAuth2 invite URL from the Discord Developer Portal.
- The user adding the bot must own the server or have the **Manage Server** permission.
- Select only the permissions the bot actually needs. Avoid **Administrator** in production.
- Channel-level permissions can override server-level roles. Check channel settings if the bot joins but does not work.
- Confirm installation by checking the member list, integrations page, and running a test action.

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

***

## Get Started

Add a Discord bot to a server and connect it to D2T Auto Forward in under three minutes:

- **Web Dashboard:** [D2T Auto Forward web dashboard at discordtotelegram.com](https://discordtotelegram.com)
- **Android:** [D2T Auto Forward Android app on Google Play](https://play.google.com/store/apps/details?id=com.autoforward.dc2tele)
- **iOS:** [D2T Auto Forward iOS app on the App Store](https://apps.apple.com/app/d2t-auto-forward-message/id6743234921)
- **Video Tutorial:** [RedFox Official YouTube channel](https://www.youtube.com/channel/UCYw0Y-7wtBHyM6sDGdHH1lA)
