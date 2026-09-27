---
name: mobile-ux-flow-architect
description: User journey mapping, navigation state machine validation, and dead-end screen detection for mobile applications.
---

# Mobile UX Flow Architect Skill

## Overview
The `mobile-ux-flow-architect` skill maps user journeys across mobile society modules, validating that navigation flows through intuitive state transitions, primary conversion actions are accessible, and screens contain zero dead ends.

## Core Capabilities
- **User Journey Traversal**: Ingests FigJam/Figma screen flows from onboarding to core feature goals.
- **Dead-End & Trap Prevention**: Confirms that every modal sheet, drawer, and secondary screen includes clear dismiss or back navigation affordances.
- **Fitts's Law Ergonomics**: Verifies that primary conversion controls are positioned within the reachable lower thumb zone.
- **Progressive Disclosure Auditing**: Checks that complex workflows (e.g., event registration, team creation) break information into digestible multi-step flows.

## Inputs
- `flow_name`: Name of the user flow under evaluation (e.g., `TeamFinderJourney`, `OnboardingFlow`).
- `screen_nodes`: Array of screen objects with incoming and outgoing navigation links.

## Outputs
- `flow_validity`: Overall status (`VALID_FLOW`, `DEADLOCK_DETECTED`, `MISSING_BACK_NAVIGATION`).
- `unreachable_screens`: List of orphan screens lacking inbound navigation connections.
- `ergonomic_recommendations`: Actionable suggestions for primary CTA placement.
