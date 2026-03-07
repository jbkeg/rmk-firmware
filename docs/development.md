# Development

This document describes day-to-day local development flow for `rmk-firmware`.

## Core Files

- `Makefile.toml`: build matrix and artifact tasks
- `profiles/*`: per-role and per-family RMK profiles
- `src/*`: role entry bins (`central`, `peripheral`, `dongle-*`, `scanner-*`, `reset`)
- `continuum/*`: canonical shared keymap model
- `tools/generate_continuum_layers/*`: Continuum generator

## Recommended Workflow

1. Edit profile/runtime code.
2. If Continuum changed, regenerate:

```bash
cargo run --manifest-path tools/generate_continuum_layers/Cargo.toml --target host-tuple --release
```

3. Build the target you changed:

```bash
cargo make build-<artifact> --release
```

4. If flashing is needed, emit UF2:

```bash
cargo make uf2-<artifact> --release
```

5. Run additional representative builds for adjacent targets.

## Task Discovery

List available tasks:

```bash
cargo make --list-all-steps
```

Important aggregate tasks:

- `build-matrix`: compile all artifacts
- `uf2`: generate UF2 for all artifacts

## Artifact Naming Rules

Compatibility-critical names are frozen:

- Keyboard: `*_left`, `*_right`, `*_left_w_dongle`
- Dongle: `*_dongle`, `*_zdd_dongle`, `*_prospector_dongle`
- Scanner: `prospector_scanner`
- Reset: `reset_nice_nano_v2`, `reset_seeeduino_xiao_ble`

When adding new tasks, keep naming conventions stable.

## Troubleshooting

- `KEYBOARD_TOML_PATH`/profile mismatch:
  - Check task env vars in `Makefile.toml`.
- Continuum changes not reflected:
  - Re-run generator and check `profiles/keyboard/*.toml` layout sections.
- UF2 not emitted:
  - Ensure corresponding `objcopy-*` and `uf2-*` tasks exist.
- Split reconnect issues after flashing:
  - Flash reset artifact for the MCU family, then re-pair.
