# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Classplay Design System — a self-contained, single-page HTML documentation site for the Classplay gamified LMS platform. No build tools, no frameworks, no dependencies. Everything lives in `index.html` (~4700 lines of embedded CSS, JS, and HTML).

## Running Locally

```bash
# Simple HTTP server (avoids CORS issues with font loading)
npx http-server .
# OR
python -m http.server 8000
```

No build step, no install, no linting configured.

## Architecture

### Single-file structure (`index.html`)

1. **CSS** — Design tokens + component styles + layout
2. **HTML** — Sidebar nav, header, main content sections, embedded Markdown spec
3. **JavaScript** — Theme toggle, scroll spy, interactive demos, dynamic rendering

### CSS Token Convention

All tokens use `--cp-` prefix (Classplay):
- Color scales: `--cp-primary-50` to `--cp-primary-900`, plus functional colors (`--cp-xp`, `--cp-streak`, `--cp-success`, `--cp-danger`, etc.)
- Surface colors (theme-aware): `--cp-bg-primary`, `--cp-text-primary`, etc.
- Typography: `--cp-font-family` (Nunito), `--cp-font-heading` (Sora), `--cp-font-mono` (JetBrains Mono)
- Spacing: `--cp-space-1` to `--cp-space-20` (4px base)
- Radius, shadows, z-index, transitions all follow `--cp-` prefix

### Layout Classes

Design system chrome uses `ds-` prefix: `.ds-sidebar` (fixed 240px), `.ds-header`, `.ds-main` (fixed position, scrollable content).

Component classes use `cp-` prefix: `.cp-btn`, `.cp-card`, `.cp-badge`, `.cp-avatar`, `.cp-progress`, `.cp-modal`, etc.

### Theme System

Data-attribute based: `<html data-theme="dark">`. Theme toggle persists to localStorage. Surface tokens change per theme; color scales stay constant.

### Key JS Functions

- `toggleTheme()` / `updateThemeIcon()` — dark/light mode
- `initScrollSpy()` — sidebar active link tracking
- `copySwatch(hex)` — copy color to clipboard with toast
- `downloadMarkdown()` — extract embedded spec as `.md` file
- `renderSwatches()`, `renderSurfaceSwatches()`, `renderTypography()`, `renderSpacing()`, `renderRadius()`, `renderShadows()` — dynamic section rendering

## Git

- **Current branch:** `master`
- **PR target:** `main`
- Commit style: conventional commits (`feat:`, `fix:`, `refactor:`, etc.)

## Docs

- [Design system spec](docs/superpowers/specs/2026-03-23-classplay-design-system.md) — full Markdown specification
- [Implementation plan](docs/superpowers/plans/2026-03-23-classplay-design-system-page.md) — build plan reference
