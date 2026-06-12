# 📭 Bot Not Forwarding Messages – How to Troubleshoot

**📭 Bot Not Forwarding Messages – How to Troubleshoot**

If you notice that the bot isn’t forwarding messages as expected, don’t worry — this guide will walk you through the common causes and how to resolve them quickly.

***

### 🛠️ Step 1: Review All Active Filters and Rules

Before assuming there’s a bug, it’s important to check if the issue is caused by any filtering or automation features you’ve enabled.

Please carefully review the following:

**✅ Blacklist**

Blocks messages containing specific keywords, usernames, or content types.

➡️ Check if the message being blocked contains any blacklisted items.

**✅ Whitelist**

Allows the bot to forward only messages that match certain criteria.

➡️ Make sure the source of your message is on the allowed list.

**✅ Filters**

Filters can restrict message types such as:

• Only text

• Only media (photos/videos)

• Only forwarded messages

➡️ Ensure the filter settings are not too restrictive.

**✅ Cleaner**

Automatically deletes certain messages after they’re received.

➡️ This could remove messages before they are forwarded.

**✅ Rules (Custom Conditions)**

You may have defined rules that unknowingly exclude certain message types or sources.

➡️ Disable all rules temporarily to test if they are the cause.

**✅ Other Active Tasks**

Check whether other forwarding tasks are working properly.

➡️ If all tasks are failing, the issue may be global (e.g. network, bot permissions, or system-wide settings).

***

> ⚠️ Pro Tip: If you’re not sure which filter is causing the issue, try disabling all filters and rules. Then test if the bot works normally again.

***

### 🧪 Step 2: Simulate the Problem in a New Test Setup

If the issue persists even with all filters and rules disabled, please help us investigate further by creating a new, clean test environment.

#### 🔧 What You Need to Do:

#### 1. Create a New Discord Server

• You can make it private and empty — just for testing.

#### 2. Create a New Telegram Channel

• Set it to public or private — either is fine.

#### **3. Setup a new Task Forward**

Create a simple forwarding task from the Discord server to the Telegram Channel.

{% content-ref url="../../guides/setup-new-task-auto-forward.md" %}
[setup-new-task-auto-forward.md](../../guides/setup-new-task-auto-forward.md)
{% endcontent-ref %}

{% embed url="https://www.youtube.com/watch?v=LzQfvkXyPXc" %}

***

#### 📤 Step 3: Share the Following Info with [Admin](https://t.me/redf0x1)

Once you’ve set up the test environment, please send the following:

• **🔗 Invitation link to the Discord server**

**• 👤 Your Discord username**

**• 🔗 Invitation link to the Telegram channel**

**• 🔗 GRANT ACCESS AS ADMIN IN TELEGRAM CHANNEL TO SUPPORT FIX BUG**

You can send this information directly to the [admin](https://t.me/redf0x1) via our support contact.

***

### 🧑‍💻 Step 4: Admin Will Help Troubleshoot

Once we receive your test setup and links, our team will:

• Verify bot connectivity

• Reproduce the issue

• Help identify the root cause

• Guide you through the fix (or apply it directly)

***

❓ Need Help?

If you need assistance during setup or have questions, don’t hesitate to contact our support team. We’re here to make sure your bot runs smoothly!
