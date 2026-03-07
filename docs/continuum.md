# Continuum

This document describes the RMK-native Continuum framework used in this repository.

## Goal

Continuum keeps one shared behavior/layer model across all keyboard families while allowing per-family matrix adaptation.

## Structure

- `continuum/core/layers.toml`
  - Canonical slot order and layer payload definitions.
- `continuum/matrix/<family>.toml`
  - Per-family matrix geometry and slot mapping.
- `continuum/generated/<family>.toml`
  - Generated family payload output.
- `tools/generate_continuum_layers/*`
  - Generator that materializes per-family layout payloads and patches keyboard profiles.

## Layer Model

Canonical layers are defined once in `continuum/core/layers.toml` and mapped to each family via `continuum/matrix`.

This avoids duplicated per-keyboard behavior definitions.

## Generation

Run:

```bash
cargo run --manifest-path tools/generate_continuum_layers/Cargo.toml --target host-tuple --release
```

Generator outputs:

- `continuum/generated/*.toml`
- `[layout]` updates in `profiles/keyboard/*.toml`

## Integration Contract

Keyboard profiles consume generated Continuum payloads. Dongle/scanner profiles do not own independent layer models.

If a behavior change affects all keyboards, update `continuum/core/layers.toml` first.

If only physical placement changes for one family, update `continuum/matrix/<family>.toml`.
