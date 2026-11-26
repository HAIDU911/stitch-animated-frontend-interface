---
name: "Calm Administrative Clarity — SQMS"
description: "An institutional registrar-grade design system for the Student Query Management System, prioritizing structured tables, hairline borders, and restrained semantic color."
---

## Overview

The **Student Query Management System (SQMS)** embodies **Calm Administrative Clarity**—the quiet, trustworthy precision of a well-run university registrar's office. Designed for students, department staff, and university administrators, the interface is information-dense yet effortless to scan, with left-aligned data-first workspaces and purposeful, understated motion that clarifies state transitions without distraction.

**Do's and Don'ts:**
- **Prefer** structured tables, 1px hairline borders (`#DDE2E9`), clear typographic hierarchy, left-aligned data-first workspaces, and restrained semantic color reserved strictly for status and priority.
- **Avoid** purple/blue gradients, glassmorphism or backdrop blur, glowing blobs, oversized hero sections, emoji used as UI icons, centered marketing-style layouts, and decorative illustrations on working screens.

## Colors

The palette anchors on a deep institutional navy (`#1F3A5F`) for primary actions and header chrome, paired with warm brass (`#B7791F`) reserved strictly for active navigation indicators and key highlights. Color is otherwise neutral and quiet so semantic status and priority badges stand out immediately.

```yaml
colors:
  primary: "#1F3A5F"
  on-primary: "#FFFFFF"
  primary-hover: "#17304F"
  primary-container: "#EBF1FF"
  on-primary-container: "#143155"
  link: "#2B6CB0"
  on-link: "#FFFFFF"
  accent-brass: "#B7791F"
  on-accent-brass: "#1F1F1F"
  accent-brass-tint: "#FFEEDE"
  on-accent-brass-tint: "#472A00"
  page: "#F5F7FA"
  surface: "#FFFFFF"
  on-surface: "#1B2430"
  surface-subtle: "#F5F7FA"
  on-surface-subtle: "#5B6675"
  ink: "#1B2430"
  text-secondary: "#5B6675"
  border: "#DDE2E9"
  border-strong: "#BEC7D7"
  status-submitted-bg: "#F1F5F9"
  status-submitted-fg: "#334155"
  status-assigned-bg: "#EBF4FF"
  status-assigned-fg: "#1E4E8C"
  status-progress-bg: "#FEF3C7"
  status-progress-fg: "#92400E"
  status-resolved-bg: "#DCFCE7"
  status-resolved-fg: "#166534"
  status-closed-bg: "#E2E8F0"
  status-closed-fg: "#475569"
  priority-high: "#BA1A1A"
  on-priority-high: "#FFFFFF"
  priority-high-tint: "#FFEDEA"
  on-priority-high-tint: "#690005"
  priority-medium-bg: "#FEF3C7"
  priority-medium-fg: "#92400E"
  priority-low-bg: "#F1F5F9"
  priority-low-fg: "#475569"
  error: "#BA1A1A"
  on-error: "#FFFFFF"
  error-tint: "#FFEDEA"
  on-error-tint: "#690005"
  success: "#166534"
  on-success: "#FFFFFF"
  success-tint: "#DCFCE7"
  on-success-tint: "#166534"
```

## Typography

**IBM Plex Sans** serves all UI copy, headings, labels, and tables for crisp institutional legibility. **IBM Plex Mono** is reserved for query reference numbers (e.g., `Q-2026-0142`), registration IDs (`2023-CS-114`), and tabular metadata. Table headers use 12px uppercase with `+0.04em` letter-spacing.

```yaml
typography:
  display-sm:
    fontFamily: "IBM Plex Sans"
    fontSize: 32px
    fontWeight: 600
    lineHeight: 40px
    letterSpacing: -0.4px
  headline-md:
    fontFamily: "IBM Plex Sans"
    fontSize: 24px
    fontWeight: 600
    lineHeight: 32px
    letterSpacing: -0.2px
  title-lg:
    fontFamily: "IBM Plex Sans"
    fontSize: 20px
    fontWeight: 600
    lineHeight: 28px
    letterSpacing: -0.1px
  title-md:
    fontFamily: "IBM Plex Sans"
    fontSize: 16px
    fontWeight: 600
    lineHeight: 24px
  body-md:
    fontFamily: "IBM Plex Sans"
    fontSize: 14px
    fontWeight: 400
    lineHeight: 21px
  body-lg:
    fontFamily: "IBM Plex Sans"
    fontSize: 16px
    fontWeight: 400
    lineHeight: 24px
  body-sm:
    fontFamily: "IBM Plex Sans"
    fontSize: 12px
    fontWeight: 400
    lineHeight: 18px
  label-lg:
    fontFamily: "IBM Plex Sans"
    fontSize: 14px
    fontWeight: 500
    lineHeight: 20px
  label-md:
    fontFamily: "IBM Plex Sans"
    fontSize: 12px
    fontWeight: 500
    lineHeight: 16px
  label-table:
    fontFamily: "IBM Plex Sans"
    fontSize: 12px
    fontWeight: 600
    lineHeight: 16px
    letterSpacing: 0.48px
  mono-md:
    fontFamily: "IBM Plex Mono"
    fontSize: 14px
    fontWeight: 500
    lineHeight: 20px
  mono-sm:
    fontFamily: "IBM Plex Mono"
    fontSize: 12px
    fontWeight: 500
    lineHeight: 16px
```

## Layout & Spacing

The application uses a 12-column responsive grid inside a `1200px` max-width container (`px-6` on desktop, `px-4` on mobile), aligned to a strict 8pt spacing scale with a 4px half-step for micro-adjustments.

```yaml
spacing:
  xs: 4px
  sm: 8px
  md: 12px
  lg: 16px
  xl: 24px
  2xl: 32px
  3xl: 48px
```

## Elevation & Depth

SQMS uses a flat, hairline-bordered architecture (`1px solid #DDE2E9`) to separate tables, panels, and form controls without visual noise. Subtle drop shadows are applied exclusively to floating modals, dropdown menus, and slide-over drawers.

## Shapes

Form inputs, buttons, and compact badges use a crisp `6px` corner radius (`DEFAULT`). Panels, data tables, cards, and modals use `8px` (`md`). Status dots and avatars use `full`.

```yaml
rounded:
  sm: 4px
  DEFAULT: 6px
  md: 8px
  full: 9999px
```

## Motion & Micro-interaction

Motion is crisp, purposeful, and understated—supporting administrative speed rather than decorative flair. Micro-interactions (button hover, focus ring, row hover, tab underline) settle within `150ms`. Panels, drawers, and modals enter with a clean decelerating curve (`220ms`) and exit quickly (`150ms`). All animations respect `prefers-reduced-motion` and animate only `transform`, `opacity`, and `color`.

```yaml
motion:
  state-change:
    duration: 150ms
    delay: 0ms
    timingFunction: cubic-bezier(0.2, 0, 0, 1)
  surface-enter:
    duration: 220ms
    delay: 0ms
    timingFunction: cubic-bezier(0.16, 1, 0.3, 1)
  surface-exit:
    duration: 150ms
    delay: 0ms
    timingFunction: cubic-bezier(0.4, 0, 1, 1)
  drawer-slide:
    duration: 260ms
    delay: 0ms
    timingFunction: cubic-bezier(0.16, 1, 0.3, 1)
```

## Voice & Content Strategy

- **Tone:** Calm, direct, institutional. Plain-spoken university registrar language without marketing buzzwords.
- **Capitalisation:** Sentence case for page headings, buttons, and form labels; uppercase `12px` for table column headers.
- **Action labels:** Verb-led and specific (`Submit Query`, `Update Status`, `Clear Filters`, `View Details`).
- **Date & Time:** Consistent `26 Nov 2026, 14:05` format paired with relative time (`2 hours ago`) in secondary text.
- **Disabled & Empty states:** Disabled controls always explain why; empty states include a simple line icon, one clear sentence, and one primary action.

## Components

Component implementations live as individual HTML sticker sheet files in
`components/`. Each file contains the canonical, styled HTML components with
`<!-- COMPONENT: name -->` comment markers. Read each file before use.

- **Badge** → `@components/badge.html` — `badge-numeric`, `badge-dot`
- **Button** → `@components/button.html` — `button-primary`, `button-icon`, `button-with-icon`
- **Input Field** → `@components/input-field.html` — `input-field-text`, `input-field-icon`
- **Modal** → `@components/modal.html` — `modal-standard`, `modal-alert`, `modal-drawer`
- **Table** → `@components/table.html` — `table-standard`, `table-interactive`, `table-selectable`
