---
name: geekhaven-design-system-auditor
description: GeekHaven mobile design system compliance, tokenized color variables, typography hierarchy, and reusable component instance auditing.
---

# GeekHaven Design System Auditor Skill

## Overview
The `geekhaven-design-system-auditor` skill inspects screen frames against the official GeekHaven mobile design system, enforcing tokenized color variables, strict typography scale hierarchies, and reusable component instance adoption.

## Core Capabilities
- **Brand Palette & Token Enforcement**: Validates that all fills and strokes reference defined semantic tokens (`surface-primary`, `accent-geek`, `status-success`).
- **Typography Scale Hierarchy**: Confirms that text layers adhere to standard mobile scale tokens (Display: 32pt, Title: 24pt, Body: 16pt, Caption: 12pt).
- **Component Instance Linkage**: Flags detached layers that should reference master library components (App Bars, Bottom Navigation Bars, Cards).
- **Dark/Light Mode Symmetry**: Checks that semantic color pairings maintain aesthetic harmony and readability across both light and dark themes.

## Inputs
- `screen_layers`: Array of layer definitions from Figma/FigJam frame trees.
- `theme_mode`: Target visual theme (`dark`, `light`, `both`).

## Outputs
- `token_adoption_rate`: Percentage of layers utilizing design system tokens ($0-100\%$).
- `detached_components`: List of hardcoded frames that should be replaced with master components.
- `typography_anomalies`: Text layers with arbitrary or non-standard font sizes.
