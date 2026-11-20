# Changelog

All notable changes to dpx_pd_pooper. Format follows [Keep a Changelog](https://keepachangelog.com/en/1.0.0/). Revisions use the board stamp (v0dN), not semver.

## [Unreleased]

### Added
- GitHub Pages deploy (`.github/workflows/pages.yml`): manual at the site root, interactive BOM at `/ibom/`.
- `hardware/production_files_RTG/v0d8-ch224a-silk2/`: regenerated fab files after a silkscreen-only tweak (top silk text moved, bottom QR box shifted 1.14 mm). Copper, mask, paste, drill, BOM and CPL are identical to `v0d8-ch224a`.
- docs: README rewritten with real content, this changelog, and a single-page manual in `docs/`.
- `.gitignore`: KiCad `*-backups/` folders.
- images: v0d8 front render and a front-to-back flip animation (GIF and MP4).

## [v0d8-ch224a] - 2026-11-18

Sent to JLC production. Untested until the boards arrive.

### Added
- CH224A (C42459160) replaces the CH224K, which JLC no longer had in stock.
- VSEL jumper header J3 (2x5): shunt one column to select 9 / 12 / 15 / 20 / 28 V. No shunt gives 5 V.
- Selector resistors R7 6.8k, R8 24k, R9 56k, R10 120k, R11 210k on the CFG1 line.
- Fab files in `hardware/production_files_RTG/v0d8-ch224a/` (BOM, CPL, gerbers).
- 3D model for the FB1 ferrite footprint.

### Changed
- Version stamp v0d8, date 11.18.26.
- CFG2 and CFG3 left to the chip's internal pull-ups (no-connect on the schematic).
- R5 kept at 10k for first power-up, because the CH224A VBUS pin tolerance is stated two ways in the datasheet.

### Removed
- The 3-position DIP switch (SW1) from v0d5.

### Known issues
- Back silk text overflows the board edge and overlaps reference designators.
- Version stamp does not distinguish the CH224A board from later spins.

## [v0d5-ch224k] - 2024-11-26

Tagged `ch224k`. The tested baseline: CH224K with a 3-position DIP switch.
