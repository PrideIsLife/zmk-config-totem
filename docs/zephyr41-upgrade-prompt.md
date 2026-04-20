# Task: Upgrade TOTEM keyboard firmware from ZMK v0.3 to ZMK main (Zephyr 4.1)

## Context

I have a GEIST TOTEM 38-key split keyboard with Seeed XIAO nRF52840 BLE controllers. It's currently working on ZMK v0.3. I want to upgrade to ZMK main for Zephyr 4.1 support and ZMK Studio (live keymap editing).

## Current Working State

- Both halves are flashed and working with ZMK v0.3
- Fork: https://github.com/PrideIsLife/zmk-config-totem (master branch = working v0.3)
- Local repo: `~/zmk-config-totem/`
- `gh` CLI is authenticated as PrideIsLife
- Firmware files: `~/totem-firmware/firmware-v0.3/` (known good, can reflash if upgrade fails)
- Full documentation: `~/totem-reflash-guide.md`

## What Needs to Change for ZMK Main

1. `config/west.yml`: change `revision: v0.3` → `revision: main`
2. `.github/workflows/build.yml`: change `@v0.3` → `@main`
3. `build.yaml`: change board `seeeduino_xiao_ble` → `xiao_ble//zmk` (Zephyr 4.1 HWMv2 board rename)
4. Shield files (`config/boards/shields/totem/`) should NOT need changes — shields don't require HWMv2 updates per the ZMK blog post

## Important Notes

- Create a `zephyr-4.1` branch from master — do NOT modify master (it's the known working config)
- The shield config uses `col2row` diode direction — this is correct, do not change it
- After flashing, always test with `sudo systemctl stop keyd && sudo evtest /dev/input/eventXX` — keyd grabs the device and hides events
- To enter bootloader: double-tap the small reset button on the XIAO, a 32MB USB drive appears, mount it and copy the .uf2 file
- The bootloader drive device name increments each time (`sda`, `sdb`, etc.) — use `lsblk -rno NAME,SIZE | grep "32"` to find it
- Flash left half first as test. If keys work, flash right half too
- Default keymap is Colemak-DH, not QWERTY
- Right half communicates with left via BLE — only left shows as USB HID
- Both halves need USB power (no batteries installed)
- USB logging (`CONFIG_ZMK_USB_LOGGING=y`) does NOT work on v0.3 with XIAO BLE, untested on main
- An earlier Zephyr 4.1 build exists at `~/totem-firmware/firmware-zephyr4.1-broken/` — it was built correctly but never tested with working switches. Could try flashing that first before rebuilding.

## Optional: Add ZMK Studio Support

If the base upgrade works, add to `build.yaml` for the left half only:
```yaml
- board: xiao_ble//zmk
  shield: totem_left
  snippet: studio-rpc-usb-uart
  cmake-args: -DCONFIG_ZMK_STUDIO=y
```

## References

- ZMK Zephyr 4.1 migration blog: https://zmk.dev/blog/2025/12/09/zephyr-4-1
- Upstream TOTEM PR for 4.1: https://github.com/GEIGEIGEIST/zmk-config-totem/pull/85
- FubukiPL's working fork on main: https://github.com/FubukiPL/zmk-config-totem
