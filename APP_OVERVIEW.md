# Matrix - Document Builder

## Overview
Matrix is a browser-based production document builder for film and commercial work. It runs as a single-file web app built entirely inside `index.html`, with no frameworks, build tools, or external dependencies beyond a Google Fonts import.

The app is designed to let a user create, organize, preview, and print professional multi-page production documents from one interface. It supports both creative-development pages and practical production-planning pages, all with a live A4-style preview.

## What The App Does
Matrix lets a user:

- Create and manage multiple projects locally in the browser
- Build multi-section production documents
- Toggle document sections on or off
- Preview pages live before print/export
- Print the final document to PDF through the browser
- Store projects locally in IndexedDB
- Import and export either full projects or document-only JSON files
- Export CSVs for selected production tables

## Main Sections
The document builder currently supports these sections:

- Cover
- Table of Contents
- Overview
- Product Features
- Moodboard
- Storyboard
- Shot List
- Film Script
- Commercial Copy
- Timeline
- Gear
- Props
- Notes

## Core Functions

### Document Building
- Live preview panel that renders the current document as A4 pages
- Section visibility controls in the sidebar
- Auto-generated table of contents
- Storyboard builder with multi-page support
- Film script pagination support
- Commercial copy mode for non-film copywriting layouts

### Project Management
- Multi-project system stored in IndexedDB
- Project list/grid view
- Folder support
- Color tag support
- Duplicate, edit, open, and delete actions
- Per-project cover image support

### Save And Backup
- Manual save
- Autosave
- Save-state indicator in the top bar
- Full-project JSON export/import
- Document-only JSON export/import
- CSV export for Shot List, Gear, and Props

### Editing Utilities
- Scoped find and replace
- Match-case option for replace
- Keyboard shortcuts:
  - `Ctrl/Cmd + S` saves
  - `Ctrl/Cmd + F` opens find/replace
  - `Ctrl/Cmd + P` prints
  - `Esc` closes open overlays/modals where applicable

### Visual / UX Features
- Matrix Dark theme
- Mono theme
- Cover background image upload
- Image uploads for moodboard, references, storyboard frames, and project covers
- Responsive behavior for desktop, smaller laptop widths, and tablet-style layouts

## Tech Stack
- Single-file `HTML / CSS / JavaScript`
- Browser `IndexedDB` for local storage
- Google Fonts: `Bebas Neue` and `Space Grotesk`
- No framework
- No package manager required
- No compile step

## Files In This Folder
- [`index.html`](I:\[13] APPS\CODEX\index.html): the full application
- [`APP_OVERVIEW.md`](I:\[13] APPS\CODEX\APP_OVERVIEW.md): this guide

## What Is Needed To Run It
To run Matrix, a user needs:

- A modern browser such as Chrome, Edge, or another Chromium-based browser
- JavaScript enabled
- Local browser storage available, because projects are saved in IndexedDB

No install, build, or package setup is required.

## How To Run It Locally

### Simplest Option
1. Open [`index.html`](I:\[13] APPS\CODEX\index.html) directly in a browser.
2. The app should load immediately.
3. Projects will save locally in that browser profile.

### Better Option For Iteration
Serve the folder with a small local web server, then open the app in a browser. This is useful if you want a cleaner browser workflow while editing.

Example approaches:
- Use a lightweight local HTTP server
- Or host the file on Vercel for deployed access

## How To Use It
1. Open the app.
2. Create a new project from the Projects panel.
3. Choose sections from the sidebar.
4. Fill in the form panel for the selected section.
5. Watch the live preview update on the right.
6. Save manually or let autosave persist changes.
7. Print to PDF when ready.

## Storage Behavior
- Projects are stored locally in the browser using IndexedDB
- Data is tied to the browser/profile/device unless exported
- Clearing browser storage may remove saved projects
- Full-project export should be used for backup

## Good To Know
- This app is currently built as a single large HTML file
- Most app logic, styling, and UI are embedded directly in `index.html`
- Because it is single-file, changes are fast to deploy but harder to modularize
- Vercel deployment can be updated by replacing the hosted `index.html`

## Recommended Usage Notes
- Use full-project export for backups
- Use document-only export when reusing the document content inside another project shell
- Use Chrome or Edge if installing as a desktop-like app is important

## PWA / Deployment Notes
- The app is suitable for static hosting
- It can be deployed on Vercel as a static page
- If a manifest and icons are added, it can behave more like a full installable PWA

## Future Improvement Areas
- App icon and manifest assets
- Cloud sync / backup
- Section reordering in the sidebar
- Character tracker
- Budget tracker
- Further modularization of the single-file codebase
