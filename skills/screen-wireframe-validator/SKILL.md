---
name: screen-wireframe-validator
description: Mobile screen wireframe inspection, minimum touch target area verification, and empty/loading state completeness checking.
---

# Screen Wireframe Validator Skill

## Overview
The `screen-wireframe-validator` skill reviews low- and mid-fidelity wireframe layouts, ensuring components satisfy physical touch target ergonomics ($44\times 44\text{pt}$), visual hierarchy is balanced, and essential edge-case states (empty, loading, error) are accounted for.

## Core Capabilities
- **Touch Target Boundary Audit**: Verifies that tap targets for buttons, icons, and chips measure at least $44 \times 44\text{pt}$ with adequate padding separation.
- **Edge-Case State Checking**: Confirms that screens include wireframes for empty states, skeleton loading placeholders, and error retry dialogs.
- **Cognitive Load Auditing**: Uses Miller's Law and Hick's Law heuristics to flag excessive options or cluttered information density per viewport.
- **Cross-Device Aspect Ratio Testing**: Checks responsive frame scaling between standard mobile screen widths ($375\text{px} - 430\text{px}$).

## Inputs
- `wireframe_frames`: List of screen frames with element dimensions and positions.
- `screen_name`: Name of the module screen (e.g., `LeaderboardScreen`, `ProfileScreen`).

## Outputs
- `ergonomic_rating`: Compliance score for touch accessibility ($0-100$).
- `undersized_touch_targets`: List of interactive elements smaller than $44\times 44\text{pt}$.
- `missing_edge_states`: Checkpoint report on empty, loading, and error states.
