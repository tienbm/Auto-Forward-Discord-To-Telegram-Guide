# How to Get a Discord Bot Token

A **Discord bot token** is the secret authentication credential for a Discord bot account. It grants the bot access to Discord API routes and the real-time gateway. This guide covers how to create, copy, and secure a bot token from the Discord Developer Portal.

***

## TL;DR

Open the Discord Developer Portal at discord.com/developers/applications. Select the application, go to the **Bot** page, and click **Reset Token** if the copy button is no longer visible. Complete Discord's identity verification step, then copy the new token immediately. Discord only shows the regenerated token once. Store it securely and replace the old token everywhere it was used.

***

## What Is a Discord Bot Token?

A Discord bot token is a secret string that authenticates a bot account with Discord's servers. Discord authenticates bot accounts using tokens rather than usernames and passwords. The token gives the bot access to API routes and the real-time gateway.

Prefer a video walkthrough? See the [RedFox Official YouTube channel](https://www.youtube.com/channel/UCYw0Y-7wtBHyM6sDGdHH1lA) for a visual guide on generating and securing bot tokens.

**Security implications:**

- A token functions like a password. Anyone with the token can run the bot and send requests as the application.
- Tokens must never be shared in public repositories, screenshots, or chat messages.
- If a token is leaked, it must be reset immediately. The old token becomes invalid as soon as a new one is generated.

***

## When Should the Token Be Reset?

Reset the token when the copy button is no longer visible on the Bot page. Discord hides the token after the first view for security reasons. The only way to obtain a usable token again is to regenerate it.

**Common reasons to reset:**

- The token was viewed once and the page was closed.
- The token was lost or not stored securely.
- The token was leaked or shared accidentally.
- The old token needs to be invalidated as a security measure.

***

## How Do I Get a Bot Token Step by Step?

Follow this sequence to obtain or regenerate a token:

**Step 1: Open the Developer Portal**

1. Navigate to discord.com/developers/applications.
2. Sign in with the Discord account that owns the application.

**Step 2: Select the application**

1. Click the application that owns the bot.
2. If no application exists, click **New Application** and create one first.

**Step 3: Open the Bot page**

1. Click **Bot** in the left sidebar.
2. Scroll to the **Token** area.

**Step 4: Reset the token**

1. Click **Reset Token** if the copy button is not visible.
2. Confirm the reset action in the pop-up window.
3. Complete the requested identity verification. This may be a password prompt, an MFA code, or another approval step depending on account security settings.

**Step 5: Copy and store**

1. Copy the new token as soon as Discord displays it.
2. Paste the token into the target system immediately.
3. Store the token in a secure location, such as a password manager or cloud secret manager.

**Step 6: Replace the old token**

1. Update the token in all environments that use it: code, `.env` files, CI secrets, hosting platforms, and third-party integrations.
2. Restart the bot or redeploy the service.

**Pre-flight checklist:**

| Requirement | Why it matters |
|-------------|----------------|
| Correct application selected | Tokens are tied to a specific bot, not the whole account. |
| Bot user already exists | The token lives in the Bot settings for that application. |
| Verification method available | Discord requires identity confirmation before revealing a regenerated token. |
| Safe storage ready | Discord only exposes the regenerated token once. |

***

## What Verification Step Should Be Expected?

Discord requires an identity check before revealing a regenerated token. The exact method depends on account security settings.

**Possible verification methods:**

- Account password
- Two-factor authentication code from an authenticator app
- Passkey or security key
- SMS backup code

The flow is the same regardless of method: verify identity, then copy the new token immediately.

***

## Where Should the Token Be Stored?

The token must be stored securely and never exposed in public files or screenshots.

**Recommended storage locations:**

1. A `.env` file used by bot code. Ensure this file is in `.gitignore`.
2. A cloud secret manager such as Vercel, Railway, Render, AWS Secrets Manager, or Google Cloud Secret Manager.
3. The bot connection form inside the [D2T Auto Forward web dashboard at discordtotelegram.com](https://discordtotelegram.com).
4. A secure local password manager if preparing deployment but not yet pasting into production.

**Prohibited storage locations:**

- Public GitHub repositories
- Screenshots or screen recordings
- Chat messages or email
- Unencrypted text files on shared drives

***

## What Happens If a Token Is Leaked?

If a bot token is leaked, reset it immediately and update every service that still uses the old value. Any code or setup using the older token will stop working until the new token is pasted in.

**Response checklist:**

1. Reset the token in the Developer Portal.
2. Replace the token in code, `.env` files, CI secrets, and hosting platforms.
3. Restart the bot or redeploy the service.
4. Audit logs and app behavior for unauthorized actions.
5. Remove the leaked token from screenshots, chat history, notes, or commit history.

***

## Related Guides

- [How to Add a Discord Bot to a Server](how-to-add-discord-bot-to-server-discord.md)
- [Auto Send Discord Messages to Another Channel With a Bot](auto-send-discord-messages-to-anther-channel-with-bot.md)
- [Discord to Discord: Setup Guide](discord-to-discord.md)
- [System Settings](system-settings.md)

***

## Key Takeaways

- A bot token is the secret credential that authenticates a Discord bot with Discord's API.
- Discord only shows the regenerated token once. Copy it immediately and store it securely.
- Reset the token if it was lost, leaked, or if the copy button is no longer visible.
- Never store tokens in public repositories, screenshots, or chat messages.
- Update the new token in all environments before restarting the bot.

***

## Frequently Asked Questions

**Can the same token be copied more than once?**

No. Discord hides the token after the first view. To obtain it again, the token must be reset.

**Does resetting the token break the running bot?**

Yes. The old token stops working immediately. Update all services with the new token before the bot can function again.

**Can a token be recovered without resetting?**

No. There is no "reveal" or "recover" function. Reset is the only option.

**Should the token be shared with team members?**

No. Each team member should use their own credentials or access the token through a secure secret manager. Direct sharing creates a leak risk.

**How often should the token be rotated?**

Rotate the token whenever there is a suspected leak, a team member departure, or a major deployment change. There is no fixed rotation schedule, but proactive rotation reduces long-term risk.

***

## Get Started

Generate a Discord bot token and connect it to D2T Auto Forward in under two minutes:

- **Web Dashboard:** [D2T Auto Forward web dashboard at discordtotelegram.com](https://discordtotelegram.com)
- **Android:** [D2T Auto Forward Android app on Google Play](https://play.google.com/store/apps/details?id=com.autoforward.dc2tele)
- **iOS:** [D2T Auto Forward iOS app on the App Store](https://apps.apple.com/app/d2t-auto-forward-message/id6743234921)
- **Video Tutorial:** [RedFox Official YouTube channel](https://www.youtube.com/channel/UCYw0Y-7wtBHyM6sDGdHH1lA)
