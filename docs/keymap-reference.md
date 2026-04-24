# TOTEM Graphite+Miryoku Keymap Reference

Miryoku-style layout with Graphite alphas and urob's timer-less home row mods.

## Base Layer (Graphite)

```
         ┌─────┬─────┬─────┬─────┬─────┐   ┌─────┬─────┬─────┬─────┬─────┐
         │  B  │  L  │  D  │  W  │  Z  │   │  '  │  F  │  O  │  U  │  J  │
         ├─────┼─────┼─────┼─────┼─────┤   ├─────┼─────┼─────┼─────┼─────┤
         │N/Ctl│R/Alt│T/Gui│S/Sft│  G  │   │  Y  │H/Sft│A/Gui│E/Alt│I/Ctl│
  ┌──────┼─────┼─────┼─────┼─────┼─────┤   ├─────┼─────┼─────┼─────┼─────┼──────┐
  │ TAB  │  Q  │  X  │  M  │  C  │  V  │   │  K  │  P  │ , ; │ . : │ ? ! │ ESC  │
  └──────┴─────┴─────┼─────┼─────┼─────┤   ├─────┼─────┼─────┼─────┴─────┴──────┘
                     │ ESC │NAV/ │SYM/ │   │NUM/ │FUN/ │ DEL │
                     │     │Space│ Tab │   │ Ret │Bspc │     │
                     └─────┴─────┴─────┘   └─────┴─────┴─────┘
```

### Home Row Mods (hold = modifier, tap = letter)

| Key | Hold |
|-----|------|
| N / I | Ctrl |
| R / E | Alt |
| T / A | Gui (Super) |
| S / H | Shift |

Uses urob's timer-less config — won't misfire during fast typing.

### Thumb Keys

| Position | Tap | Hold |
|----------|-----|------|
| Left outer | Esc | — |
| Left middle | Space | **NAV** layer |
| Left inner | Tab | **SYM** layer |
| Right inner | Enter | **NUM** layer |
| Right middle | Backspace | **FUN** layer |
| Right outer | Delete | — |

### Mod-Morphs

| Key | Normal | Shifted |
|-----|--------|---------|
| Bottom row 3rd from right | , | ; |
| Bottom row 2nd from right | . | : |
| Bottom row rightmost | ? | ! |

---

## NAV Layer (hold left middle thumb — Space)

Right hand: navigation. Left hand: modifiers for Ctrl/Shift+arrows etc.

```
         ┌─────┬─────┬─────┬─────┬─────┐   ┌─────┬─────┬─────┬─────┬─────┐
         │     │     │     │     │     │   │     │Home │  ↑  │ End │PgUp │
         ├─────┼─────┼─────┼─────┼─────┤   ├─────┼─────┼─────┼─────┼─────┤
         │Ctrl │ Alt │ Gui │Shift│     │   │     │  ←  │  ↓  │  →  │PgDn │
  ┌──────┼─────┼─────┼─────┼─────┼─────┤   ├─────┼─────┼─────┼─────┼─────┼──────┐
  │      │     │     │     │     │     │   │     │     │     │     │     │      │
  └──────┴─────┴─────┼─────┼─────┼─────┤   ├─────┼─────┼─────┼─────┴─────┴──────┘
                     │ Esc │▓▓▓▓▓│ Tab │   │ Ret │Bspc │ Del │
                     └─────┴─────┴─────┘   └─────┴─────┴─────┘
```

---

## NUM Layer (hold right inner thumb — Enter)

Left hand: numpad layout. Right hand: modifiers.

```
         ┌─────┬─────┬─────┬─────┬─────┐   ┌─────┬─────┬─────┬─────┬─────┐
         │  +  │  7  │  8  │  9  │  *  │   │     │     │     │     │     │
         ├─────┼─────┼─────┼─────┼─────┤   ├─────┼─────┼─────┼─────┼─────┤
         │  0  │  4  │  5  │  6  │  =  │   │     │Shift│ Gui │ Alt │Ctrl │
  ┌──────┼─────┼─────┼─────┼─────┼─────┤   ├─────┼─────┼─────┼─────┼─────┼──────┐
  │      │  -  │  1  │  2  │  3  │  /  │   │     │     │     │     │     │      │
  └──────┴─────┴─────┼─────┼─────┼─────┤   ├─────┼─────┼─────┼─────┴─────┴──────┘
                     │  .  │Space│  ;  │   │▓▓▓▓▓│Bspc │ Del │
                     └─────┴─────┴─────┘   └─────┴─────┴─────┘
```

---

## SYM Layer (hold left inner thumb — Tab)

Left hand: symbols. Right hand: modifiers.

```
         ┌─────┬─────┬─────┬─────┬─────┐   ┌─────┬─────┬─────┬─────┬─────┐
         │  `  │  &  │  *  │     │     │   │     │     │     │     │     │
         ├─────┼─────┼─────┼─────┼─────┤   ├─────┼─────┼─────┼─────┼─────┤
         │  ~  │  $  │  %  │  ^  │     │   │     │Shift│ Gui │ Alt │Ctrl │
  ┌──────┼─────┼─────┼─────┼─────┼─────┤   ├─────┼─────┼─────┼─────┼─────┼──────┐
  │      │  |  │  !  │  @  │  #  │     │   │     │     │     │     │     │      │
  └──────┴─────┴─────┼─────┼─────┼─────┤   ├─────┼─────┼─────┼─────┴─────┴──────┘
                     │  (  │  )  │▓▓▓▓▓│   │ Ret │Bspc │ Del │
                     └─────┴─────┴─────┘   └─────┴─────┴─────┘
```

---

## FUN Layer (hold right middle thumb — Backspace)

Left hand: F-keys. Right hand: modifiers.

```
         ┌─────┬─────┬─────┬─────┬─────┐   ┌─────┬─────┬─────┬─────┬─────┐
         │ F12 │ F7  │ F8  │ F9  │PrtSc│   │     │     │     │     │     │
         ├─────┼─────┼─────┼─────┼─────┤   ├─────┼─────┼─────┼─────┼─────┤
         │ F11 │ F4  │ F5  │ F6  │ScrLk│   │     │Shift│ Gui │ Alt │Ctrl │
  ┌──────┼─────┼─────┼─────┼─────┼─────┤   ├─────┼─────┼─────┼─────┼─────┼──────┐
  │      │ F10 │ F1  │ F2  │ F3  │Pause│   │     │     │     │     │     │      │
  └──────┴─────┴─────┼─────┼─────┼─────┤   ├─────┼─────┼─────┼─────┴─────┴──────┘
                     │ App │Space│ Tab │   │     │     │▓▓▓▓▓│
                     └─────┴─────┴─────┘   └─────┴─────┴─────┘
```

---

## UTIL Layer (hold NAV + NUM simultaneously)

```
         ┌─────┬─────┬─────┬─────┬─────┐   ┌─────┬─────┬─────┬─────┬─────┐
         │BOOT │     │     │     │     │   │     │     │Vol+ │     │     │
         ├─────┼─────┼─────┼─────┼─────┤   ├─────┼─────┼─────┼─────┼─────┤
         │ BT0 │ BT1 │ BT2 │ BT3 │BTclr│   │     │     │Vol- │     │     │
  ┌──────┼─────┼─────┼─────┼─────┼─────┤   ├─────┼─────┼─────┼─────┼─────┼──────┐
  │      │RESET│     │     │     │O_TOG│   │     │     │     │     │     │      │
  └──────┴─────┴─────┼─────┼─────┼─────┤   ├─────┼─────┼─────┼─────┴─────┴──────┘
                     │     │▓▓▓▓▓│     │   │▓▓▓▓▓│Mute │     │
                     └─────┴─────┴─────┘   └─────┴─────┴─────┘
```

- **BOOT** = bootloader (for flashing)
- **RESET** = soft reset
- **BT0-3** = select Bluetooth profile
- **BTclr** = clear current BT profile
- **O_TOG** = toggle USB/BLE output

---

## Combos (press two keys simultaneously)

### Brackets & Parens (right hand, horizontal)

```
Top row:     [ = F+O       ] = O+U
Home row:    ( = H+A       ) = A+E
Bottom row:  { = P+,       } = ,+.
Edges:       < = Y+H       > = E+I
```

### Symbols (vertical — press top+home or home+bottom)

```
Left (top+home):    L+R=@   D+T=#   W+S=$   Z+G=%
Left (home+bottom): R+X=`   T+M=\   S+C==   G+V=~

Right (top+home):   '+Y=^   F+H=+   O+A=*   U+E=&
Right (home+bottom):Y+K=_   H+P=-   A+,=/   E+.=|
```

### Cut / Copy / Paste (left bottom row)

```
Copy  = X+M    Paste = M+C    Cut = X+C
```

### Caps Word

Press **S + H** (both index home row keys) simultaneously.

---

## Quick Reference

```
Layer access:
  NAV   = hold left middle thumb  (Space)
  SYM   = hold left inner thumb   (Tab)
  NUM   = hold right inner thumb  (Enter)
  FUN   = hold right middle thumb (Backspace)
  UTIL  = hold NAV + NUM together

Common needs:
  Numbers    → NUM layer, left hand (numpad layout)
  Arrows     → NAV layer, right hand
  Symbols    → SYM layer or combos
  F-keys     → FUN layer, left hand
  Bluetooth  → UTIL layer (NAV+NUM)
  Brackets   → combos (two adjacent keys, right hand)
  Shift+key  → use opposite hand's Shift (H or S)
```
