# SaqrWare GCam Configs for Galaxy Z Fold8

Google Camera (AGC) configuration files tuned for the **Samsung Galaxy Z Fold8 (SM-F971B)**, with a focus on maximum-quality HDR photos.

| | |
|---|---|
| **Device** | Galaxy Z Fold8 · SM-F971B (`h8q`) · Snapdragon SM8850 |
| **OS tested** | Android 17 / One UI 9 |
| **GCam port** | BigKaka AGC 9.6.19 V7.0 (`_samsung` build); also loads on AGC 9.2 V14 |
| **Config base** | AGC 9.2 V13 format |

---

## Config variants

All five files share the same six profiles and camera settings. They differ only in sharpening and processing style, so pick the look you like:

| File | Look |
|---|---|
| `Fold8_SaqrWare_Natural.agc` | Closest to what the scene looked like, with light sharpening. **Start here.** |
| `Fold8_SaqrWare_Soft.agc` | Softer detail and less sharpening |
| `Fold8_SaqrWare_Medium.agc` | Moderate sharpening |
| `Fold8_SaqrWare_Sharp.agc` | Strong sharpening and crisp detail |
| `Fold8_SaqrWare_Instalook.agc` | Instagram-style processed look |

## Profiles inside each config

AGC lets you switch profiles from the viewfinder (the profile button next to the shutter):

| Slot | Profile | Use it for |
|---|---|---|
| 1 | Balanced-LDR 🏞️ | Everyday shots, fast capture |
| 2 | MaxQ-LDR 🏞️ | Maximum detail in good light |
| 3 | Astro 🌃 | Night and astrophotography, on a tripod |
| 4 | Balanced-HDR 🌄 | Everyday HDR scenes |
| 5 | **MaxQ-HDR 🌄** | **Maximum HDR quality (HDR+ Enhanced).** Best for landscapes and high-contrast scenes |
| 6 | Sport 🏂 | Moving subjects, short exposures |

---

## Installation

### 1. Install the GCam app

Download **BigKaka AGC 9.6.19 V7.0, `_samsung` variant** (package `com.samsung.agc.gcam96`) from the official BigKaka release channel, then install it.

> The `_samsung` build installs alongside the stock Samsung camera and avoids crashes specific to Samsung phones. The APK is not included in this repo because of its size and because the porter distributes it.

Open the app once and grant the camera, microphone, storage and location permissions.

### 2. Copy the config files to the phone

Create this folder on the phone's internal storage and copy the `.agc` files from [`configs/`](configs/) into it:

```
/sdcard/Download/AGC.9.6/configs/
```

For AGC 9.2, use `/sdcard/Download/AGC.9.2/configs/` instead.

**Option A: file manager.** Download the files from this repo directly on the phone, then move them into the folder above with **My Files**.

**Option B: adb from a computer:**

```bash
adb shell mkdir -p /sdcard/Download/AGC.9.6/configs
adb push configs/*.agc /sdcard/Download/AGC.9.6/configs/
```

### 3. Load a config

1. Open the AGC app.
2. **Double-tap the black area** next to the shutter button. A config picker appears.
3. Choose a config, for example `Fold8_SaqrWare_Natural.agc`, and tap **Restore**.
4. The app restarts with the config applied.


### 4. Pick a profile

Tap the profile selector in the viewfinder and choose **MaxQ-HDR 🌄** (slot 5) for maximum HDR quality, or another profile for the scene.

---

## Tips

- **Hold still** for about a second after the shutter on the MaxQ profiles. They merge many frames.
- Use **Astro** only on a tripod or a stable surface.
- These configs deliberately leave out hard-coded camera IDs, so AGC auto-detects the Fold8 lenses. If a lens is missing, restart the app after restoring the config.
- To go back to defaults, clear the app's data or restore a different config.

## Known limitations

- **Ultra HDR (gain-map JPEG)** output was not observed in testing. Photos are saved as standard SDR JPEGs with HDR+ processing.
- The configs were adapted from a Galaxy S24 Ultra tuning. Colour and noise reduction are close but not calibrated per sensor for the Fold8 lenses.

---

## What was changed for the Fold8

Starting from the original S24 Ultra configs:

- Removed the S24 Ultra camera-ID and lens lists so AGC auto-detects the Fold8 cameras
- Changed the device info fields (`model`, `device`, `board`, `fingerprint`, Android version) to the Fold8
- Rebranded the config nickname to **SaqrWare**
- Kept all original processing and profile tuning

## Credits

- **JavaSaBr**: author of the original AGC config pack (Galaxy S24 Ultra, AGC 9.2 V13 v8). These configs are built directly on that tuning work.
- **BigKaka**: developer of the AGC (Advanced GCam) port.
- **Google**: original Google Camera and HDR+ pipeline.

Adapted for the Galaxy Z Fold8 by **SaqrWare**.

## Disclaimer

These are community configs for an unofficial camera port, provided as-is. Use them at your own risk.
