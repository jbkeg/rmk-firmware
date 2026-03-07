# Sofle and Eyelash Sofle

This document describes Sofle-family support in the RMK firmware repository.

![Sofle layout](/docs/images/sofle_layout.svg)

## Support Snapshot

Sofle artifacts:

- `sofle_left`
- `sofle_right`
- `sofle_left_w_dongle`
- `sofle_dongle` (basic)
- `sofle_zdd_dongle`
- `sofle_prospector_dongle`

Eyelash Sofle artifacts:

- `eyelash_sofle_left`
- `eyelash_sofle_right`
- `eyelash_sofle_left_w_dongle`
- `eyelash_sofle_dongle` (basic)
- `eyelash_sofle_zdd_dongle`
- `eyelash_sofle_prospector_dongle`

Shared reset artifacts:

- `reset_nice_nano_v2`
- `reset_seeeduino_xiao_ble`

## Reference Material

- Sofle hardware: <https://github.com/josefadamcik/SofleKeyboard>
- RMK docs: <https://rmk.rs/docs/>

## Keymap

![Sofle keymap](/docs/images/sofle_keymap.svg)

## RMK Profiles

- Keyboard profiles:
  - `profiles/keyboard/sofle.toml`
  - `profiles/keyboard/eyelash_sofle.toml`
- Dongle profiles:
  - `profiles/dongle/basic/sofle.toml`
  - `profiles/dongle/basic/eyelash_sofle.toml`
  - `profiles/dongle/zdd/sofle.toml`
  - `profiles/dongle/zdd/eyelash_sofle.toml`
  - `profiles/dongle/prospector/sofle.toml`
  - `profiles/dongle/prospector/eyelash_sofle.toml`

## Build

```bash
cargo make uf2-sofle_left --release
cargo make uf2-sofle_right --release
cargo make uf2-sofle_left_w_dongle --release
cargo make uf2-sofle_dongle --release
cargo make uf2-sofle_zdd_dongle --release
cargo make uf2-sofle_prospector_dongle --release

cargo make uf2-eyelash_sofle_left --release
cargo make uf2-eyelash_sofle_right --release
cargo make uf2-eyelash_sofle_left_w_dongle --release
cargo make uf2-eyelash_sofle_dongle --release
cargo make uf2-eyelash_sofle_zdd_dongle --release
cargo make uf2-eyelash_sofle_prospector_dongle --release
```

## Status

Sofle and Eyelash Sofle are integrated in the v1 matrix for keyboard + all dongle roles.
