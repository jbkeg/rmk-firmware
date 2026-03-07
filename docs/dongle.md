# Dongle

This document defines dongle/scanner roles in the RMK migration.

## Scope

Dongle role is fixed by built artifact. Runtime role switching is not supported.

Role changes require reflashing and usually re-pairing.

## Roles

- `basic` dongle
  - Headless transport role (`*_dongle`).
- `zdd` dongle
  - Display-enabled dongle (`*_zdd_dongle`).
- `prospector` dongle
  - Prospector hardware/display role (`*_prospector_dongle`).
- `prospector_scanner`
  - Status observer role (not input transport).

## Artifact Matrix

Per keyboard family:

- `<family>_dongle`
- `<family>_zdd_dongle`
- `<family>_prospector_dongle`

Shared scanner artifact:

- `prospector_scanner`

## Build Commands

Examples:

```bash
cargo make build-totem_dongle --release
cargo make uf2-totem_zdd_dongle --release
cargo make uf2-corne_prospector_dongle --release
cargo make uf2-prospector_scanner --release
```

## Reset and Recovery

Use reset artifacts by MCU family:

- `uf2-reset_nice_nano_v2`
- `uf2-reset_seeeduino_xiao_ble`

Typical recovery sequence:

1. Flash matching reset artifact.
2. Flash target runtime artifacts.
3. Remove stale host/device bonds.
4. Re-pair and verify reconnect.

## Scanner Notes (V1)

- Scanner UI mode in v1 is non-touch observer mode.
- Channel filtering and status advertisement flow are part of the scanner milestone plan.
- Scanner does not carry keyboard input to host.
