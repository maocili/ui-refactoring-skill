# Figma Alignment Workflow

Use this workflow when the request includes Figma links, node IDs, mockups, or design-library requirements.

## 1) Gather Design Inputs

- Collect the Figma file key, relevant node IDs, and target states/screens.
- Capture supporting constraints: responsive expectations, accessibility goals, and acceptance notes.
- Identify whether design tokens come from library variables, local styles, or external docs.

## 2) Retrieve Structured Context

- Use the `figma` skill and its recommended tools to extract:
  - Node screenshots for visual truth.
  - Contextual code/design metadata for component structure.
  - Variable definitions for tokens and semantic roles.
- Prefer node-specific extraction over whole-file assumptions.

## 3) Build A Design Delta Map

- Compare current code output against Figma truth by category:
  - Structure and composition.
  - Spacing and sizing.
  - Typography and iconography.
  - State styling and interaction affordances.
- Record each delta as "design intent -> code change candidate".

## 4) Apply Mode-Aware Refactor Strategy

- Load `polish-mode-contract.md` and enforce the selected mode.
- Sequence edits from lowest risk to highest impact.
- Validate each batch against both Figma context and runtime behavior.

## 5) Resolve Ambiguity

- If design sources disagree, stop and request prioritization order (for example, node screenshot over stale handoff note).
- If a required component/token is missing, propose safe fallback and mark it as unresolved.
- Keep unresolved items explicit rather than guessing.

## 6) Report Outcomes

- Report what is fully aligned with Figma.
- Report partial alignment and blockers.
- Report follow-up actions needed from design or product.
