# Firmware Changelog Template

Use this template for release notes where behavior impact matters more than raw diff size.

## Release Metadata

- Release: `<tag or milestone>`
- Date: `<YYYY-MM-DD>`
- Scope: `<artifacts/families>`
- Base branch: `<branch>`
- Compared against: `<previous tag/commit>`
- RMK revision: `<version or commit>`

## Summary

Short statement of user-visible changes.

## Behavior Changes

### Breaking / User Action Required

- `<change>` - `<required action>`

### Typing and Layer Behavior

- `<layer/behavior change>`
- `<combo or tap-hold timing change>`

### Wireless / Split / Profiles

- `<pairing or reconnect change>`
- `<profile/output mode change>`

### Power / Battery

- `<sleep/idle change>`
- `<battery reporting change>`

### Display / Scanner / Dongle

- `<status UI change>`
- `<scanner protocol or channel behavior>`

## Build and Target Changes

- Added artifacts:
  - `<artifact>`
- Removed artifacts:
  - `<artifact>`
- Renamed artifacts:
  - `<old> -> <new>`

## Validation Evidence

### Build

- `cargo make build-<artifact> --release`: `<result>`
- `cargo make uf2-<artifact> --release`: `<result>`

### Hardware Runtime

- `<family/role>`: `<result>`
- Checked scenarios:
  - `<pairing/reconnect>`
  - `<sleep/wake>`
  - `<critical typing behavior>`

## Known Issues / Follow-up

- `<issue>`

## Rollback Plan

1. Flash matching reset artifact.
2. Flash previous known-good firmware.
3. Re-pair if bonds changed.
