# ZSocialMediaManager
**ZSocialMediaManager** is a powerful ZygnalBot extension that serves as the central hub for community social media monitoring. It keeps your Discord server updated with the latest content from **YouTube, Twitch, X (Twitter), Reddit, and GitHub**.
> 💡 **Built for the Zygnal Ecosystem — to download and use this extension, you must be part of the Zygnal Ecosystem.**  
> This extension (cog) is part of the **Zygnal Ecosystem** and is only available through its supported platforms.  
> You can use it with:  
> - The **[Discord Bot Framework](https://github.com/TheHolyOneZ/discord-bot-framework)** — ideal for developers who want full control and flexibility *(includes an integrated extension marketplace)*, or  
> - The **[ZygnalBot](https://zygnalbot.de)** — a prebuilt, plug-and-play Discord bot *(also includes an integrated extension marketplace)*.  
>
> Browse and install extensions at [zygnalbot.com/extension](https://zygnalbot.com/extension).  
> For help or community discussions, join us on Discord: [discord.gg/sgZnXca5ts](https://discord.gg/sgZnXca5ts)
# ZSocialMediaManager

**ZSocialMediaManager** is a powerful ZygnalBot extension that serves as the central hub for community social media monitoring. It keeps your Discord server updated with the latest content from **YouTube, Twitch, X (Twitter), Reddit, and GitHub**.

Everything is managed through a **user-friendly interactive interface** with buttons and modals, allowing complex notification configurations without memorizing commands.

---

## ⚠️ Important: Initial Setup & Security

When you first load the cog, it creates the directory:

```
data/SocialMediaManager/
```

This folder contains configurations, backups, and **one critical file**:

### `secret.key`

* Encrypts sensitive API credentials (Twitch, X, etc.) using Fernet symmetric encryption.
* **Do not delete, share, or modify**.
* Backup safely; losing it means API keys become unreadable and must be re-entered.

### Automatic Backups

Before saving configurations, a backup is stored in:

```
data/SocialMediaManager/backups/
```

This safeguards against accidental data loss or corruption.

---

## ⭐ Core Features

* **Multi-Platform Support**: YouTube uploads, Twitch streams & videos, X tweets, Reddit posts, GitHub events.
* **Ironclad Security**: API keys encrypted using Fernet.
* **Fully Interactive UI**: Buttons, dropdowns, and modals guide all setup.
* **Customizable Notifications**:

  * Channel assignment per platform
  * Role mentions per platform + global fallback
  * Twitch toggles: Live Streams, Video Uploads, or both
  * Optional thumbnails and metrics in embeds
* **Reliable Operation**:

  * Atomic saves prevent corruption
  * Configurable check intervals (5–60 min)
  * Smart account initialization prevents notification spam
  * Manual & automatic checks available
* **Advanced Diagnostics & Logging**:

  * Dedicated logging channel for real-time operational logs
  * `!smdebug` command inspects account state and notification readiness

---

## 📜 Commands

| Command                         | Description                                | Permissions   |
| ------------------------------- | ------------------------------------------ | ------------- |
| `!socialmedia` / `!scmg`        | Opens Social Media Manager dashboard       | Manage Guild  |
| `!smapi`                        | Opens API Setup dashboard (ephemeral)      | Administrator |
| `!smdebug <platform> [account]` | Shows internal state of monitored accounts | Administrator |

**Usage Examples**:

* `!smdebug` → lists platforms
* `!smdebug twitch` → lists Twitch accounts
* `!smdebug twitch TheZ` → detailed info for "TheZ"

**Output Details**:

* Last known post ID
* Cached recent posts
* Initialization status
* Latest post trigger check

---

## 🖥️ Dashboard & Button Guide

### Main Dashboard (`!socialmedia`)

* **Platform Select Dropdown**: Navigate to platform panel
* **⚙️ Global Settings**: Configure server-wide settings
* **🔄 Check Now**: Manual scan of all platforms with ephemeral summary

### Platform Configuration Panel (example: YouTube)

* **🔄 Toggle Status**: Enable/disable monitoring
* **📺 Set Channel**: Modal to set notification channel
* **🎭 Set Role**: Modal to assign role mention
* **➕ Add Account**: Add social media account
* **🗑️ Remove Account**: Remove monitored accounts
* **🔄 Check This Platform**: Scan only this platform
* **🔧 Initialize Accounts**: Prevents old content notifications, sets baseline for new accounts
* **🔔 Notification Settings (Twitch Only)**: Toggle Live Streams / New Videos
* **🔙 Back to Dashboard**

### Global Settings Panel

* **⏰ Check Interval**: Set auto-check frequency (5–60 min)
* **🎭 Global Role**: Server-wide notification role
* **📋 Logging Channel**: Set detailed logs channel
* **🖼️ Toggle Thumbnails / 📊 Toggle Metrics**: Control embeds display
* **🔙 Back to Dashboard**

### API Setup Panel (`!smapi`)

* **🎮 Twitch API / 🐦 X API / 🔧 GitHub API**: Enter credentials securely
* **🧪 Test All APIs**: Check connections and verify credentials

---

This document contains all details from the original README, formatted for clarity, readability, and easy navigation.
