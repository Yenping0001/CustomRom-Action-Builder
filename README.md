# CustomRom-Action-Builder
# ⚡️ Android ROM Builder (GitHub Actions CI)

A powerful GitHub Actions workflow to build **any Android ROM for any device**, automatically upload the ROM to Telegram, and show build logs, changelogs, MD5, and size.

---

## 🔧 Features

- ✅ Supports any ROM (AfterlifeOS, LineageOS, PixelOS, etc.)
- 📱 Build any device by inputting codename & name
- 🌲 Input your own device/vendor/kernel trees
- 📜 Auto-generates Git changelog from past 7 days
- 📨 Uploads to Telegram channel with all build details
- ❌ Sends failure message if build fails

---

## 🚀 How to Use

1. **Fork this repo**
2. Add the following **GitHub Secrets**:
   | Secret            | Description                          |
   |-------------------|--------------------------------------|
   | `GIT_USERNAME`    | Your Git username                    |
   | `GIT_EMAIL`       | Your Git email                       |
   | `TG_BOT_TOKEN`    | Telegram bot token from [@BotFather](https://t.me/BotFather) |
   | `TG_CHAT_ID`      | Telegram **channel ID or username** (see below) |

3. Go to **Actions → ROM Builder → Run workflow**
4. Enter your ROM/device build configuration:
   - ROM name (e.g. AfterlifeOS)
   - Manifest URL and branch
   - Device codename (e.g. `violet`)
   - Device name (e.g. `Redmi Note 7 Pro`)
   - Lunch combo (e.g. `afterlife_violet-userdebug`)
   - Device tree URL
   - Vendor tree URL
   - Kernel tree URL

---

## 📨 Setting Up Telegram Channel Notifications

To receive build results in a **Telegram channel**, follow these steps:

### 🔹 Step 1: Create Your Channel
- Create a **Telegram Channel** (public or private)
- Example name: `AfterlifeOS Builds`

### 🔹 Step 2: Add Your Bot as Admin
- Use [@BotFather](https://t.me/BotFather) to create a bot and get the token
- Add your bot to the channel as an **admin**
- Enable the permissions:
  - ✅ Post Messages
  - ✅ Send Media

### 🔹 Step 3: Get the Channel ID
- **Public channel:** use `@channelusername` (e.g. `@AfterlifeOSBuilds`)
- **Private channel:** get the ID using [@userinfobot](https://t.me/userinfobot), you'll get a numeric ID like `-1001234567890`

### 🔹 Step 4: Set in GitHub Secrets
In your repo, go to **Settings → Secrets → Actions** and add:

| Key           | Value                     |
|---------------|---------------------------|
| `TG_CHAT_ID`  | `@AfterlifeOSBuilds` *or* `-100xxxxxxxxxx` |

That's it! The workflow will now post all build results to your channel.

---

## 📦 Telegram Output Example
🎯 AfterlifeOS Build Summary
📱 Device: violet ( Redmi Note 7 Pro )
📦 Filename: AfterlifeOS-violet-20250621.zip
🧩 Size: 1.9G
🔐 MD5: abc123456...
⏱️ Build Time: 41 minutes
✅ Status: Build completed successfully via GitHub Actions



---

## 📱 Example Build Configuration (Redmi Note 7 Pro)

| Field              | Value                                                           |
|-------------------|------------------------------------------------------------------|
| ROM Name          | AfterlifeOS                                                     |
| Manifest URL      | https://github.com/AfterlifeOS/android_manifest.git            |
| Manifest Branch   | 14                                                              |
| Device Codename   | violet                                                          |
| Device Name       | Redmi Note 7 Pro                                                |
| Lunch Combo       | goafterlife violet-userdebug                                    |
| Device Tree       | https://github.com/Afterlife-Devices/device_xiaomi_violet       |
| Vendor Tree       | https://github.com/Afterlife-Devices/vendor_xiaomi_violet       |
| Kernel Tree       | https://github.com/Afterlife-Devices/kernel_xiaomi_violet       |

---

## ❤️ Credits

- [Afterlife-OS](https://github.com/Afterlife-OS)
- [LineageOS](https://github.com/LineageOS)
- Telegram bot API via [@BotFather](https://t.me/BotFather)
- GitHub Actions for free compute power 💥

---

**Happy Building!** 🧪  
Need help? Open an issue or reach out in your Telegram dev group.

