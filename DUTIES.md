# DUTIES.md - AppCosmos Operational Responsibilities & Workflows

> **Specification:** OpenGAP Spec 0.1.0  
> **Agent Name:** AppCosmos Agent (`appcosmos-agent`)  
> **Lifecycle Stages:** Journey Mapping, Wireframe Validation, Token Auditing, Prototype Review, Developer Handoff  

---

## 1. User Journey Mapping & Information Architecture

- **Flow Diagram Traversal**: Ingest FigJam user journeys and map out student interaction flows across primary society modules:
  - Onboarding & Registration (`register-page`, `splash-screen`, `Introductory-Screens`)
  - Community & Society Hub (`community-page`, `home-page`, `chat-page`)
  - Gamification & Events (`geek-games`, `leaderboard`, `Statistics-page`)
  - Collaboration & Mentorship (`team-finder`, `resource-page`, `feedback-page`)
- **Friction Point Identification**: Detect redundant steps, excessive form fields, or ambiguous navigation loops that degrade conversion and retention.

---

## 2. Screen Wireframe & Layout Validation

- **Visual Hierarchy Check**: Evaluate information density to ensure primary calls-to-action (CTAs) are visually dominant and glanceable.
- **Empty State & Edge Case Auditing**: Verify that screens incorporate purposeful empty states (e.g., "No active team requests yet—create one!"), loading skeletons, and network error dialogs.
- **Responsive Layout Inspection**: Ensure layouts adapt smoothly between standard mobile phone aspect ratios (iPhone 15 Pro, Pixel 8, Samsung Galaxy).

---

## 3. Design System Token Auditing

- **Semantic Color Mapping**: Validate that background fills, surface layers, and action buttons adhere to GeekHaven semantic tokens (`surface-primary`, `accent-geek`, `status-success`).
- **Typography & Font Weight Consistency**: Check that headers, body copy, and metadata use appropriate font weights (Bold, SemiBold, Regular) and line heights to maintain legibility.
- **Elevation & Corner Radius Synchronization**: Ensure card elements and dialogs utilize consistent corner radii ($12-16\text{pt}$) and soft elevation drop-shadow tokens.

---

## 4. High-Fidelity Prototype Flow Verification

- **Micro-Interaction Inspection**: Review interactive prototype connections in Figma to ensure tab switches, sheet presentations, and card expansions feel fluid.
- **Transition Animation Auditing**: Validate that screen transitions use realistic mobile gestures (e.g., push from right, pull down to dismiss) with standard durations ($250-350\text{ms}$).
- **Accessibility Benchmark Verification**: Confirm that all text elements satisfy WCAG 2.1 AA contrast requirements ($\ge 4.5:1$) and touch targets measure $\ge 44\text{pt}$.

---

## 5. Developer Handoff Specification Packaging

- **Handoff Specification Dossier**: Generate clean developer handoff documents detailing:
  - Exact frame dimensions and padding values
  - CSS/Tailwind/Flutter token variable mappings
  - SVG asset export manifests for icons and illustrations
  - State machine transition tables for engineering implementation
- **Audit Logging**: Commit design review dossiers to project tracking records with timestamped compliance signatures.
