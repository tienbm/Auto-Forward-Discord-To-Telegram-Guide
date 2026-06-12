# 🌀 Replace : Create And Management

### **Overview**

The **Replace** feature in Auto Forward Bot allows you to modify message content before it is forwarded. This is particularly useful when you want to:

* Customize forwarded messages to match your target audience.
* Remove sensitive or unwanted information.
* Add consistent branding or formatting.

With the replace feature, you can define rules to substitute specific text within messages.

{% hint style="warning" %}
This feature will not work if you enable "**Show Header Forwarder**" in task list
{% endhint %}

## **1. Accessing the Replace Feature**

1. Log in to the[ Auto Forward Web](https://web.discordtotelegram.com) Dashboard.
2. In the left-hand menu under **Features**, click on **Replace**.

<div align="left"><figure><img src="../.gitbook/assets/image (16).png" alt="" width="375"><figcaption></figcaption></figure></div>

Next Tap on the **Add New** button (as shown in the image below):

<div align="left"><figure><img src="../.gitbook/assets/image (6).png" alt="" width="375"><figcaption></figcaption></figure></div>

## **2. Create Replace Rule**

The **Create Replace** feature allows you to define rules to modify message content before forwarding. It supports various replace types, including **Basic**, **Regex**, and advanced options for removing or keeping specific lines.

<figure><img src="../.gitbook/assets/image (17).png" alt=""><figcaption></figcaption></figure>

***

### **1. Replace Options**

When creating a replace rule, you can choose a **Replace Type** from the dropdown menu:

| Replace Type                             | Description                                                                                          |
| ---------------------------------------- | ---------------------------------------------------------------------------------------------------- |
| **Basic**                                | Replace specific words or phrases.                                                                   |
| **Use Regex**                            | Use Regular Expressions (Regex) for advanced replacements.                                           |
| **Remove Empty Lines**                   | Automatically remove all empty lines.                                                                |
| **Remove Lines By Keywords**             | Remove lines containing specific keywords.                                                           |
| **Remove Lines By Line Number**          | Remove lines based on their line numbers.                                                            |
| **Replace Power**                        | A powerful feature that combines multiple syntaxes and supports Regex to remove or replace keywords. |
| **Keep The Line Containing The Keyword** | Only keep lines containing specific keywords.                                                        |

***

### **2. Creating a Replace Rule**

Follow these steps to create a replace rule:

#### **Step 1: Choose Replace Type**

1. In the **Replace Type** dropdown, select the desired type (e.g., Basic, Use Regex, Remove Empty Lines).

**Example**:

* For simple word replacement, select **Basic**.
* For advanced patterns, select **Use Regex**.

***

#### **Step 2: Fill in Replace Details**

1.  **Label** (_Required_):

    * Enter a name for your replace rule. The label must meet the following guidelines:
      * <mark style="color:orange;">**Length**</mark><mark style="color:orange;">: Less than</mark> <mark style="color:orange;"></mark><mark style="color:orange;">**20 characters**</mark><mark style="color:orange;">.</mark>
      * <mark style="color:orange;">**Characters**</mark><mark style="color:orange;">: Only letters (</mark><mark style="color:orange;">**a-z**</mark><mark style="color:orange;">), numbers (</mark><mark style="color:orange;">**0-9**</mark><mark style="color:orange;">), hyphens (</mark><mark style="color:orange;">**-**</mark><mark style="color:orange;">), and underscores (</mark><mark style="color:orange;">**\_**</mark><mark style="color:orange;">).</mark>
      * <mark style="color:orange;">**Case-Insensitive**</mark><mark style="color:orange;">:</mark> <mark style="color:orange;"></mark><mark style="color:orange;">`example`</mark> <mark style="color:orange;"></mark><mark style="color:orange;">and</mark> <mark style="color:orange;"></mark><mark style="color:orange;">`Example`</mark> <mark style="color:orange;"></mark><mark style="color:orange;">are treated the same.</mark>
      * <mark style="color:orange;">**No Whitespace**</mark><mark style="color:orange;">: Spaces are not allowed.</mark>

    **Examples of valid labels**:

    * <mark style="color:green;">`replace_rule_1`</mark>
    * <mark style="color:green;">`clean-text`</mark>
    * <mark style="color:green;">`filter2024`</mark>
2. **Full Content Original** (_Optional_):
   * Paste the full message content to preview or test matches.
3. **Original Words** (_Required_):
   * Insert the exact word, phrase, or regex pattern you want to replace.
4. **New Words Replace** (_Required_):
   * Insert the new text to replace the original content.
5. **(Optional) Apply For Task**:
   * Specify the task or forward rule this replace rule will apply to (leave blank for all tasks).

***

#### **Step 3: Save the Rule**

1. Click **Create Replace** to save the rule.
2. The rule will now be listed under the **Replace** section.

***

## **3. Replace Type**

### **Basic Replace**

Replace simple words or phrases with new content.

| **Use Case**                 | **Original Text** | **New Text**    | **Result**                    |
| ---------------------------- | ----------------- | --------------- | ----------------------------- |
| Replace "black" with "white" | `black`           | `white`         | `I like white.`               |
| Remove the word "do not"     | `do not`          | _(Leave blank)_ | `I like black.`               |
| Replace "under the moon"     | `under the moon`  | `on the sun`    | `Sometimes I lay on the sun.` |

**Steps to Use in App**:

<figure><img src="../.gitbook/assets/image (165).png" alt=""><figcaption></figcaption></figure>

1. Select **Basic** as the Replace Type.
2. Enter:
   * **Original Words**: Text to be replaced (e.g., "black").
   * **New Words Replace**: Replacement text (e.g., "white").
3. Save the rule.

### **Regex Replace**

The **Regex Replace** feature allows you to perform advanced message replacements using **Regular Expressions (Regex)**. Regex is a powerful tool for matching and manipulating text patterns in messages, making it ideal for complex tasks like removing URLs, mentions, or specific patterns.

Using **Regex Replace** requires a basic understanding of **Regular Expressions (Regex)**. If you are not familiar with Regex, it’s recommended to:

* Start with simpler replacements using **Basic Replace**.
* Learn basic Regex patterns for common use cases.

***

<figure><img src="../.gitbook/assets/image (166).png" alt=""><figcaption></figcaption></figure>

#### **1. Replace "good" or "perfect" with "bad"**

**Use Case**: Replace the words "good" or "perfect" with "bad".

**Input**:

* **Original Words**: `(good|perfect)`
* **New Words Replace**: `bad`

**Example Message**:

```
This is a good day, everything is perfect.
```

**Result**:

```
This is a bad day, everything is bad.
```

***

#### **2. Replace URLs or mentions with a fixed text**

**Use Case**: Replace all URLs or mentions (e.g., `@username` or `https://example.com`) with "@Auto\_Forward\_Messages\_Bot".

**Input**:

* **Original Words**: `(@|www|https?)\S+`
* **New Words Replace**: @Auto\_Forward\_Messages\_Bot

**Example Message**:

```
Visit https://example.com or contact @username for more info.
```

**Result**:

```
Visit @Auto_Forward_Messages_Bot or contact @Auto_Forward_Messages_Bot for more info.
```

***

#### **3. Remove unnecessary phrases and keep core content**

**Use Case**: Remove unwanted phrases like "✉️TPA trading report" and "The monitoring will be continued".

**Input**:

* **Original Words**: `(?:.*)(BUY|SELL)(.*)\n(?:.*)`
* **New Words Replace**: `\1\2`

**Example Message**:

```
✉️TPA trading report:
TPA: Entry BUY  UUDCHF M30 at 2023.06.16 15:30
The monitoring will be continued.
```

**Result**:

```
BUY  UUDCHF M30 at 2023.06.16 15:30
```

***

#### **4. Replace "Take profit" with "TP"**

**Use Case**: Replace "Take profit (1|2|3) at" with "TP".

**Input**:

* **Original Words**: ^(Take\&#x73;_&#x70;rofit\s_\d(?:➡️|👉)at)`t`
* **New Words Replace**: `TP`

**Example Message**:

```
🚨Signal Alert🚨 
GOLD sell at (@ 1966.40)
Take profit 1👉at 1955.35 
Take profit 2👉at 1938.94 
Take profit 3👉at 1918.62 
Stop loss at 1982.45
🎯Chance of success: 83% 
⚠️Risk 1-2% per trade!
```

**Result**:

```
🚨Signal Alert🚨 
GOLD sell at (@ 1966.40)
TP 1955.35 
TP 1938.94 
TP 1918.62 
Stop loss at 1982.45
🎯Chance of success: 83% 
⚠️Risk 1-2% per trade!
```

***

#### **5. Reformat content for better readability**

**Use Case**: Reformat reports with a new structure.

**Input**:

* **Original Words**: (?:._#)(._)\s+(?:._Long._,\s+(\w+)(?:._))\n+(?:Entry._)\s+(\d+.?\d+)\s+(?:SL._-)(?:._)\s+(\d+-\d+)(?:%)\n+(?:._:)\n(?:._)\s+(\d+.?\d+)(?:._)\n(?:._)\s+(\d+.?\d+)(?:._)\n(?:._)\s+(\d+.?\d+)(?:._)\n(?:._)\s+(\d+.?\d+)(?:.\*)
* **New Words Replace**: \1 Binance futures\nLEVERAGE CROSS \2\nBUY \3\nSELL: \5 \6 \7 \8\nSTOP: \4%

**Example Message**:

```
🔥 #RDNT/USDT (Long📈, x20) 🔥

Entry - 0.2483
SL - 25-30%

Take-Profit:
🥇 0.2534 (40% of profit)
🥈 0.256 (60% of profit)
🥉 0.2586 (80% of profit)
🚀 0.2614 (100% of profit)
```

**Result**:

```
RDNTUSDT Binance futures
LEVERAGE CROSS 20X
BUY   0.2483
SELL: 0.2534 0.256 0.2586 0.2614
STOP: 25%
```

***

#### **Tips for Users**

* Use **Basic Replace** for simple word or phrase replacements.
* Use **Regex Replace** for advanced patterns like URLs, mentions, or multi-line formatting.
* Test your Regex rules on sample messages to ensure accuracy.
* To **remove content**, leave the "New Words Replace" field blank.

***

### **Replace Power**

The **Replace Power** feature is an advanced tool that allows you to apply **multiple replacement rules** at once. You can combine both **Simple Replace** and **Regex Replace** to remove or replace complex patterns in a single operation.

#### **Key Features of Replace Power**

1. Apply multiple replacement rules simultaneously.
2. Support for **Simple Replace** (basic words/phrases).
3. Use **Regex** for advanced text modifications.
4. Each syntax rule corresponds to one line.

Replace Power allows you to add **multiple replacement rules**.&#x20;

**For example:**

1. **Rule 1** (Simple Mode):
   * **Original Words** = `2+1=3` → **Replace Words** = 2+2=4
2. **Rule 2** (Regex Mode):
   * **Original Words** = `(@|www|https?)\S+` → **Replace Words** = `@Auto_Forward_Messages_Bot`
3. **Rule 3** (Simple Mode):
   * **Original Words** = `url:tag` → **Replace Words** = `customer`

<figure><img src="../.gitbook/assets/image (19).png" alt=""><figcaption></figcaption></figure>

***

### **Using Shortcodes in Replace Features**

Shortcodes allow you to dynamically insert message details like sender names, message IDs, and original text when creating replacement rules. These shortcodes can be used across all **Replace Types**, including **Basic**, **Regex**, and **Replace Power**.



Shortcodes can be used in the following **Replace Types**:

| **Replace Type**  | **Description**                                                               |
| ----------------- | ----------------------------------------------------------------------------- |
| **Basic**         | Replace simple words or phrases with static or shortcode values.              |
| **Use Regex**     | Use Regular Expressions (Regex) combined with shortcodes for dynamic results. |
| **Replace Power** | Apply multiple replacement rules with shortcodes in a single operation.       |

***

#### **Supported Shortcodes**

These shortcodes allow you to dynamically include attributes from the message source:

| **Shortcode**            | **Description**                                      |
| ------------------------ | ---------------------------------------------------- |
| `[[FULL_TEXT]]`          | Replaces the full content of the original message.   |
| `[[ORIGIN_USERNAME]]`    | Sender's username.                                   |
| `[[ORIGIN_USERID]]`      | Sender's user ID.                                    |
| `[[ORIGIN_TEXT]]`        | The original message text.                           |
| `[[ORIGIN_NAME]]`        | Sender's display name or channel name.               |
| `[[ORIGIN_POST_ID]]`     | The ID of the original post.                         |
| `[[ORIGIN_CHAT_ID]]`     | The ID of the originating chat.                      |
| `[[ORIGIN_QUOTED_TEXT]]` | The quoted text from the original post.              |
| `[[ORIGIN_NAME_URL]]`    | The link associated with the original sender's name. |
| `[[FROM_USER]]`          | The username of the message sender.                  |
| `[[SOURCE_NAME]]`        | The name of the forwarded source.                    |
| `[[SENDER_CHAT]]`        | The display name of the sender.                      |
| `[[FORWARD_FROM_CHAT]]`  | The name of the original message owner.              |

#### **Examples for Using Shortcodes**

#### **Example 1: Replace Full Message Content**

**Replace Type**: **Basic**

* **Original Words**: `[[FULL_TEXT]]`
* **New Words Replace**: `Hello! This message was forwarded by [[SOURCE_NAME]].`

**Original Message**:

```yaml
Important announcement: Meeting tomorrow at 10 AM.
```

**Result**:

```csharp
Hello! This message was forwarded by Channel_Name.
```

***

#### **Example 2: Add Sender Information Using Shortcodes**

**Replace Type**: **Basic**

* **Original Words**: `Hi`
* **New Words Replace**: `Hi - Sent by [[ORIGIN_NAME]] ([[ORIGIN_USERID]])`

**Original Message**:

**Original Message**:

```yaml
Hi
```

**Result**:

```csharp
Hi - Sent by John Doe (12345678)
```

***

### **Remove Lines Without Keywords Using Replace**

The **Remove Lines Without Keywords** feature allows you to keep specific lines from a message that contain certain **keywords**. Any line **without the keywords** will be removed from the final result. This feature is especially useful for filtering message content to keep only relevant information.

#### **How It Works**

* You specify one or more **keywords**.
* The feature will **scan each line** of the message.
* **Only lines containing the keywords** will be kept.

#### **Steps to Use the Feature in the App**

1. Choose  **Keep Lines with Keywords** as your Replace Type.
2. Configure the rule:
   * **Enter Keyword**
   * Tap **+ New Keyword** to add multiple keywords.
   * **Example Keywords**:
     * `BUY`
     * `Take`
     * `Profit`
     * `risk size`
3. Tap **Save** to apply the rule.

#### **Example Scenario**

<figure><img src="../.gitbook/assets/image (25).png" alt=""><figcaption></figcaption></figure>

#### **Original Message**

```yaml
24/11/23 | Market Execution  

Notes:  

📉BUY limit XAUUSD at 1994  
Stop Loss 1990  
Take Profit 1 at 2000  
Take Profit 2 at 2006  
Take Profit  3 at 2026  
•APPROPRIATE risk size 1%  
```

***

#### **Replace Configuration**

* **Keywords**: `BUY,Take Profit,risk size`
* **New Words Replace**: `KEEP`

***

#### **Final Result**

Only lines containing the specified keywords (`BUY`, `Take Profit`, or `risk size`) will be kept:

```yaml
📉BUY limit XAUUSD at 1994  
Take Profit 1 at 2000  
Take Profit 2 at 2006  
Take Profit 3 at 2026  
•APPROPRIATE risk size 1%  
```

***

### **Remove Lines by Keyword Using Replace**

The **Remove Lines by Keyword** feature allows you to **remove lines** from a message if they contain one or more specific **keywords**. This feature helps you filter out irrelevant or unwanted lines while keeping the rest of the content intact.

#### **How It Works**

* You provide **keywords** to match lines in the message.
* If a line contains any of the specified keywords, it will be **removed** from the final output.

**Steps to Use the Feature**

* Enter the keywords that will be used to identify and remove lines containing them.
* Tap **+ New Keyword** to add multiple keywords.
* **Example Keywords**:
  * `Market`
  * `Notes`
  * `risk size`

#### **Example Scenario**

<figure><img src="../.gitbook/assets/image (20).png" alt=""><figcaption></figcaption></figure>

#### **Original Message**

```yaml
24/11/23 | Market Execution  

Notes:  

📉BUY limit XAUUSD at 1994  
Stop Loss 1990  
Take Profit 1 at 2000  
Take Profit 2 at 2006  
Take Profit 3 at 2026  
•APPROPRIATE risk size 1%  
```

#### **Keywords**:

* `Market`
* `Notes`
* `risk size`

#### **Result After Applying the Rule**

Lines containing the keywords **"Market"**, **"Notes"**, and **"risk size"** will be removed:

```yaml
📉BUY limit XAUUSD at 1994  
Stop Loss 1990  
Take Profit 1 at 2000  
Take Profit 2 at 2006  
Take Profit  3 at 2026  
```

***

### **Remove Empty Lines Using Replace**

The **Remove Empty Lines** feature allows you to clean up messages by removing all blank or empty lines. This ensures your forwarded content is clean and well-formatted.

<figure><img src="../.gitbook/assets/image (22).png" alt=""><figcaption></figcaption></figure>

#### **Example Scenario**

#### **Original Message**

```yaml
24/11/23 | Market Execution  

Notes:  

📉BUY limit XAUUSD at 1994  

Stop Loss 1990  

Take Profit 1 at 2000  

Take Profit 2 at 2006  

Take Profit 3 at 2026  

•APPROPRIATE risk size 1%  
```

#### **After Applying the Rule**

All empty lines are removed, and the content becomes:

```yaml
24/11/23 | Market Execution  
Notes:  
📉BUY limit XAUUSD at 1994  
Stop Loss 1990  
Take Profit 1 at 2000  
Take Profit 2 at 2006  
Take Profit 3 at 2026  
•APPROPRIATE risk size 1%  
```

***

### **Remove Lines By Line Number Using Replace**

The **Remove Lines By Line Number** feature allows you to specify which lines in a message should be removed based on their line order. This is particularly useful when you need to clean up messages by eliminating unnecessary lines.

In the **Replace Type** dropdown menu, select **Remove Lines By Line Number**.

<figure><img src="../.gitbook/assets/image (23).png" alt=""><figcaption></figcaption></figure>

**Configure the Rule**

* **Label**:
  * Enter a descriptive name for your rule.
  * Example: `remove_line_2_5`.
* **Line Order**:
  * Enter the specific line numbers you want to remove.
  * Use commas (`,`) to separate multiple line numbers.
  * Example: `1,3,5` (to remove lines 1, 3, and 5).
* **Optional: Apply For Task**:
  * Select a specific task to apply this rule.

#### **Example Scenario**

#### **Original Message**

```yaml
24/11/23 | Market Execution  
Notes:  
📉BUY limit XAUUSD at 1994  
Stop Loss 1990  
Take Profit 1 at 2000  
Take Profit 2 at 2006  
Take Profit 3 at 2026  
•APPROPRIATE risk size 1%  
```

#### **Remove Lines**: 2, 5

* **Label**: `remove_line_2_5`
* **Line Order**: `2,5`

***

#### **Result After Applying the Rule**

Lines 2 and 5 are removed from the message:

```yaml
24/11/23 | Market Execution  
📉BUY limit XAUUSD at 1994  
Stop Loss 1990  
Take Profit 2 at 2006  
Take Profit 3 at 2026  
•APPROPRIATE risk size 1%  
```

## **4.** Apply/Disable Replace For a Task

The **Replace** feature allows you to apply or disable specific replacement rules for tasks. This guide will show you how to manage Replace rules, enabling them for individual tasks or across all tasks.

#### **Step 1: Access the Replace List**

1. From the **Dashboard**, select the **Replace** feature.
2. You will see a list of all previously created **Replace rules**.

<figure><img src="../.gitbook/assets/image (167).png" alt=""><figcaption></figcaption></figure>

***

#### **Step 2: Select a Replace Rule**

1. Locate the Replace rule you want to manage.
2.  Tap or click on the rule.

    A **popup window** will appear, showing details of the selected Replace rule (as seen in the second image).

<figure><img src="../.gitbook/assets/image (168).png" alt=""><figcaption></figcaption></figure>

***

#### **Step 3: Manage the Replace Rule for Tasks**

In the popup window, you will see the following options:

1. **Activate/Deactivate For Task** (Green Button)
   * Use this option to enable or disable the Replace rule for a specific task.
   * If the Replace rule is already active for the task, clicking this will **deactivate** it.
   * If the Replace rule is inactive, clicking this will **activate** it.

***

2. **Apply For All Tasks** (Blue Button)
   * This option allows you to apply the Replace rule to **all existing tasks**.
   * Use this feature when you want the Replace rule to take effect globally across all your tasks.

***

3. **Edit Replace** (Orange Button)
   * Tap this option to **edit the Replace rule**.
   * You can update the label, Replace syntax, or any other details of the rule as needed.

***

4. **Delete** (Red Button)
   * Use this option to **delete** the Replace rule permanently.
   * Be cautious, as this action cannot be undone.
