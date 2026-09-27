---
name: interactive-hifi-prototyper
description: High-fidelity interactive prototype connection verification, mobile gesture animation auditing, and developer handoff packaging.
---

# Interactive HiFi Prototyper Skill

## Overview
The `interactive-hifi-prototyper` skill audits high-fidelity Figma prototype connections, ensuring that mobile transitions (push, modal slide, bottom sheet expand) animate with realistic physics and outputs structured developer handoff specifications.

## Core Capabilities
- **Mobile Gesture Verification**: Validates appropriate gesture triggers (`On tap`, `On drag`, `On swipe`) for mobile components like sliders, carousels, and bottom sheets.
- **Motion Timing & Curve Auditing**: Ensures screen transitions use natural durations ($250-350\text{ms}$) and appropriate easing curves (Ease Out, Spring Damping).
- **WCAG 2.1 AA Contrast Auditing**: Mathematically verifies text luminance contrast against backgrounds to guarantee accessibility.
- **Handoff Specification Packaging**: Generates CSS/Tailwind/Flutter token mappings and SVG asset manifests for engineering implementation.

## Inputs
- `prototype_flow_data`: Serialized interaction connections and screen transitions.
- `target_framework`: Intended engineering target (e.g., `Flutter`, `React Native`).

## Outputs
- `prototype_polish_score`: Normalized score ($0-100$) reflecting micro-interaction quality.
- `accessibility_pass_rate`: Percentage of text elements meeting WCAG 2.1 AA contrast.
- `developer_handoff_spec`: Structured markdown specification for engineering handoff.
