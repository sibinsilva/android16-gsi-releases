# Android 16 QPR2 (`bp4a`) Generic System Image (GSI) Releases

Prebuilt **Android 16 QPR2 (`bp4a`)** ARM64 A/B Generic System Images (`system.img.xz`) with Google Apps (GMS) and full hardware support for **ASUS ROG Phone 5 / 5s (`anakin` / `ASUS_I005`)** as well as standard Treble-compliant devices.

- **Maintainer:** `Sibieeeee`
- **Architecture:** `arm64` (`ab` / System-as-Root)
- **Android Version:** Android 16 QPR2 (`BP4A.251205.006`)
- **VNDK Support:** Full VNDK `v28`, `v29`, `v30`, `v31`, `v32`, `v33`, `v34` compatibility included

---

## Highlights & Device Features (ASUS ROG Phone 5 / 5s)
- **Optical UDFPS (In-Display Fingerprint):** `@2.3` HIDL Fingerprint bridge HAL + automatic HBM (`/proc/globalHbm`, `/sys/class/drm/fod_touched`) & 16.16 fixed-point coordinate bridge (`/proc/driver/fp_xy`).
- **Aura Sync RGB & Lighting Triggers:** Full Aura Sync RGB lighting control (2-zone / 3-zone phone-body & Kunai gamepad LEDs), color wheel, and event lighting triggers (calls, notifications, charging, screen on/off).
- **AirTriggers & X-Mode Gaming Controls:** Ultrasonic shoulder triggers, squeeze force thresholds, and high touch-sampling / report rate toggles.
- **Dual Wi-Fi (`wlan0` + `wlan1`):** Simultaneous dual-band Wi-Fi acceleration and status monitoring.
- **Battery & Power:** Bypass Charging support, calibrated `6000 mAh` dual-cell power profile, and Game Mode CPU scheduler boost.
- **Display & Telephony:** 144Hz peak refresh rate support and Qualcomm IWLAN / VoWiFi integration.

---

## Installation

### Option 1: DSU Sideloader (Non-Destructive Dual-Boot)
1. Download the `.img.xz` release asset.
2. Open **DSU Sideloader**, select the downloaded `.img.xz`, allocate your desired userdata size, and tap **Install**.
3. Once installation completes, tap **Reboot** in the Dynamic System Updates notification.

### Option 2: Fastboot (`fastbootd`)
1. Extract the image:
   ```bash
   xz -d GSI_treble_arm64-ab-GAPPS-userdebug-20261022.img.xz
   ```
2. Reboot to userspace fastboot (`fastbootd`) and flash `system`:
   ```bash
   adb reboot fastboot
   fastboot flash system GSI_treble_arm64-ab-GAPPS-userdebug-20261022.img
   ```
3. Format userdata if switching ROM bases, then reboot:
   ```bash
   fastboot reboot
   ```
