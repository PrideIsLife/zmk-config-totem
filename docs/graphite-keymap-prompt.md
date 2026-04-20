# Task: Implement Graphite + Miryoku-style keymap for TOTEM keyboard

## Context

I have a GEIST TOTEM 38-key split keyboard running ZMK v0.3 with ZMK Studio support.
- Fork: https://github.com/PrideIsLife/zmk-config-totem (master branch)
- Local repo: `~/zmk-config-totem/`
- `gh` CLI authenticated as PrideIsLife
- Working firmware in `~/totem-firmware/firmware-v03-studio/` (fallback)
- Full docs: `~/totem-reflash-guide.md`

## What I Want

A full Miryoku-inspired keymap using:
- **Graphite** alpha layout as the base layer
- **urob's timer-less home row mods** (require-prior-idle-ms + positional hold-trigger)
- **Miryoku layer structure**: Nav, Num, Sym, Fun, Util/Media
- **Symbol combos** (vertical/horizontal key combos for symbols like bsag's approach)
- **Caps word** via combo (both index home row keys)
- **Mod-morphs** for comma→semicolon, dot→colon when shifted
- **Outer pinky keys** used for useful shortcuts (tab nav, back/forward, or parens)

## Reference Configs

1. **bsag/zmk-config-bsag** — https://github.com/bsag/zmk-config-bsag
   - TOTEM-specific Miryoku+urob keymap with Colemak-DH
   - Uses `zmk-nodefree-config` submodule for clean combo/behavior macros
   - Has combos.dtsi, custom HRMs, mod-morphs
   - Study their full approach and adapt for Graphite alphas

2. **urob/zmk-config** — https://github.com/urob/zmk-config
   - The gold standard for timer-less home row mods
   - `zmk-nodefree-config` is his project

3. **Graphite layout** — https://github.com/rdavison/graphite-layout
   ```
    B  L  D  W  Z     '  F  O  U  J
    N  R  T  S  G     Y  H  A  E  I
    Q  X  M  C  V     K  P  .  -  /
   ```

## Implementation Approach

- Add `zmk-nodefree-config` as a ZMK module (via west.yml, not git submodule) — see urob's config for how
- Create `config/combos.dtsi` adapted from bsag's
- Rewrite `config/totem.keymap` with Graphite base + Miryoku layers + urob HRMs
- Keep the existing shield files (`config/boards/shields/totem/`) unchanged
- Keep `build.yaml` unchanged (v0.3, Studio enabled)
- Test build via GitHub Actions before flashing

## Important Notes

- ZMK version is **v0.3** (pinned in west.yml) — do NOT upgrade to main
- Board is `seeeduino_xiao_ble` (v0.3 naming)
- ZMK Studio is enabled on left half — keep `snippet: studio-rpc-usb-uart` and `cmake-args`
- Studio won't be able to edit custom behaviors (HRMs, mod-morphs, combos) but will show the layout — that's fine
- The `&studio_unlock` key from the ADJ layer keymap can be removed since we use `-DCONFIG_ZMK_STUDIO_LOCKING=n`
- Flash procedure: double-tap reset on XIAO → 32MB drive appears → mount → copy .uf2
- `sudo systemctl stop keyd` before testing with evtest
- Both halves need USB power (no batteries)
- Fallback firmware: `~/totem-firmware/firmware-v03-studio/`

## Graphite Home Row Mod Mapping

Left hand home row: N(LCTRL) R(LALT) T(LGUI) S(LSHFT)
Right hand home row: H(RSHFT) A(RGUI) E(RALT) I(RCTRL)

## Deliverables

1. Updated `config/west.yml` with zmk-nodefree-config module
2. New `config/combos.dtsi`
3. Rewritten `config/totem.keymap`
4. Build and flash both halves
5. Verify keys work on both halves
