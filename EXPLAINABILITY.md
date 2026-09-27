# EXPLAINABILITY.md

This document explains the internal mechanisms, data lineage, operational boundaries, and governance framework of **AppCosmos Agent** (`appcosmos-agent`) in accordance with the **OpenGAP v0.1.0** specification for the **HiDevs GitAgent Passport** clearance pipeline.

> **Agent Name:** AppCosmos Agent (`appcosmos-agent`)  
> **Specification:** OpenGAP v0.1.0  
> **Category / Domain:** Education / Mobile UI/UX Design Systems & Product Prototyping  
> **Compliance Standard:** OpenGAP Checkpoint 2 (Explainability & Decision Governance), FERPA, GDPR  

---

## How the Agent Decides

AppCosmos Agent is an autonomous mobile app UX/UI design system orchestration, user flow verification, high-fidelity prototyping, and screen architecture agent designed for **AppCosmos** (the official GeekHaven mobile application). The agent coordinates mobile screen design guidelines, information architecture, navigation state machines, component token consistency, and student collaboration review workflows.

### 1. Decision Architecture

The mobile screen review, user journey validation, and developer handoff pipeline operates across a deterministic, five-stage architecture:

```
Contributor Action (Submit Screen Flow / Propose New Module / Update Design System Tokens)
    │
    ▼
[Stage 1: User Journey Mapping & Scope Verification]
    │  - Evaluates user flow from entry point to primary conversion action
    │  - Confirms feature aligns with GeekHaven module taxonomy (Community, Events, Mentorship)
    │  - Flags navigation dead ends and missing exit/back paths
    ▼
[Stage 2: Ergonomic & Touch-Zone Layout Auditing]
    │  - Evaluates interactive elements against the 44x44pt minimum touch target rule
    │  - Checks primary action placement within the natural bottom-screen thumb zone
    │  - Audits spacing consistency against standard 4pt/8pt spatial grid systems
    ▼
[Stage 3: GeekHaven Design Token Conformance Inspection]
    │  - Validates semantic color variable usage across light/dark surfaces
    │  - Verifies typography styles match Display, Title, Body, and Caption scales
    │  - Checks component reusability: enforces master library instance linkage
    ▼
[Stage 4: Accessibility & WCAG Contrast Evaluation]
    │  - Computes foreground-to-background color contrast ratios
    │  - Enforces WCAG 2.1 AA compliance: text contrast $\ge 4.5:1$ (headings $\ge 3.0:1$)
    │  - Validates icon clarity and interactive state affordances
    ▼
[Stage 5: Handoff Specification Packaging & Review Synthesis]
    │  - Computes composite Mobile UX Quality Score ($Q_{\text{ux}} \in [0, 100]$)
    │  - Assembles structured developer handoff specifications (dimensions, tokens, SVGs)
    │  - Generates actionable review feedback for student designers and design leads
    ▼
Validated Mobile Screen Design Merged into GeekHaven App Prototype Repository
```

### 2. Usability Scoring & UX Rubric Formulations

AppCosmos evaluates screen designs and user flows using a mathematically deterministic scoring formula:

1. **Composite Mobile UX Score ($Q_{\text{ux}}$)**:
   $$Q_{\text{ux}} = (w_f \cdot F_{\text{flow}}) + (w_t \cdot T_{\text{touch}}) + (w_c \cdot C_{\text{contrast}}) + (w_s \cdot S_{\text{system}})$$
   where:
   - $F_{\text{flow}} \in [0, 100]$: User flow navigation continuity (penalizing dead-end screens or orphaned modal takeovers).
   - $T_{\text{touch}} \in [0, 100]$: Ergonomic touch target compliance (percentage of interactive controls $\ge 44\times 44\text{pt}$).
   - $C_{\text{contrast}} \in [0, 100]$: WCAG 2.1 AA color contrast compliance ratio ($\ge 4.5:1$).
   - $S_{\text{system}} \in [0, 100]$: Design system token adoption (percentage of linked library styles vs hardcoded hex/font sizes).
   - Weights: $w_f = 0.30, w_t = 0.25, w_c = 0.25, w_s = 0.20$ ($\sum w_i = 1.0$).

2. **Heuristic Laws of UX Validation Rubric**:
   - **Fitts's Law**: Critical actions (e.g., "Join Team", "Submit Feedback") must reside near screen bottoms with ample target width.
   - **Hick's Law**: Decision choices per screen are minimized; lists exceeding 7 options require categorization or search filters.
   - **Miller's Law**: Information chunks are restricted to $7 \pm 2$ cognitive clusters per viewport.

### 3. Thresholding & Refusal Decision Criteria

AppCosmos Agent deterministically enforces quality boundaries:
- **Refusal on Navigation Deadlock**: Any screen or modal sheet lacking an accessible dismiss, cancel, or back navigation path is rejected with code `ERR_NAVIGATION_DEADLOCK`.
- **Refusal on Inaccessible Touch Target**: Core interactive buttons measuring below $36\text{pt}$ in width or height are rejected with code `ERR_INACCESSIBLE_TOUCH_TARGET`.
- **Refusal on Severe Contrast Failure**: Text elements failing minimum WCAG contrast standards ($<3.0:1$) trigger an automatic revision notice (`ERR_FAILS_WCAG_CONTRAST`).
- **Refusal on Real Student Data in Mockups**: Mockups displaying actual student phone numbers, email addresses, or roll numbers are rejected to enforce privacy (`ERR_REAL_PII_IN_MOCKUP`).

### 4. Fallback Decision Mechanism

AppCosmos Agent maintains operational continuity through multi-tier fallback mechanisms:
- **Static Token Map Fallback**: If live Figma design token sync APIs are unavailable, the agent cross-references screens against local static token definitions in `assets/tokens.json`.
- **Pre-Authored Screen Templates**: If generative screen layout advice encounters rate limits, the system provides standard pre-approved wireframe templates for common mobile patterns (List-Detail, Form, Leaderboard).
- **Model Fallback Cascade**: High-level UX review and heuristic critique default to `gemini-2.0-flash` with automatic failover to `gpt-4o` and `claude-3-5-sonnet`.

### 5. Human-in-the-Loop Governance

AppCosmos maintains human design lead stewardship:
- **Lead Designer Final Review**: Automated validation scores technical ergonomics and accessibility, but subjective visual polish and brand identity decisions are reviewed by GeekHaven design leads.
- **Student Usability Testing Feedback**: Contributor proposals are validated against empirical feedback from student testers across different smartphone screen sizes.
- **Collaborative Mentorship**: Automated review comments are formulated to educate student contributors on mobile product design best practices.

---

## The Data It Uses

AppCosmos Agent operates under strict privacy and open-source educational standards.

### 1. Ingested Input Data

The agent processes only mobile UI/UX deliverables and design system assets:
- **Screen Layout Hierarchies**: Frame dimensions, layer arrangements, Auto-Layout constraints, and typography definitions.
- **User Flow Diagrams**: FigJam node trees, state transition arrows, and decision branch logic.
- **Prototype Interaction Connections**: Figma interaction noodles, triggers, and transition animation curves.
- **Contributor Documentation**: Design rationale notes, component descriptions, and issue pull request metadata.

### 2. Configuration & Reference Data

- **GeekHaven Mobile Design System**: Official color palette tokens, typography scales, corner radii, and elevation shadow levels.
- **Laws of UX & Human Interface Guidelines**: Authoritative ergonomic standards (Apple HIG and Google Material Design 3).
- **WCAG 2.1 AA Accessibility Standards**: Standard luminance contrast formulas and visual accessibility thresholds.

### 3. Base Model & Inference Lineage

- **Deterministic Geometry & Contrast Linters**: Touch target calculations, contrast ratio mathematics, and navigation state machine traversals are executed by deterministic rule-based algorithms.
- **AI UX Review Copilot**: Frontier foundation models (`gemini-2.0-flash`, `gpt-4o`, `claude-3-5-sonnet`) utilized for design critique, user persona analysis, and handoff documentation generation.
- **Zero Training on Contributor Designs**: Student wireframes, original UI layouts, and society graphics are never used to train commercial foundation models.

### 4. Data Privacy, Storage, and Retention

- **FERPA & GDPR Compliance**: Student contributor identities, commit histories, and personal information are protected under educational privacy standards.
- **Zero Telemetry Collection**: The repository does not include analytics trackers, advertising beacons, or telemetry collectors.
- **Local Project Sandboxing**: All design evaluations and specification checks occur strictly within the repository boundary.

---

## Limitations

Understanding the operational boundaries and technical constraints of AppCosmos Agent is essential for effective mobile design collaboration.

### 1. Cloud Figma/FigJam Canvas Sync Boundaries
- **Limitation**: Real-time canvas edits in cloud Figma/FigJam files cannot be inspected continuously without authenticated API tokens and webhooks.
- **Mitigation**: The agent inspects exported frame assets, component manifests, and version-tagged Figma URL snapshots submitted in pull requests.

### 2. Subjective Visual Delight vs Heuristic Usability
- **Limitation**: While mathematical contrast and touch target sizes are verifiable, emotional delight, brand prestige, and aesthetic elegance cannot be measured strictly by algorithmic equations.
- **Mitigation**: Algorithmic scoring evaluates objective ergonomics and accessibility, reserving aesthetic nuance for human design lead review.

### 3. Multi-Screen Navigation State Explosions
- **Limitation**: In complex mobile applications with conditional authentication, push notifications, and deep linking, the total combinatorial space of screen states can become immense.
- **Mitigation**: The agent evaluates user journeys modularly by society domain (Onboarding, Community, Leaderboard, Team Finder) rather than as a monolithic state machine.

### 4. Platform Divergence (iOS HIG vs Android Material Design)
- **Limitation**: iOS and Android enforce subtly different navigation conventions (e.g., bottom swipe bar vs system back button, navigation bar title alignment).
- **Mitigation**: The design system adopts universal mobile design patterns that translate cleanly across both Flutter and React Native cross-platform implementations.

### 5. Automated Critique vs Live User Usability Testing
- **Limitation**: Static screen analysis cannot fully predict real-world user confusion or physical ergonomics across varying hand sizes.
- **Mitigation**: The agent encourages student designers to conduct live hallway usability testing with fellow campus peers before finalizing high-fidelity flows.

---

## Summary & Compliance Checklist

| Checkpoint 2 Requirement | Corresponding Section | Status |
| :--- | :--- | :---: |
| **How the agent decides** | [How the Agent Decides](#how-the-agent-decides) | **Covered** |
| - Decision architecture & 5-stage pipeline | Section 1 | Verified |
| - Mobile UX scoring & Laws of UX rubrics | Section 2 | Verified |
| - Thresholding, touch target & refusal criteria | Section 3 | Verified |
| - Fallback decision mechanism & static tokens | Section 4 | Verified |
| - Human-in-the-loop & lead designer governance | Section 5 | Verified |
| **The data it uses** | [The Data It Uses](#the-data-it-uses) | **Covered** |
| - Ingested screen layouts, user flows & prototypes | Section 1 | Verified |
| - Configuration, GeekHaven tokens & HIG baselines | Section 2 | Verified |
| - Base model lineage & deterministic linters | Section 3 | Verified |
| - Data privacy, zero telemetry & FERPA/GDPR | Section 4 | Verified |
| **Its limitations** | [Limitations](#limitations) | **Covered** |
| - Cloud Figma/FigJam canvas sync boundaries | Section 1 | Verified |
| - Subjective visual delight vs heuristic usability | Section 2 | Verified |
| - Multi-screen navigation state explosions | Section 3 | Verified |
| - Platform divergence between iOS and Android | Section 4 | Verified |
| - Automated critique vs live user usability testing | Section 5 | Verified |
