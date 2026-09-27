# RULES.md - AppCosmos Operational Constraints & Guardrails

> **Specification:** OpenGAP Spec 0.1.0  
> **Agent Name:** AppCosmos Agent (`appcosmos-agent`)  
> **Enforcement Level:** Mandatory & Deterministic  

---

## 1. Mobile Usability & Ergonomic Guardrails

1. **Minimum Touch Target Boundary**: All interactive elements (buttons, icons, list items, chips) must satisfy a minimum touch target area of $44 \times 44\text{pt}$ (iOS Human Interface Guidelines / Android Material Design standards).
2. **Accessible Contrast Ratios**: Text and primary interface graphics must meet or exceed WCAG 2.1 AA contrast requirements ($\ge 4.5:1$ for normal body text, $\ge 3.0:1$ for large headings).
3. **No Navigation Traps**: Every modal sheet, full-screen takeover, or deep screen flow must include an accessible dismiss action (e.g., standard back arrow, close 'X' button, or swipe-down gesture).

---

## 2. GeekHaven Design System Adherence

1. **Brand Palette Conformance**: Screen designs must utilize the official GeekHaven brand tokens and dark/light mode semantic color variables.
2. **Typography Scale Strictness**: Arbitrary font sizes are prohibited; text layers must map to the defined typographic scale (Display: 32pt, Title: 24pt, Body: 16pt, Caption: 12pt).
3. **Component Reusability**: Common interface elements (App Bars, Bottom Navigation Bars, Cards, Modals) must utilize master library component instances rather than detached ad-hoc frames.

---

## 3. Data Governance & Student Privacy Standards

1. **FERPA & GDPR Compliance**: Contributor portfolios, student roll numbers, and personal details must be treated as private educational records.
2. **Mock Data Sanitization**: Prototype screens and user testing mockups must utilize realistic but fictitious placeholder student data (e.g., "Alex Developer", "alex@geekhaven.in") rather than real student credentials.
3. **Zero Telemetry Collection**: AppCosmos design repositories must not embed external commercial telemetry beacons or unauthorized analytics tracking scripts.

---

## 4. Human-in-the-Loop & Lead Designer Governance

1. **Design Lead Sign-Off**: While the agent validates technical ergonomics and contrast mathematically, creative direction and final prototype merges require human design lead review.
2. **User Research Validation**: Major architectural shifts to core navigation (e.g., replacing bottom bar with gesture navigation) must be supported by user research notes or student usability testing findings.
