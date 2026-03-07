# Road to V1: Full ZMK to RMK Port (Keyboard + Continuum + Dongle + Scanner)

## Summary

- V1 scope includes all four pillars:
  1. Keyboard
  2. Continuum
  3. Dongle (`basic`, `zdd`, `prospector`)
  4. Scanner (`prospector`)
- Coverage: `totem`, `urchin`, `corne`, `eyelash_corne`, `sofle`, `eyelash_sofle`, `delta_omega`, `cornix`.
- Architecture: single RMK crate with multiple bins and per-target profile TOMLs.
- Completion gate: all targets green (build + hardware regression), direct commit/push per milestone.

## Public Interfaces and Artifacts

- Keep artifact compatibility:
  - Per family: `*_left`, `*_right`, `*_left_w_dongle`, `*_dongle`, `*_zdd_dongle`, `*_prospector_dongle`
  - Shared: `prospector_scanner`, `reset_nice_nano_v2`, `reset_seeeduino_xiao_ble`
- Profiles:
  - `profiles/keyboard/<family>.toml`
  - `profiles/dongle/basic/<family>.toml`
  - `profiles/dongle/zdd/<family>.toml`
  - `profiles/dongle/prospector/<family>.toml`
  - `profiles/scanner/prospector_scanner.toml`
- Shared Continuum source-of-truth:
  - `continuum/core/*`
  - `continuum/matrix/<family>.toml`
  - generated layer payloads consumed by target profiles
- RMK-native scanner protocol:
  - `src/protocol/status_adv.rs` with `StatusFrameV1`
  - fields: protocol/version, keyboard id, channel, layer, output mode, profile, battery(main/peer), flags, wpm
- Scanner UI mode in v1: non-touch only.

## Milestones (test + commit + push)

1. M0 Scope reset and inventory freeze
2. M1 Multi-bin build architecture
3. M2 Continuum canonical core
4. M3 Keyboard foundation across all families
5. M4 Keyboard behavior parity pass
6. M5 Basic dongle role (all families)
7. M6 ZDD dongle role (all families)
8. M7 Prospector dongle role (all families)
9. M8 Prospector scanner role
10. M9 CI/release matrix parity
11. M10 Full hardware regression
12. M11 Release prep and v1 lock

## Assumptions

- Single repo/crate (`d:\rmk-firmware`), multi-bin architecture
- RMK-native dongle/scanner (no ZMK interoperability bridge in v1)
- Shared Continuum core (no per-keyboard behavior forks)
- Scanner non-touch in v1
- Functional display parity (not pixel-identical)
- All required hardware is available
- Minimal RMK patching is allowed only for parity-critical gaps
