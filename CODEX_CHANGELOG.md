# Matrix Change Log

This file is a handoff-friendly running summary of major changes made to the Matrix app in this folder.

Primary app file:
- [`index.html`](I:\[13] APPS\CODEX\index.html)

Reference docs:
- [`APP_OVERVIEW.md`](I:\[13] APPS\CODEX\APP_OVERVIEW.md)
- [`CODEX_CHANGELOG.md`](I:\[13] APPS\CODEX\CODEX_CHANGELOG.md)

## Version 3.0

Baseline app state described by the project brief:

- Single-file HTML/CSS/JS document builder
- Multi-project system stored in IndexedDB
- Sections for cover, TOC, overview, product, moodboard, storyboard, shot list, film script, commercial copy, timeline, gear, props, and notes
- Themes for Matrix Dark and Mono
- Print / PDF workflow
- Storyboard grid and film-script pagination support

## Version 3.1

Trust, stability, backup, and workflow improvements:

- Fixed visible text/encoding issues in the UI so labels and symbols render correctly
- Added canonical project metadata behavior:
  - Project name now stays tied to project management
  - Cover title and overview title no longer silently rename the saved project
- Added top-bar save-state feedback:
  - `Unsaved changes`
  - `Saving...`
  - `Saved`
  - `Autosaved {time}`
  - `Save failed`
- Reworked saving to use direct IndexedDB lookup for the active project instead of scanning all projects during autosave
- Added full-project and document-only JSON export/import modes
- Added safer confirmation flow for destructive actions like replace-all and folder deletion
- Improved find/replace:
  - Match case option
  - Scope selector by section
  - Per-section match counts
- Added keyboard shortcuts:
  - `Ctrl/Cmd + S`
  - `Ctrl/Cmd + F`
  - `Ctrl/Cmd + P`
  - `Esc`
- Added responsive improvements for smaller laptop/tablet layouts
- Added image preprocessing/compression before storing uploaded images
- Updated page counting so rendered preview pages are used as the authoritative TOC/page-number source

## Version 3.2

Document layout polish and print-fit cleanup:

- Tightened overall A4 page spacing and page chrome
- Reduced clipping/overflow risk in dense sections
- Improved formatting in:
  - Timeline
  - Shot List
  - Gear
  - Props
  - Notes
- Added density-aware compact fallback classes for crowded sections
- Improved wrapping and spacing in cards, tables, dates, labels, and version-history rows

## Version 3.3

Document sizing modes and subtle screen motion:

- Added 3 document density modes:
  - `Compact`
  - `Standard`
  - `Spacious`
- Added top-bar selector for switching density modes
- Density mode is now stored in project data and persists across save/reload
- Replaced many fixed print-layout values with shared density tokens controlling:
  - Page padding
  - Header/footer spacing
  - Section title sizes
  - Body text sizing and line height
  - Grid/card/table spacing
  - Cover scale and spacing
  - Timeline density
  - Notes density
- Updated film-script pagination heuristics to respond to the chosen density mode
- Kept A4 page size fixed while changing internal document density only
- Added subtle screen-only motion:
  - Modal fade/scale
  - Preview page fade/slide in
  - Form section reveal
  - Overlay fade polish
- Added `prefers-reduced-motion` handling
- Kept print output animation-free

## Current Notes

Current architecture:

- The app is still intentionally single-file
- Main logic, styling, and UI remain inside [`index.html`](I:\[13] APPS\CODEX\index.html)
- Project storage is local browser storage via IndexedDB

Things not yet done:

- Cloud sync / remote backup
- PWA manifest/icon setup
- Full live browser QA pass for every section after all layout changes
- Cross-device persistence
- Sidebar drag-reordering for sections

## Handoff Notes For Another Codex Session

If another Codex instance continues work on this project, it should assume:

- The latest source of truth is [`index.html`](I:\[13] APPS\CODEX\index.html)
- The app now includes save-state UX, import/export modes, scoped find/replace, image compression, layout compaction, density modes, and subtle motion
- Layout work should continue carefully because many print-facing values are now token-driven by density mode
- Any new print/layout change should be tested against all 3 density modes:
  - Compact
  - Standard
  - Spacious
