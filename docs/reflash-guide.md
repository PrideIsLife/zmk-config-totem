# TOTEM Keyboard Reflash Guide

## Status

**WORKING** — Both halves on ZMK main (Zephyr 4.1) with ZMK Studio support. Updated 2026-04-20.

## Hardware

- **Keyboard:** GEIST TOTEM 38-key split (BLE wireless version)
- **Controllers:** Seeed XIAO nRF52840 (BLE) on both halves
- **Switches:** Kailh Choc low profile (hotswap sockets)
- **Batteries:** NOT installed (not soldered yet)
- **Case:** Fully enclosed MJF 3D printed
- **Purchased from:** KeebSupply (with assembly service)

## Current Firmware

- **ZMK version:** main (Zephyr 4.1)
- **Board:** `xiao_ble//zmk`
- **Shield:** `totem_left` / `totem_right`
- **Diode direction:** `col2row` (official default)
- **Default keymap:** Colemak-DH (NOT QWERTY)
- **ZMK Studio:** Enabled on left half (central)
- **Fork:** https://github.com/PrideIsLife/zmk-config-totem (master branch)

## ZMK Studio

- Access at https://zmk.studio/ over USB (connect left half)
- Or use the native app: https://zmk.studio/download
- To unlock: press `&studio_unlock` on ADJ layer (left hand, row 0, col 3)
- On Linux you may need to be in the `uucp` or `dialout` group for USB serial access

## Firmware Files Location

```
~/totem-firmware/
├── firmware-zephyr4.1-studio/      ← CURRENT WORKING firmware (Zephyr 4.1 + Studio)
│   ├── totem_left-xiao_ble__zmk-zmk.uf2
│   ├── totem_right-xiao_ble__zmk-zmk.uf2
│   └── settings_reset-xiao_ble__zmk-zmk.uf2
├── firmware-v0.3/                  ← FALLBACK firmware (ZMK v0.3, no Studio)
│   ├── totem_left-seeeduino_xiao_ble-zmk.uf2
│   ├── totem_right-seeeduino_xiao_ble-zmk.uf2
│   └── settings_reset-seeeduino_xiao_ble-zmk.uf2
├── firmware-zephyr4.1-broken/      ← old Zephyr 4.1 build (no Studio, untested)
├── firmware-row2col/               ← debug builds (can delete)
├── firmware-row2col-fixed/         ← debug builds (can delete)
├── firmware-row2col-nopull/        ← debug builds (can delete)
└── firmware-col2row-original/      ← duplicate of v0.3 (can delete)
```

## Config Repo

```
~/zmk-config-totem/   (branch: master)
├── .github/workflows/build.yml     ← @main
├── build.yaml                      ← xiao_ble//zmk + studio-rpc-usb-uart on left
├── config/
│   ├── west.yml                    ← revision: main
│   ├── totem.conf                  ← USB logging off, passkey entry off
│   ├── totem.keymap                ← Colemak-DH + studio_unlock on ADJ layer
│   └── boards/shields/totem/
│       ├── totem.dtsi              ← col2row, physical-layout chosen
│       ├── totem-layouts.dtsi      ← physical layout with keys (for ZMK Studio)
│       ├── totem_left.overlay
│       └── totem_right.overlay
```

## Root Cause of Initial Failure

**Choc switches were inserted upside down in the hotswap sockets.** They fit physically but pins don't make electrical contact. Fix: pull switches and reinsert rotated 180°.

## Flash Procedure

### Enter Bootloader
Double-tap the small reset button on the XIAO. A 32MB USB drive appears.

### Flash Order (clean install)
1. `settings_reset` on left → double-tap → mount → copy UF2
2. `totem_left` on left → double-tap → mount → copy UF2
3. `settings_reset` on right → double-tap → mount → copy UF2
4. `totem_right` on right → double-tap → mount → copy UF2

### Flash Commands
```bash
DEV=$(lsblk -rno NAME,SIZE | grep "32" | head -1 | awk '{print $1}')
sudo mount /dev/$DEV /mnt
sudo cp firmware.uf2 /mnt/
```

### Verify
```bash
sudo systemctl stop keyd
sudo evtest   # pick the TOTEM device, press keys
sudo systemctl start keyd   # re-enable after testing
```

## Important Notes

- **keyd grabs the device** — stop it before evtest
- **Right half doesn't show as USB HID** — communicates with left via BLE
- **Both halves need USB power** until batteries are soldered
- **Bootloader drive name increments** each flash cycle — always use `lsblk | grep 32`
- **Fallback:** if Zephyr 4.1 breaks, flash v0.3 files from `firmware-v0.3/`

## What Was Needed for ZMK Studio

The TOTEM shield originally used `chosen { zmk,matrix-transform }` which is incompatible with Studio. We:
1. Created `totem-layouts.dtsi` with a `physical_layouts` node containing `keys` property (38 key positions derived from QMK's keyboard.json)
2. Changed `chosen` to use `zmk,physical-layout` instead of `zmk,matrix-transform`
3. Added `&studio_unlock` to the ADJ layer keymap
4. Added `snippet: studio-rpc-usb-uart` and `cmake-args: -DCONFIG_ZMK_STUDIO=y` to left half in build.yaml

## References

- ZMK Studio: https://zmk.studio/
- ZMK docs: https://zmk.dev/docs
- ZMK physical layouts: https://zmk.dev/docs/development/hardware-integration/physical-layouts
- TOTEM hardware: https://github.com/GEIGEIGEIST/TOTEM
- Our fork: https://github.com/PrideIsLife/zmk-config-totem
- XIAO nRF52840 wiki: https://wiki.seeedstudio.com/XIAO_BLE/
