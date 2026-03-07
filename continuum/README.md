# Continuum Canonical Core

This directory is the source of truth for Continuum layer payload generation in RMK.

## Structure

- `core/layers.toml`: Canonical slot order and canonical layer payloads.
- `matrix/<family>.toml`: Per-family slot-to-matrix mapping.
- `generated/<family>.toml`: Generated layout payloads for each family.

## Generate

Run:

```bash
cargo run --manifest-path tools/generate_continuum_layers/Cargo.toml --target host-tuple --release
```

The generator updates:

- `continuum/generated/*.toml`
- `profiles/keyboard/<family>.toml` `[layout]` sections

Generated keyboard profiles are then consumed by per-target `cargo make` tasks.
