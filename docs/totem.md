# Totem

This document describes Totem support in the RMK firmware repository.

![TOTEM layout](/docs/images/totem_layout.svg)

## Support Snapshot

Active artifacts:

- `totem_left`
- `totem_right`
- `totem_left_w_dongle`
- `totem_dongle` (basic)
- `totem_zdd_dongle`
- `totem_prospector_dongle`

Shared reset artifacts:

- `reset_nice_nano_v2`
- `reset_seeeduino_xiao_ble`

## Reference Material

- Hardware: <https://github.com/GEIGEIGEIST/TOTEM>
- RMK docs: <https://rmk.rs/docs/>

## Hardware Overview

- 38-key column-staggered split keyboard
- Typical controller: XIAO BLE
- Supports direct split and dongle topology

## Keymap

![TOTEM keymap](/docs/images/totem_keymap.svg)

## RMK Profiles

- Keyboard profile: `profiles/keyboard/totem.toml`
- Dongle profiles:
  - `profiles/dongle/basic/totem.toml`
  - `profiles/dongle/zdd/totem.toml`
  - `profiles/dongle/prospector/totem.toml`

## Build

```bash
cargo make uf2-totem_left --release
cargo make uf2-totem_right --release
cargo make uf2-totem_left_w_dongle --release
cargo make uf2-totem_dongle --release
cargo make uf2-totem_zdd_dongle --release
cargo make uf2-totem_prospector_dongle --release
```

## Flashing

1. Flash matching keyboard artifacts for your topology.
2. For clean recovery, flash the MCU-family reset artifact first.
3. Re-pair if switching topology or dongle role.

## Status

Totem is integrated in the v1 matrix for keyboard + all dongle roles.
