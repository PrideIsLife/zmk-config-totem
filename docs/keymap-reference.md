# TOTEM Graphite+Miryoku Keymap Reference

## Base Layer (Graphite)

```
         ┌─────┬─────┬─────┬─────┬─────┐   ┌─────┬─────┬─────┬─────┬─────┐
         │  B  │  L  │  D  │  W  │  Z  │   │  '  │  F  │  O  │  U  │  J  │
         ├─────┼─────┼─────┼─────┼─────┤   ├─────┼─────┼─────┼─────┼─────┤
         │N/Ctl│R/Alt│T/Gui│S/Sft│  G  │   │  Y  │H/Sft│A/Gui│E/Alt│I/Ctl│
  ┌──────┼─────┼─────┼─────┼─────┼─────┤   ├─────┼─────┼─────┼─────┼─────┼──────┐
  │ TAB  │  Q  │  X  │  M  │  C  │  V  │   │  K  │  P  │ , ; │ . : │ ? ! │ ESC  │
  └──────┴─────┴─────┼─────┼─────┼─────┤   ├─────┼─────┼─────┼─────┴─────┴──────┘
                     │ DEL │NAV/ │1-Sft│   │ RET │SYM/ │FUN/ │
                     │     │Space│     │   │     │Bspc │ Tab │
                     └─────┴─────┴─────┘   └─────┴─────┴─────┘
```

### Home Row Mods (hold the key instead of tapping)

| Key | Tap | Hold |
|-----|-----|------|
| Left pinky (home) | N | Ctrl |
| Left ring (home) | R | Alt |
| Left middle (home) | T | Gui/Super |
| Left index (home) | S | Shift |
| Right index (home) | H | Shift |
| Right middle (home) | A | Gui/Super |
| Right ring (home) | E | Alt |
| Right pinky (home) | I | Ctrl |

These use urob's timer-less config: they won't misfire during fast typing.

### Thumb Keys

| Position | Tap | Hold |
|----------|-----|------|
| Left outer | DEL | — |
| Left middle | Space | NAV layer |
| Left inner | — | One-shot Shift |
| Right inner | Enter | — |
| Right middle | Backspace | SYM layer |
| Right outer | Tab | FUN layer |

### Mod-Morphs (shifted behavior)

| Key | Normal | With Shift |
|-----|--------|------------|
| Bottom row right 3rd | , | ; |
| Bottom row right 4th | . | : |
| Bottom row right 5th | ? | ! |

---

## NAV Layer (hold left middle thumb)

```
         ┌─────┬─────┬─────┬─────┬─────┐   ┌─────┬─────┬─────┬─────┬─────┐
         │     │     │     │     │     │   │     │Home │  ↑  │ End │PgUp │
         ├─────┼─────┼─────┼─────┼─────┤   ├─────┼─────┼─────┼─────┼─────┤
         │Ctrl │ Alt │ Gui │Shift│     │   │     │  ←  │  ↓  │  →  │PgDn │
  ┌──────┼─────┼─────┼─────┼─────┼─────┤   ├─────┼─────┼─────┼─────┼─────┼──────┐
  │      │     │     │     │     │     │   │     │     │     │     │     │      │
  └──────┴─────┴─────┼─────┼─────┼─────┤   ├─────┼─────┼─────┼─────┴─────┴──────┘
                     │     │▓▓▓▓▓│     │   │ RET │Bspc │ DEL │
                     └─────┴─────┴─────┘   └─────┴─────┴─────┘
```

Left hand has mods so you can do Ctrl+Arrow, Shift+Home, etc.

---

## NUM Layer (hold left middle thumb + right middle thumb → conditional)

Activated via the SYM layer thumb — it's a standalone layer.

```
         ┌─────┬─────┬─────┬─────┬─────┐   ┌─────┬─────┬─────┬─────┬─────┐
         │  +  │  7  │  8  │  9  │  *  │   │     │     │     │     │     │
         ├─────┼─────┼─────┼─────┼─────┤   ├─────┼─────┼─────┼─────┼─────┤
         │  0  │  4  │  5  │  6  │  =  │   │     │Shift│ Gui │ Alt │Ctrl │
  ┌──────┼─────┼─────┼─────┼─────┼─────┤   ├─────┼─────┼─────┼─────┼─────┼──────┐
  │      │  -  │  1  │  2  │  3  │  /  │   │     │     │     │     │     │      │
  └──────┴─────┴─────┼─────┼─────┼─────┤   ├─────┼─────┼─────┼─────┴─────┴──────┘
                     │  .  │Space│  ;  │   │     │▓▓▓▓▓│     │
                     └─────┴─────┴─────┘   └─────┴─────┴─────┘
```

---

## SYM Layer (hold right middle thumb)

```
         ┌─────┬─────┬─────┬─────┬─────┐   ┌─────┬─────┬─────┬─────┬─────┐
         │  `  │  &  │  *  │     │     │   │     │     │     │     │     │
         ├─────┼─────┼─────┼─────┼─────┤   ├─────┼─────┼─────┼─────┼─────┤
         │  ~  │  $  │  %  │  ^  │     │   │     │Shift│ Gui │ Alt │Ctrl │
  ┌──────┼─────┼─────┼─────┼─────┼─────┤   ├─────┼─────┼─────┼─────┼─────┼──────┐
  │      │  |  │  !  │  @  │  #  │     │   │     │     │     │     │     │      │
  └──────┴─────┴─────┼─────┼─────┼─────┤   ├─────┼─────┼─────┼─────┴─────┴──────┘
                     │  (  │  )  │  _  │   │     │▓▓▓▓▓│     │
                     └─────┴─────┴─────┘   └─────┴─────┴─────┘
```

---

## FUN Layer (hold right outer thumb)

```
         ┌─────┬─────┬─────┬─────┬─────┐   ┌─────┬─────┬─────┬─────┬─────┐
         │ F12 │ F7  │ F8  │ F9  │PrtSc│   │     │     │     │     │     │
         ├─────┼─────┼─────┼─────┼─────┤   ├─────┼─────┼─────┼─────┼─────┤
         │ F11 │ F4  │ F5  │ F6  │ScrLk│   │     │Shift│ Gui │ Alt │Ctrl │
  ┌──────┼─────┼─────┼─────┼─────┼─────┤   ├─────┼─────┼─────┼─────┼─────┼──────┐
  │      │ F10 │ F1  │ F2  │ F3  │Pause│   │     │     │     │     │     │      │
  └──────┴─────┴─────┼─────┼─────┼─────┤   ├─────┼─────┼─────┼─────┴─────┴──────┘
                     │     │Space│ Tab │   │     │     │▓▓▓▓▓│
                     └─────┴─────┴─────┘   └─────┴─────┴─────┘
```

---

## UTIL Layer (hold NAV + SYM thumbs simultaneously)

```
         ┌─────┬─────┬─────┬─────┬─────┐   ┌─────┬─────┬─────┬─────┬─────┐
         │BOOT │     │     │     │     │   │     │     │Vol+ │     │     │
         ├─────┼─────┼─────┼─────┼─────┤   ├─────┼─────┼─────┼─────┼─────┤
         │ BT0 │ BT1 │ BT2 │ BT3 │BTclr│   │     │     │Vol- │     │     │
  ┌──────┼─────┼─────┼─────┼─────┼─────┤   ├─────┼─────┼─────┼─────┼─────┼──────┐
  │      │RESET│     │     │     │O_TOG│   │     │     │     │     │     │      │
  └──────┴─────┴─────┼─────┼─────┼─────┤   ├─────┼─────┼─────┼─────┴─────┴──────┘
                     │     │     │     │   │     │Mute │     │
                     └─────┴─────┴─────┘   └─────┴─────┴─────┘
```

- **BOOT** = bootloader mode (for flashing)
- **RESET** = soft reset
- **BT0-3** = select Bluetooth profile
- **BTclr** = clear current BT profile
- **O_TOG** = toggle USB/BLE output

---

## Combos (press two keys at the same time)

### Brackets & Parens (right hand, horizontal)

```
         Top row:     [ = F+O       ] = O+U
         Home row:    ( = H+A       ) = A+E
         Bottom row:  { = P+,       } = ,+.
         Edges:       < = Y+H       > = E+I
```

### Symbols (vertical combos — press top+home or home+bottom)

```
Left hand (top + home row):        Right hand (top + home row):
  L+R = @                            '+Y = ^
  D+T = #                            F+H = +
  W+S = $                            O+A = *
  Z+G = %                            U+E = &

Left hand (home + bottom row):     Right hand (home + bottom row):
  R+X = `                            Y+K = _
  T+M = \                            H+P = -
  S+C = =                            A+, = /
  G+V = ~                            E+. = |
```

### Cut / Copy / Paste (left hand bottom row)

```
  Copy  = X+M  (positions 22+23)
  Paste = M+C  (positions 23+24)
  Cut   = X+C  (positions 22+24)
```

### Caps Word

Press **S + H** simultaneously (both index home row keys) to activate caps word.
Types in ALL CAPS until you press space, enter, or a non-alpha key.

---

## Quick Reference Card

```
Layer access:
  NAV   = hold left middle thumb (Space)
  SYM   = hold right middle thumb (Bspc)
  FUN   = hold right outer thumb (Tab)
  UTIL  = hold NAV + SYM together
  
Common needs:
  Numbers    → NAV layer, left hand
  Arrows     → NAV layer, right hand
  Symbols    → SYM layer or combos
  F-keys     → FUN layer, left hand
  Bluetooth  → UTIL layer (NAV+SYM)
  Brackets   → combos (two adjacent keys, right hand)
  Ctrl+C/V/X → combos (left bottom row) or hold N + tap key
```
