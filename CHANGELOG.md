 Changelog

All notable changes to the Grand Theft Auto V Android native port and launcher are documented in this file.

---

## [1.1.3] - 2026-10-29

### 🚀 Highlights
This hotfix resolves the black screen stall at `"Ludendorff, North Yankton, nine years ago."` on Qualcomm Adreno devices (Snapdragon 8 Gen 2/3/Elite) and introduces a "Direct Los Santos Boot" selector in Launcher Settings.

### 🎮 Graphics & GPU Drivers
* **Qualcomm Adreno WGSL Clip-Distance Hotfix:**
  * Batch-sanitized all 500 `.wgsl` shaders on disk to strip unsupported `enable clip_distances;` and `@builtin(clip_distances)`.
  * Fixes native `naga`/`wgpu` validation failures (`ptfx_sprite::VS_lit`) that triggered `VK_ERROR_DEVICE_LOST` and deadlocked rendering at 0 FPS on Adreno 740/750 GPUs (Galaxy Z Fold, Galaxy S23/S24, OnePlus 12/13).
  * Shaders now strictly comply with standard mobile WebGPU/Vulkan specifications across all Android devices.

### 🌴 Launcher & Story Mode
* **Direct Los Santos Boot Selector:**
  * Added **"DIRECT LOS SANTOS BOOT"** toggle under **Settings → Graphics**.
  * **Enabled (Default):** Spawns immediately as Franklin in open-world Los Santos, bypassing the 15-minute scripted prologue.
  * **Disabled:** Starts the North Yankton bank robbery prologue from the beginning (now fully playable with fixed shaders).
  * Seamlessly synchronized with `config.json` and native environment (`MUGUET_START_MODE`).

### 📦 Release Verification
* **File:** `GTAV_Android_v1.1.3_arm64.apk`
* **Size:** `317,586,968 bytes` (~302.87 MB)
* **SHA-256:** `C2E9F7961735525E8DB2D9971A965B5EF5208EAE6ADCC48664F424F37F9B7EFE`
* **Signature:** APK Signature Scheme v2 (Verified)

---

## [1.1.2] - 2026-10-29

### 🚀 Highlights
This release focuses on multi-vendor GPU stability, driver compatibility fixes for Qualcomm Adreno GPUs, buffer race condition mitigations, and OS-level memory clamping to prevent Low Memory Killer (LMK) aborts.

### 🎮 Graphics & GPU Drivers
* **Adreno Clip-Distance Emulation:**
  * Added automated vendor/architecture detection for Qualcomm Adreno Vulkan drivers.
  * Emulates broken hardware clip planes via software interpolation (`lowerClipDistances`), eliminating black-screen bugs and driver panics on Snapdragon 7xx/8xx/8-Gen series.
  * Native hardware clip path remains active on ARM Mali (Dimensity) and Samsung Xclipse (Exynos).
* **Buffer-Mapping Race Condition Guards:**
  * Implemented defensive `safeUnmap()` and `safeDestroy()` wrappers validating `buf.mapState === 'mapped'` prior to unmapping.
  * Resolves unhandled `OperationError: Buffer is not mapped` crashes in the WebGPU worker thread during scene streaming.
* **CPU Texture Decompression Diagnostic Mode:**
  * Added "Decode BC Textures on CPU" toggle under **Settings → Graphics**.
  * Routes block-compressed textures (BC1–BC7) through bundled `bc_decoder.wasm` (`bcdec`) for devices with buggy or unsupported hardware BC texture compression.

### ⚙️ Engine & Memory Architecture
* **Android OS Game Category & DVFS Optimization:**
  * Declared `android:appCategory="game"` and `android:isGame="true"` in AndroidManifest.
  * Activates OEM gaming services (Samsung Game Booster, Xiaomi Game Turbo, Android Game Dashboard), unlocking maximum CPU clock frequencies (2.6 GHz on Dimensity/Snapdragon) and preventing battery saver throttling.
* **Sustained Performance Mode & Elevated Thread Priority:**
  * Enabled `Window.setSustainedPerformanceMode(true)` to stabilize DVFS clock rates and stop sudden frame pacing drops.
  * Elevated render thread priority to `Process.THREAD_PRIORITY_URGENT_DISPLAY` in Linux CFS scheduler.
  * Registered `GameManager.setGameState(MODE_GAMEPLAY_UNINTERRUPTIBLE)` for Android 13+ devices.
* **Adaptive MSAA Governor (`MUGUET_MSAA_MAX`):**
  * Clamps MSAA to `1` (off) on budget/mid-range hardware (<= 6GB RAM or scale <= 0.70x), recovering 15–20% GPU fillrate on Mali and Adreno chips.
* **Strict WebAssembly Linear Heap Clamping:**
  * Added `clampHeapForDevice()` in `DeviceProfiler` to guarantee at least **1.5 GB – 2.0 GB** of RAM remains unallocated for Android OS, audio daemon, SurfaceFlinger, and the Vulkan driver.
  * Prevents premature Android Low Memory Killer (`SIGKILL` / LMK) terminations on 4GB–8GB RAM devices.
* **Dynamic Engine Environment Overrides:**
  * Engine parameters (`MUGUET_ANDROID_HEAP_GB`, `MUGUET_FPS`, `MUGUET_SCALE`, `WGPU_BC_FALLBACK`, `MUGUET_MSAA_MAX`, `MUGUET_MUTE`) are now passed directly to native `libmuguet.so` via `android.system.Os.setenv` on startup.

### 🎮 Controls & User Experience
* **Native Gamepad Calibration:**
  * Tuned DualShock 4 and Xbox Bluetooth controller analog deadzones and input debouncing.
* **Overlay & In-Game Touch HUD:**
  * Refined touch HUD toggle responsiveness and character switch wheel handling.

### 🔒 Security & Verification
* **APK Signature Scheme v2:** Cryptographically signed and verified with zero legacy JAR signature vulnerabilities.
* **Binary Integrity:**
  * **File:** `GTAV_Android_v1.1.2_arm64.apk`
  * **Size:** `317,626,080 bytes` (~302.9 MB)
  * **SHA-256:** `1EC9F78D3A508CBF032D8CD0D18CAA456D89EBBEFBC44E99DB5EDF12A47F2D87`

---

## [1.0.2] - 2026-10-28
* Initial hardened release with Dynamic Resolution Scaling (DRS), dual-stream rotating server security logging, lease grace-period verification, and hardware gamepad integration.

