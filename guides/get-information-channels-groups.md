---
description: >-
  To set up an auto-forward task from Discord to Telegram, you need to have the
  Channel ID information.
---

# ℹ️ Get information channels, groups

### 1. Get information channels Discord

{% hint style="danger" %}
**To retrieve Discord channel ID information, you must first configure both the Discord Token and the Telegram Token.**
{% endhint %}

After completing this configuration step, proceed to the Discord channel where you want to set up auto-forwarding.

<figure><img src="../.gitbook/assets/image (185).png" alt=""><figcaption></figcaption></figure>

At this point, type **`/getid`** and press send.

<figure><img src="../.gitbook/assets/image (186).png" alt=""><figcaption></figcaption></figure>

**The information about the channel, including the Channel ID, will be displayed immediately.**&#x20;

**Copy this ID to set up the forward task.**&#x20;

In the example above, the Channel ID will be **1330086886491947102**.

#### 🟠 **Manual Guide to Retrieve Channel ID from Discord**

<mark style="color:orange;">If the</mark> <mark style="color:purple;">`/getid`</mark> <mark style="color:orange;">command does not work to retrieve channel information, you can manually get the Channel ID by following these steps:</mark>

1. **Go to the Discord channel you want to retrieve the ID from**.
   * Open Discord and navigate to the desired channel.
2. **Copy the channel link**.
   * Right-click on the channel name and select **Copy Link**.
   * Example: The copied link will look like:\
     `https://discord.com/channels/1330015664596848711/1330086886491947102`.
3. **Extract the Channel ID**.
   * The Channel ID is the last numeric part of the link.
     * For example, from the link:\
       `https://discord.com/channels/1330015664596848711/1330086886491947102`,\
       the **Channel ID** is **1330086886491947102**.
4. **Use this ID** in your configuration for the next steps.

***

### 2. Get information channels/Group/User/Bot Telegram

To retrieve information about Telegram channels or groups, use the following bot: [FindMyIDs Bot](https://t.me/FindMyIDs_Bot) or search **@FindMyIDs\_Bot** on Telegram

<figure><img src="../.gitbook/assets/image (187).png" alt=""><figcaption></figcaption></figure>

**With Options**

* **User**: This option allows you to retrieve the ID of a specific Telegram user. You need to share the user's contact or information to get their ID.
* **Group**: This option enables you to get the ID of a Telegram group. You can share the group or forward a message from the group to receive its ID.
* **Channel**: This option lets you retrieve the ID of a Telegram channel. You need to share the channel or forward a message from it to obtain the ID.
* **Bot**: This option allows you to fetch the ID of another Telegram bot. You can share the bot's information or mention it to retrieve the ID.

<figure><img src="../.gitbook/assets/image (188).png" alt=""><figcaption></figcaption></figure>

To retrieve the channel ID, simply select the **Channel** option and then choose the desired channel. In the example above, the channel ID is **-1001716791967**.
