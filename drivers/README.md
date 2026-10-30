# 🎮 Grand Theft Auto V (Android) - GPU Drivers Package

This folder contains verified, high-performance **Vulkan GPU Driver packages** for Qualcomm Snapdragon devices, packaged specifically for the **GTA V Android Native Port**.

---

## 📂 Included Driver Packages

| Package Filename | Version & Author | Target Hardware | Recommended For |
|---|---|---|---|
| [`Turnip_v24.3.0_R12.zip`](Turnip_v24.3.0_R12.zip) | **Turnip Mesa 24.3.0 (R12)**<br>by KIMCHI | **Snapdragon 8 Gen 1 / 8+ Gen 1 / 8 Gen 2** *(Adreno 730 / 740)*<br>**Snapdragon 865 / 870 / 888** *(Adreno 650 / 660)* | **🔥 #1 General Recommendation.** High FPS, Vulkan 1.3 compliance, zero vertex stretching. |
| [`Turnip_v24.1.0_R18_A6xx.zip`](Turnip_v24.1.0_R18_A6xx.zip) | **Turnip Mesa 24.1.0 (R18)**<br>by KIMCHI | **Snapdragon 845 / 855 / 860 / 778G** *(Adreno 618 / 620 / 630 / 640 / 642L)* | **⚡ Best for Older Chips.** Ultra-low RAM footprint, low thermal overhead, highest stability on legacy Adreno 6xx. |
| [`Turnip_v26.0.0_R8.zip`](Turnip_v26.0.0_R8.zip) | **Turnip Mesa 26.0.0 (R8)**<br>by KIMCHI | **Snapdragon 8 Gen 3 / 8 Elite** *(Adreno 750 / 830)* | **🚀 Bleeding-Edge.** First Turnip driver supporting the newest Adreno 750 / 830 instruction set. |
| [`Qualcomm_v757_Adreno.zip`](Qualcomm_v757_Adreno.zip) | **Qualcomm v757.0**<br>Extracted from Meta Quest 3 | **Snapdragon Adreno 7xx** *(Adreno 730 / 740 / 750)* | **🛡️ OEM Fallback.** Use if Turnip produces visual texture artifacts on specific custom ROMs or Android 14/15 firmware. |

---

## 📱 Notice for MediaTek (Dimensity / Helio / ARM Mali) Users

> [!IMPORTANT]
> **Do NOT install Turnip driver ZIPs on MediaTek devices.**
> * Turnip is an open-source driver developed strictly for **Qualcomm Adreno** architecture.
> * MediaTek processors (Dimensity 1080, 7050, 8100, 8200, 9000, 9200, 9300, etc.) use **ARM Mali / Immortalis** GPUs (`vulkan.mali.so`).
> * Loading an Adreno driver on a Mali chip will be rejected by the launcher's built-in validator or cause a crash.

### How to get maximum performance on MediaTek:
1. **Leave Driver as System Default:** Keep the driver setting on **System Default Vulkan Driver**.
2. **Native BCN Transcoder:** The GTA V launcher automatically uses `libgtav_bcn.so` to decompress desktop DirectX textures in real time for Mali GPUs.
3. **TBDR Tiler Mode:** Keep **Tiler Mode** enabled in Settings to optimize the rendering pass for Mali's Tile-Based Deferred Rendering architecture.
4. **System Updates:** Ensure your phone is updated to the latest official Android firmware for the latest Mali Vulkan drivers from ARM.

---

## 🚀 How to Install a Driver on Your Device

1. Download the desired `.zip` driver from this folder onto your phone (or transfer via USB).
2. Launch **Grand Theft Auto V**.
3. In the launcher, tap **SETTINGS** (bottom right).
4. Tap the **ENHANCEMENTS** tab on the left.
5. Under **Custom GPU Driver**, tap **SELECT CUSTOM DRIVER (.ZIP)**.
6. Browse and pick the downloaded `.zip` file.
7. The launcher will automatically validate the package (`meta.json`, 64-bit ARM64 ELF, `vkGetInstanceProcAddr`) and activate it immediately.
8. If you ever experience issues, simply tap **RESET TO SYSTEM DEFAULT** to restore the stock driver.

