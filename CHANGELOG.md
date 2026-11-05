# Changelog

## 1.2.0 — 2026-11-05

Feedback button.

- **Feedback** button in the header, next to the light/dark toggle. It opens a short form (in a new tab) for bugs, questions and ideas about this app

## 1.1.0 — 2026-11-04

Nordic theme, light and dark modes, accessibility.

- New look shared across the CAITO tool suite: an airy Nordic palette with its own accent and icon (also the browser tab icon)
- **Light / dark toggle** in the header. It follows your device until you choose, then remembers your choice across all the tools
- Inter font (SIL Open Font License) is now built into the file, so the app makes no font requests and looks the same everywhere
- Accessibility: every control has a label, all text meets WCAG AA contrast in both modes, and keyboard focus is clearly visible
- The old theme button is replaced by the shared toggle; charts redraw when you switch. The report preview stays paper-white.

## 1.0.0 — 2026-11-03

First public release.

- Device inventory with manual entry, RMM / CSV import, inline editing, filtering, sorting and mass editing
- Policy packages with backup schedule and tiered local retention (intra-daily, daily, weekly, monthly) at regular intervals; draft / published status, clone, global default, and "apply to all devices"
- Per-device retention overrides, applied to one device, the selection, or everyone on a policy
- Global settings: FIPS encryption storage markup, compression/dedupe ratio, monthly change rate, offsite retention as a global policy or per device group
- Monthly storage forecast over a configurable start month and horizon, with data growth as % or GB per month (global or per device) and planned fleet additions
- Watermark and zeroed delta view; live forecast on the Devices tab
- Required capacity, target / full dates, and retention headroom across all policies or per policy
- Named checkpoints with a starred preferred configuration
- Executive report (HTML, prints to PDF) and technician workbook (.xlsx) with inventory, groupings, policy breakdown, device config, overrides and sign-off
- Clear split between labeled sample data and a client plan
- Light and dark themes
- Version check against a public `wyrd.json`, with repository-move support
- Footer with authorship, LinkedIn and Portfolio Toolbox links
