# Corne and Eyelash Corne

This document describes Corne-family support in the RMK firmware repository.

![Corne 3x6 layout](/docs/images/corne_3x6_layout.svg)

## Support Snapshot

Corne artifacts:

- `corne_left`
- `corne_right`
- `corne_left_w_dongle`
- `corne_dongle` (basic)
- `corne_zdd_dongle`
- `corne_prospector_dongle`

Eyelash Corne artifacts:

- `eyelash_corne_left`
- `eyelash_corne_right`
- `eyelash_corne_left_w_dongle`
- `eyelash_corne_dongle` (basic)
- `eyelash_corne_zdd_dongle`
- `eyelash_corne_prospector_dongle`

Shared reset artifacts:

- `reset_nice_nano_v2`
- `reset_seeeduino_xiao_ble`

## Reference Material

- Corne hardware: <https://github.com/foostan/crkbd>
- RMK docs: <https://rmk.rs/docs/>

## Keymap

![Corne keymap](/docs/images/corne_keymap.svg)

## RMK Profiles

- Keyboard profiles:
  - `profiles/keyboard/corne.toml`
  - `profiles/keyboard/eyelash_corne.toml`
- Dongle profiles:
  - `profiles/dongle/basic/corne.toml`
  - `profiles/dongle/basic/eyelash_corne.toml`
  - `profiles/dongle/zdd/corne.toml`
  - `profiles/dongle/zdd/eyelash_corne.toml`
  - `profiles/dongle/prospector/corne.toml`
  - `profiles/dongle/prospector/eyelash_corne.toml`

## Build

```bash
cargo make uf2-corne_left --release
cargo make uf2-corne_right --release
cargo make uf2-corne_left_w_dongle --release
cargo make uf2-corne_dongle --release
cargo make uf2-corne_zdd_dongle --release
cargo make uf2-corne_prospector_dongle --release

cargo make uf2-eyelash_corne_left --release
cargo make uf2-eyelash_corne_right --release
cargo make uf2-eyelash_corne_left_w_dongle --release
cargo make uf2-eyelash_corne_dongle --release
cargo make uf2-eyelash_corne_zdd_dongle --release
cargo make uf2-eyelash_corne_prospector_dongle --release
```

## Status

Corne and Eyelash Corne are integrated in the v1 matrix for keyboard + all dongle roles.
