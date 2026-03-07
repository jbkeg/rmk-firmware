# Documentation Rules

This file defines documentation quality and consistency rules for this RMK repository.

## Required Structure for Keyboard Docs

Each keyboard doc in `docs/*.md` should include:

- Title and one-line scope
- Support snapshot (active artifacts)
- Reference material
- Hardware overview
- Layout section (physical + keymap images when available)
- RMK profile/build section
- Flashing/recovery section
- Status notes

## Accuracy Rules

- Do not mark unimplemented targets as active.
- Artifact names must match `Makefile.toml` tasks.
- Profile paths must match files in `profiles/`.
- If support is partial, explicitly state the gap.

## Asset Rules

- Store images in `docs/images/`.
- Keep stable names when replacing images.
- Avoid duplicate copies of the same diagram.

## Formatting Rules

- Keep paths in backticks.
- Use numbered steps for procedures.
- Keep wording factual and concise.
- Keep build commands copy/paste-ready.

## Change Coupling

When structure changes in `profiles/`, `continuum/`, or `Makefile.toml`, update affected docs in the same commit.
