# Changelog

All notable changes to the Grand Theft Auto V Android native port and launcher are documented in this file.

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
* **Strict WebAssembly Linear Heap Clamping:**
  * Added `clampHeapForDevice()` in `DeviceProfiler` to guarantee at least **1.5 GB – 2.0 GB** of RAM remains unallocated for Android OS, audio daemon, SurfaceFlinger, and the Vulkan driver.
  * Prevents premature Android Low Memory Killer (`SIGKILL` / LMK) terminations on 4GB–8GB RAM devices.
* **Dynamic Engine Environment Overrides:**
  * Engine parameters (`MUGUET_ANDROID_HEAP_GB`, `MUGUET_FPS`, `MUGUET_SCALE`, `WGPU_BC_FALLBACK`, `MUGUET_MUTE`) are now passed directly to native `libmuguet.so` via `android.system.Os.setenv` on startup.

### 🎮 Controls & User Experience
* **Native Gamepad Calibration:**
  * Tuned DualShock 4 and Xbox Bluetooth controller analog deadzones and input debouncing.
* **Overlay & In-Game Touch HUD:**
  * Refined touch HUD toggle responsiveness and character switch wheel handling.

### 🔒 Security & Verification
* **APK Signature Scheme v2:** Cryptographically signed and verified with zero legacy JAR signature vulnerabilities.
* **Binary Integrity:**
  * **File:** `GTAV_Android_v1.1.2_arm64.apk`
  * **Size:** `317,625,211 bytes` (~302.9 MB)
  * **SHA-256:** `67F6A1D96486FC845AC6EB664FA853225A40A80CC8A0C1AD40A6A02964E23CA3`

---

## [1.0.2] - 2026-10-28
* Initial hardened release with Dynamic Resolution Scaling (DRS), dual-stream rotating server security logging, lease grace-period verification, and hardware gamepad integration.

