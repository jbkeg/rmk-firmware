# Jon's RMK Firmware

- [English](/README.md)
- [한국어](/README_KO.md)

This repository migrates Jon's keyboard stack from ZMK to RMK with one integrated multi-target firmware project.

## V1 Scope

- Keyboard: split targets for all supported families
- Continuum: shared canonical layer/behavior core
- Dongle: `basic`, `zdd`, and `prospector` roles
- Scanner: `prospector_scanner` (non-touch observer mode)

Keyboard families:

- `totem`
- `urchin`
- `corne`
- `eyelash_corne`
- `sofle`
- `eyelash_sofle`
- `delta_omega`
- `cornix`

## Repository Layout

```text
rmk-firmware/
├── src/                         # role entry bins (central/peripheral/dongles/scanner/reset)
├── profiles/                    # per-family and per-role RMK profile TOMLs
│   ├── keyboard/
│   ├── dongle/{basic,zdd,prospector}/
│   ├── scanner/
│   └── reset/
├── continuum/                   # canonical layers + per-family matrix maps + generated layouts
│   ├── core/
│   ├── matrix/
│   └── generated/
├── tools/generate_continuum_layers/         # Rust Continuum generator tool
├── Makefile.toml                # build matrix and artifact tasks
├── docs/
└── ZMK to RMK V1.md             # v1 plan and milestone status
```

## Build

Prerequisites:

1. Rust toolchain (see `rust-toolchain.toml`)
2. `cargo-make`

```bash
cargo install --force cargo-make
```

Useful commands:

```bash
# list all tasks
cargo make --list-all-steps

# build one target
cargo make build-totem_left --release

# build and emit uf2 for one target
cargo make uf2-totem_left --release

# build full matrix (all artifacts)
cargo make build-matrix --release

# emit uf2 for full matrix
cargo make uf2 --release
```

## Continuum Workflow

Continuum is RMK-native in this repo.

1. Edit canonical behavior/layer definitions in `continuum/core/layers.toml`
2. Edit matrix mapping in `continuum/matrix/<family>.toml`
3. Regenerate family payloads:

```bash
cargo run --manifest-path tools/generate_continuum_layers/Cargo.toml --target host-tuple --release
```

The generator updates `continuum/generated/*.toml` and patches `[layout]` in `profiles/keyboard/*.toml`.

## Artifacts and Flashing

- Artifact names are compatibility-locked with prior naming (`*_left`, `*_right`, `*_dongle`, `*_zdd_dongle`, `*_prospector_dongle`, `prospector_scanner`, reset artifacts).
- Generated `.hex`/`.uf2` files are written to repo root.
- Flash by entering bootloader mode and copying the matching `.uf2` file.

Reset artifacts:

- `reset_nice_nano_v2`
- `reset_seeeduino_xiao_ble`

## Docs Index

- [Road to V1](./ZMK%20to%20RMK%20V1.md)
- [V1 Target Inventory](./docs/V1_TARGET_INVENTORY.md)
- [Development](./docs/development.md)
- [Continuum](./docs/continuum.md)
- [Dongle](./docs/dongle.md)
- Keyboards:
  - [Totem](./docs/totem.md)
  - [Urchin](./docs/urchin.md)
  - [Corne / Eyelash Corne](./docs/corne.md)
  - [Sofle / Eyelash Sofle](./docs/sofle.md)
  - [Delta Omega](./docs/delta_omega.md)
  - [Cornix](./docs/cornix.md)

## License

This repository is licensed under the [MIT License](./LICENSE).
