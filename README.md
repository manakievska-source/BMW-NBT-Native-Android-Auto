# BMW NBT Native Android Auto

Wired Android Auto for the **original BMW HU_NBT** head unit (F-series iDrive, Intel / QNX).
**Not** for NBT Evo / ID4 / ID5 / ID6 — those use a different platform.

This repository contains **installer releases only** (see *Releases*), a description and the licenses.

> **⚠️ Beta.** This is a beta version, not a final release. It works well in the test car, but it has only been
> tested on a few cars and phones so far. **Testers are welcome!** If you have an original NBT, try it and report
> what works and what does not via GitHub *Issues* (car model, NBT software version, phone model, and the diagnostic
> logs from the installer).

---

## Features (car-tested, November 2026)

| Feature | State |
|---|---|
| Wired Android Auto over the NBT's own USB port | ✅ works |
| Own iDrive entry **Multimedia → Android Auto** | ✅ works |
| iDrive controller (turn, push, tilt, BACK) controls Android Auto | ✅ works |
| **60 fps**, full-screen picture on the 1280×480 display | ✅ works |
| **Low lag** — fast response to the controller and smooth maps | ✅ works |
| **Sound without Bluetooth**, through the car's audio system | ✅ works |
| Android Auto music as a real audio source — switch between radio and Android Auto like any other source | ✅ works |
| Navigation announcements | ✅ works |
| Sound and picture come back by themselves after a short ignition off/on | ✅ works |
| Unplug / replug the phone: Android Auto starts again cleanly | ✅ works |
| **Motor Live** — iDrive page with live engine data | ⚠️ **not ready — not recommended to install yet** |
| **Car microphone** for "Hey Google" / voice commands — the Google Assistant hears you through the car's microphones | ✅ works |
| **NAV button shortcut**: short press = Android Auto from any menu, long press = original BMW navigation | ✅ works |
| Back to Android Auto after park sensors (PDC) / reverse gear | ⚠️ one push on the popup (automatic return in progress) |
| CarPlay (with a CarPlay receiver adapter on the NBT's USB port) | 🔧 in progress |

Tested phones: Samsung Galaxy A20e, S20, S26.

## Requirements

- BMW with the **original NBT** head unit.
- Root SSH access to the head unit over the ENET (OBD Ethernet) cable, laptop with Windows and Python 3.8+.
- Android phone with Android Auto, USB cable.

## Install

1. Download the newest zip from **Releases** and unpack it.
2. Connect the laptop to the car with the ENET cable, ignition on (parked).
3. Run `python nbt_aa_installer.py`, enter the head unit's IP (default `169.254.199.99`) and the root password.
   - Python 3.8 or newer is needed (<https://www.python.org/downloads/>, check *Add python.exe to PATH* during setup).
   - If a required Python package is missing, the installer says which one and how to install it — follow its
     instructions and start it again.
4. Keep **Android Auto** checked and **uncheck Motor Live** (see below), then click *Install / Update*.
5. Restart iDrive (hold the volume/power button for about 30 s).
6. Open **Multimedia → Android Auto** and plug in the phone.

Nothing outside the package folders is changed: no firmware flashing, no coding, no system files.

## Update and uninstall

- **Update:** run the installer of the new release the same way. Your settings are kept.
- **Uninstall:** run the installer, check the parts to remove and click *Uninstall*, then restart iDrive. The menu
  entries disappear and the head unit is back to stock.

## Motor Live (experimental)

Motor Live is an optional iDrive page (**Multimedia → Motor Live**) meant to show live engine data such as boost,
rail pressure, exhaust gas temperatures, DPF soot load and oil/coolant temperatures. **It is not ready yet:** the page
appears in the menu, but the engine values are not read yet, and it has only been tried on one car with a B47 diesel.
**It is recommended not to install it for now** — leave the *Motor Live* box unchecked in the installer. It is
installed and removed independently of Android Auto.

## Troubleshooting

- **Problem report:** in the installer click *Save diagnostic logs* and attach the zip to a GitHub issue.

## Known limitations

- After the park sensors (PDC) or reverse gear, Android Auto does not come back by itself yet: a popup appears, one
  push on the controller brings Android Auto back. *A fix is actively being worked on.*
- A short NAV press shows the original navigation for a moment before Android Auto opens. *A fix is actively being
  worked on.*
- The picture comes from the phone at 800×480 and is scaled to the 1280×480 screen.

## Disclaimer

Use at your own risk. Install and test while parked. This is an independent hobby project, not affiliated with or
endorsed by BMW AG or Google. BMW, iDrive, Android and Android Auto are trademarks of their respective owners.

## Credits and licenses

- The Android Auto protocol core is based on **NBT-AAD** by nanaisu
  (<https://github.com/Sq00ky/Supra-iDrive6-Android-Auto>), PolyForm Noncommercial 1.0.0.
- Further components and their licenses: see [NOTICE.md](NOTICE.md) and [licenses/](licenses/).
- Original work in this project: © manakievska-source — see [LICENSE.md](LICENSE.md).

Noncommercial use only.
