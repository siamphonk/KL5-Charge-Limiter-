# 🔋 KL5 Charge Limit

A simple and lightweight charging limiter module for the **TECNO Spark 30C (KL5)**.

KL5 Charge Limit automatically stops charging when the battery reaches **80%** and resumes charging when it drops to **78%**.

The module uses the device's actual charging control node instead of simply changing the Android battery status.

---

## ✨ Features

- 🔋 Automatic charging limit at **80%**
- ⚡ Charging resumes at **78%**
- 🔄 2% hysteresis to prevent rapid ON/OFF switching
- 🔌 Detects charger connection and disconnection
- 🧠 Uses the actual KL5 charging control interface
- 🔔 Toast notifications
- 📢 System notifications
- 🌓 Transparent Helper Activity
- 🚫 No launcher icon for the Helper APK
- 📱 Helper APK is automatically installed with the module
- 🪶 Lightweight and minimal
- 📝 Detailed charging activity log
- 🛠️ Designed for KernelSU / root environments

---

## 📱 Supported Device

### TECNO Spark 30C

**Device:** `KL5`

> ⚠️ This module was developed and tested specifically for the TECNO Spark 30C (KL5).

It may work on other devices with a compatible charging control interface, but they are **not officially supported**.

---

## ⚙️ How It Works

The module monitors the battery level and charger state.

### Charging Logic

| Battery Level | Action |
|---|---|
| 🔋 80% or higher | Charging OFF |
| 🔋 79% | Keep previous state |
| 🔋 78% or lower | Charging ON |

This hysteresis prevents the charging controller from repeatedly switching between ON and OFF around the limit.

### Example

```text
Battery: 77%
       ↓
Charging ON ⚡
       ↓
Battery: 80%
       ↓
Charging OFF 🛑
       ↓
Battery slowly drops
       ↓
Battery: 78%
       ↓
Charging ON ⚡

## 🔔 Notifications
The Helper APK provides user notifications for charging state changes.
Supported modes:
toast — Toast only
notification — System notification only
both — Toast + notification
The current release uses: both (will update in future release)

## 📦 Installation
Requirements
🔓 Unlocked bootloader
👑 Root access
KernelSU or compatible root environment
TECNO Spark 30C (KL5)
Steps
Download the latest module ZIP from Releases.
Open KernelSU Manager.
Go to Modules.
Choose Install from storage.
Select the KL5 Charge Limit ZIP.
Reboot the device.
The Helper APK will be installed automatically during module installation.
🗑️ Uninstallation
Simply remove the module from your root manager and reboot.