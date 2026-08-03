# Changelog

## v0.3.0 — 3 August 2026

### KDP production

- Added deterministic interior-page calculations with a 24-page minimum.
- Set the KDP Production Mode default to 14 generated content pages while preserving the Starter range of 5–15.
- Added live generated-page and estimated final-interior summaries.
- Added UK and US large-trim black-ink pricing and dynamic royalty thresholds.
- Added spine-width calculation and the 80-page spine-text rule.

### Cover and export workflow

- Separated cover assets from interior manuscript pages.
- Added front-cover and back-cover artwork generation states.
- Added one-page full-wrap KDP paperback cover assembly.
- Added separate interior and cover PDFs.
- Added a complete KDP package ZIP containing PDFs and cover PNG assets.

### Review experience

- Added the live Book Page Calculator to the concept review screen.
- Kept compact word and character counters for editable concept text.
- Clarified that cover assets are excluded from the interior manuscript count.

### Research and settings

- Preserved the DataForSEO connection test separately from the Amazon Market Research enable/disable toggle.
- Disabled Amazon research when the feature toggle is off while keeping KDP production available.

### Verification

- Google AI Studio reports 202 passing automated assertions.
- Repository preparation found no embedded credentials and no TypeScript/TSX syntax diagnostics across 23 files.
