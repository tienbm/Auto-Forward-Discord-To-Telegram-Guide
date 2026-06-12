# 💫 Setup New Task Auto Forward

**To start creating an auto-forward task, you need to complete the following steps:**

* ✅ [Create account and login your account ](how-to-create-account-and-connect.md)
* ✅ [Setup discord token and telegram token](how-to-create-account-and-connect.md#id-2.-configure-tokens)
* ✅ [Get info channel id discord and channel/group telegram want receive ](get-information-channels-groups.md)

{% embed url="https://youtu.be/LzQfvkXyPXc" %}

✅ **To receive content sent from Discord to Telegram, you must add the Telegram bot you created earlier to the desired channel/group and grant it admin permissions.**

<figure><img src="../.gitbook/assets/image (194).png" alt=""><figcaption></figcaption></figure>

Please add the @**discordtotele\_bot** to your channel as **Admin**.

<figure><img src="../.gitbook/assets/image (195).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (196).png" alt=""><figcaption></figcaption></figure>

Next, access the home screen from the website: [https://web.discordtotelegram.com/#/home](https://web.discordtotelegram.com/#/home)

<figure><img src="../.gitbook/assets/image (189).png" alt=""><figcaption></figcaption></figure>

Here, select **Create Task +**

<figure><img src="../.gitbook/assets/image (191).png" alt=""><figcaption></figcaption></figure>

This is the **Create Task** screen for setting up an auto-forward task between Discord and Telegram. Here's an explanation of each field:

1. **Label** (_Required_):
   * Enter a name for your replace rule. The label must meet the following guidelines:
     * **Length**: Less than **20 characters**.
     * **Characters**: Only letters (**a-z**), numbers (**0-9**), hyphens (**-**), and underscores (**\_**).
     * **Case-Insensitive**: `example` and `Example` are treated the same.
     * **No Whitespace**: Spaces are not allowed.
2. **Discord Channel ID (**_Required_**)**:
   * Input the ID of the Discord channel from which you want to forward messages.
   * Click **+ Add** after entering the ID to save it.
   * [You can review the method to retrieve the channel ID here.](get-information-channels-groups.md#id-1.-get-information-channels-discord)
3. **Telegram Chat ID (**_Required_**)**:
   * Input the ID of the Telegram chat or group where messages should be forwarded.
   * Click **+ Add** after entering the ID to save it.
   * [You can review the method to retrieve the channel ID here.](get-information-channels-groups.md#id-2.-get-information-channels-group-user-bot-telegram)
4. **Telegram Topic ID (Optional)**:
   * If applicable, input the ID of a specific Telegram topic (for chats that support topics).
   * Click **+ Add** after entering the ID to save it.
5. **Create Task Button**:
   * Once all required fields (\*) are completed, click **Create Task** to finalize the setup.

### Example

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

### 2. Get information channels/Group/User/Bot Telegram

To retrieve information about Telegram channels or groups, use the following bot: [FindMyIDs Bot](https://t.me/FindMyIDs_Bot) or search **@FindMyIDs\_Bot** on Telegram

<figure><img src="../.gitbook/assets/image (187).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (188).png" alt=""><figcaption></figcaption></figure>

To retrieve the channel ID, simply select the **Channel** option and then choose the desired channel. In the example above, the channel ID is **-1001716791967**.

<figure><img src="../.gitbook/assets/image (192).png" alt=""><figcaption></figcaption></figure>

Next Click **Create Task and wait create**

<figure><img src="../.gitbook/assets/image (193).png" alt=""><figcaption></figcaption></figure>

✅ **Result**

<figure><img src="../.gitbook/assets/ezgif-4-3e4e3ed85b (1).gif" alt=""><figcaption></figcaption></figure>

