# Cornix

This document describes Cornix support in the RMK firmware repository.

![Cornix layout](/docs/images/cornix_layout.svg)

## Support Snapshot

Active artifacts:

- `cornix_left`
- `cornix_right`
- `cornix_left_w_dongle`
- `cornix_dongle` (basic)
- `cornix_zdd_dongle`
- `cornix_prospector_dongle`

Shared reset artifacts:

- `reset_nice_nano_v2`
- `reset_seeeduino_xiao_ble`

## Reference Material

- Hardware/project: <https://cornixhub.com/>
- RMK docs: <https://rmk.rs/docs/>

## Hardware Overview

- 48-key split keyboard family
- Supports direct split and dongle topology

## Keymap

![Cornix keymap](/docs/images/cornix_keymap.svg)

## RMK Profiles

- Keyboard profile: `profiles/keyboard/cornix.toml`
- Dongle profiles:
  - `profiles/dongle/basic/cornix.toml`
  - `profiles/dongle/zdd/cornix.toml`
  - `profiles/dongle/prospector/cornix.toml`

## Build

```bash
cargo make uf2-cornix_left --release
cargo make uf2-cornix_right --release
cargo make uf2-cornix_left_w_dongle --release
cargo make uf2-cornix_dongle --release
cargo make uf2-cornix_zdd_dongle --release
cargo make uf2-cornix_prospector_dongle --release
```

## Flashing and Recovery

1. Flash runtime artifacts for chosen topology.
2. If stale pairing/settings remain, flash matching shared reset artifact.
3. Reflash runtime artifacts and re-pair.

## Current Note

Right-side row wiring in `profiles/keyboard/cornix.toml` is compile-safe and marked for final hardware verification during full regression.
