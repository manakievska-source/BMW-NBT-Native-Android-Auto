# BMW NBT Native Android Auto

Wired Android Auto for the **original BMW HU_NBT** head unit (Intel Atom / QNX 6.5, F-series iDrive).
**Not** for NBT Evo / ID4 / ID5 / ID6 — those use a different platform.

This repository contains **installer releases only** (see *Releases*), a description and the licenses.

---

## What works (car-tested, November 2026)

| Feature | State |
|---|---|
| Wired Android Auto over the NBT's USB port | ✅ works |
| iDrive entry **Multimedia → Android Auto**, iDrive controller (turn, push, tilt, BACK) controls Android Auto | ✅ works |
| **Picture straight to the NVIDIA display layer** (own decoder, no Cinemo, no 800×480 capture), full screen 1280×480 | ✅ works |
| **Low lag**: H.264 decoded on the head unit's CPU in ~14 ms per picture, 60 fps requested from the phone | ✅ works |
| **Sound without Bluetooth**, over the car's audio system | ✅ works |
| Android Auto music as a real iDrive entertainment source (radio ⇄ Android Auto switching) | ✅ works (option) |
| Sound returns by itself after a short ignition off/on | ✅ works |
| Unplug / replug the phone: Android Auto restarts cleanly | ✅ works |
| **Motor Live**: iDrive page with live engine data (B47 diesel) | 🧪 page works, engine values in progress |
| Car microphone for the Google Assistant / voice commands | ❌ not yet (under investigation) |
| Native wired CarPlay | ❌ not possible with this head unit's Apple chip (iAP1 only) |

Tested phones: Samsung Galaxy A20e, S20, S26.

## Requirements

- BMW with the **original NBT** head unit (QNX 6.5, x86).
- Root SSH access to the head unit over the ENET (OBD Ethernet) cable, laptop with Windows and Python 3.8+.
- Android phone with Android Auto, USB cable.

## Install

1. Download the newest zip from **Releases** and unpack it.
2. Connect the laptop to the car with the ENET cable, ignition on (parked).
3. Run `python nbt_aa_installer.py`, enter the head unit's IP (default `169.254.199.99`) and the root password.
4. Choose what to install — **Android Auto** and/or **Motor Live** — and click *Install / Update*.
5. Restart iDrive (hold the volume/power button ~30 s). Then **Multimedia → Android Auto** and plug in the phone.

*Uninstall* removes only the checked parts. Nothing outside the package folders is changed: no firmware flashing,
no coding, no system files.

## Known limitations

- Sometimes iDrive does not switch into the Android Auto view and shows the Android Auto entry page instead:
  press **BACK** and open Android Auto again.
- The phone's own Google Assistant works, but not with the car microphone yet.
- Picture resolution is the phone's 800×480, scaled by the GPU to the 1280×480 screen.

## Disclaimer

Use at your own risk. Test parked. This is an independent hobby project, not affiliated with or endorsed by BMW AG
or Google. BMW, iDrive, Android and Android Auto are trademarks of their respective owners.

## Credits and licenses

- The Android Auto protocol core is based on **NBT-AAD** by nanaisu
  (<https://github.com/Sq00ky/Supra-iDrive6-Android-Auto>), PolyForm Noncommercial 1.0.0.
- Further components and their licenses: see [NOTICE.md](NOTICE.md) and [licenses/](licenses/).
- Original work in this project (GPU video path, decoder integration, audio routing and keeper, Motor Live, fixes):
  © manakievska-source — see [LICENSE.md](LICENSE.md).

Noncommercial use only.
