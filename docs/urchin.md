# Urchin

This document describes Urchin support in the RMK firmware repository.

![Urchin Layout](/docs/images/urchin_layout.svg)

## Support Snapshot

Active artifacts:

- `urchin_left`
- `urchin_right`
- `urchin_left_w_dongle`
- `urchin_dongle` (basic)
- `urchin_zdd_dongle`
- `urchin_prospector_dongle`

Shared reset artifacts:

- `reset_nice_nano_v2`
- `reset_seeeduino_xiao_ble`

## Reference Material

- Hardware: <https://github.com/duckyb/urchin>
- RMK docs: <https://rmk.rs/docs/>

## Hardware Overview

- 34-key split ergonomic keyboard
- nice!nano-family controller usage
- Supports direct split and dongle topology

## Keymap

![Urchin Keymap](/docs/images/urchin_keymap.svg)

## RMK Profiles

- Keyboard profile: `profiles/keyboard/urchin.toml`
- Dongle profiles:
  - `profiles/dongle/basic/urchin.toml`
  - `profiles/dongle/zdd/urchin.toml`
  - `profiles/dongle/prospector/urchin.toml`

## Build

```bash
cargo make uf2-urchin_left --release
cargo make uf2-urchin_right --release
cargo make uf2-urchin_left_w_dongle --release
cargo make uf2-urchin_dongle --release
cargo make uf2-urchin_zdd_dongle --release
cargo make uf2-urchin_prospector_dongle --release
```

## Flashing

1. Flash keyboard halves for selected topology.
2. Flash dongle artifact if using dongle mode.
3. Use shared reset artifacts when stale bonds/settings remain.

## Current Note

Right-side row wiring in `profiles/keyboard/urchin.toml` is compile-safe and marked for final hardware verification during full regression.
