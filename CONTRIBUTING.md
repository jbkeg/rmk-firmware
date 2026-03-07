# Contributing

Thanks for improving this RMK firmware repository.

## Scope

Contributions are welcome for:

- Firmware/runtime sources: `src/*`
- Target profiles: `profiles/**/*.toml`
- Continuum core and matrix maps: `continuum/**/*`, `tools/generate_continuum_layers.py`
- Build/release setup: `Makefile.toml`, `.github/workflows/*`
- Documentation: `README*.md`, `docs/*`

## Workflow

1. Fork the repository.
2. Create a focused branch for one change set.
3. Keep changes minimal and scoped.
4. Validate locally.
5. Open a PR with context and evidence.

## Validation Guidance

For firmware/profile updates:

- Confirm profile path and role mapping are correct.
- Confirm expected tasks exist in `Makefile.toml`.
- Run at least one representative build:
  - `cargo make build-<artifact> --release`

For Continuum updates:

- Run `python tools/generate_continuum_layers.py`.
- Confirm generated layout sections are updated in `profiles/keyboard/*.toml`.
- Rebuild at least one affected keyboard family.

For docs updates:

- Follow `docs/docs_rules.md`.
- Keep artifact names and commands exact.
- Keep docs aligned with current repo state.

## PR Description Checklist

Include:

- What changed
- Why it changed
- How it was validated
- Known limitations or follow-up items

## Reporting Issues

When opening an issue, include:

- Target artifact name(s)
- Profile path(s)
- Expected behavior
- Actual behavior
- Reproduction steps
- Commit SHA or release tag
