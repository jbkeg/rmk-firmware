# Delta Omega

This document describes Delta Omega support in the RMK firmware repository.

![Delta Omega layout](/docs/images/delta_omega_layout.svg)

## Support Snapshot

Active artifacts:

- `delta_omega_left`
- `delta_omega_right`
- `delta_omega_left_w_dongle`
- `delta_omega_dongle` (basic)
- `delta_omega_zdd_dongle`
- `delta_omega_prospector_dongle`

Shared reset artifacts:

- `reset_nice_nano_v2`
- `reset_seeeduino_xiao_ble`

## Reference Material

- Hardware: <https://github.com/unspecworks/delta-omega>
- RMK docs: <https://rmk.rs/docs/>

## Hardware Overview

- 34-key split keyboard
- Ultra-low-profile layout
- Supports direct split and dongle topology

## Keymap

![Delta Omega keymap](/docs/images/delta_omega_keymap.svg)

## RMK Profiles

- Keyboard profile: `profiles/keyboard/delta_omega.toml`
- Dongle profiles:
  - `profiles/dongle/basic/delta_omega.toml`
  - `profiles/dongle/zdd/delta_omega.toml`
  - `profiles/dongle/prospector/delta_omega.toml`

## Build

```bash
cargo make uf2-delta_omega_left --release
cargo make uf2-delta_omega_right --release
cargo make uf2-delta_omega_left_w_dongle --release
cargo make uf2-delta_omega_dongle --release
cargo make uf2-delta_omega_zdd_dongle --release
cargo make uf2-delta_omega_prospector_dongle --release
```

## Status

Delta Omega is integrated in the v1 matrix for keyboard + all dongle roles.
