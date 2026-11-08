# Component-inventory research record

## Overview and status

- **Project:** Robot Royale meltybrain.
- **Objective:** Identify the parts and functions involved before selecting hardware.
- **Status:** Research document prepared; component selection, design, assembly and hardware validation remain unfinished.
- **Scope change:** The user replaced the purchasing/BOM request with a generic inventory. Product choices, prices, suppliers, a selected class and a cost/weight budget are excluded from this deliverable.

## Requirements and evidence

- Provide a compact grouped checklist, six fields for each detailed component role, power/signal connection diagrams and sources.
- Cover onboard electronics, heading methods, indication, radio/failsafe/telemetry, drive, power, structure, wiring/retention, rule-dependent equipment, workshop tools and the optional overhead-camera branch.
- Classify required functions, common components and optional/conditional branches. Integrated roles are not separate purchase quantities.
- Use original projects, construction notes, builder accounts, experiments, technical references and organizer rules. Label engineering interpretation **(reasoning)**.
- Keep research and its summary in `research/parts/`; preserve the existing project/firmware survey in `research/code/`.

## Research stage — 8 November 2026

- **Attempted:** Trace real melty components and failure reports, then decompose them into a component inventory.
- **Changed:** Replaced the initial product-research direction with the user's updated scope. Separated physical parts, integrated functions, off-robot equipment and optional external correction equipment.
- **Result:** `meltybrain-component-inventory.md` contains 141 component/function entries, each with six fields, 67 distinct evidence links, and three connection diagrams. `README.md` contains the compact checklist and navigation.
- **Design implications (reasoning):** A high-range accelerometer is one sensing branch; external references and other rate/heading methods change the parts needed. Motor command timing, mechanical response and traction are separate stages. Retention, mounting geometry and common electrical references affect the whole system.
- **Remaining issues:** No assembled architecture, numerical specifications, pinout, rule approval or physical performance has been established.
- **Next stage:** Component selection and architecture decisions can be recorded separately when requested. This record does not make those decisions.

## Validation status

- **Confirmed by document inspection:** Six-field entry structure, explicit reasoning/evidence distinctions, classification legend, source links, included power/common-return diagram and separate signal/camera diagrams.
- **Reviewed:** An independent document review identified an ambiguous camera-radio classification; it was corrected to require the receiving/interface function within the selected wireless-camera branch.
- **Unresolved:** Actual sensor accuracy, drift, response, fail-safe stopping, containment adequacy, electrical compatibility, mass, thermal behavior, retention and impact survival.
- **Not performed:** Hardware tests, firmware compilation, CAD validation, camera experiments or rule inspection of a built robot.

## Assets

- [Full component inventory](meltybrain-component-inventory.md).
- [Checklist and navigation](README.md).
- [Related project/firmware survey](../code/meltybrain-project-survey.md).

Source-specific evidence links are retained in the inventory. No source code, circuit, CAD model or completed robot was created as part of this research stage.
