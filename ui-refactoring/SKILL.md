---
name: ui-refactoring
description: Refactor existing UI code to align implementation with design context while preserving delivery safety. Use when requests involve Figma-to-code alignment, design-token consistency, style-system conformance, component cleanup, layout/spacing corrections, or UI structure simplification without defaulting to framework-specific patterns. Trigger on prompts about matching mockups, harmonizing design and code, reducing UI inconsistency, or improving maintainability of frontend presentation layers.
---

# UI Refactoring

## Overview

Use this skill to turn design deltas into safe, explicit UI refactor plans and edits. Keep guidance framework-neutral and integrate design context through the `figma` skill when Figma artifacts are part of the request.

## Workflow

1. Gather context first.
   - Inspect existing UI code structure, component boundaries, and styling strategy before proposing changes.
   - Collect design artifacts: Figma URL/node IDs, screenshots, design-token docs, and acceptance notes.
   - If provided, incorporate external source notes (including PDF summaries) as optional context. Do not block execution if they are unavailable.
2. Ask for polish mode before proposing edits.
   - Use this exact gate question: "Choose polish mode: strict behavior-preserving refactor, minor visual polish, or broader redesign."
   - Do not continue into edit proposals until the mode is explicit.
3. Map design deltas to code deltas.
   - Translate differences into concrete edit groups: structure, tokens, spacing, typography, states, and interaction details.
   - Keep changes scoped to the selected polish mode.
   - Keep outputs framework-neutral unless the user asks for framework-specific implementation.
4. Execute with verification after each edit group.
   - Apply small, reviewable changes.
   - Re-check visual and behavioral expectations against selected mode after each group.
   - Track unresolved gaps and call them out immediately.
5. Close with explicit validation.
   - Summarize what now matches design context.
   - List any remaining mismatches, unknowns, or blocked dependencies.
   - Provide next safe step for unresolved items.

## Figma Integration

- Use `figma` skill workflows for design context retrieval, node-level extraction, and design-token interpretation.
- Keep this skill focused on refactoring decisions and execution strategy. Avoid duplicating `figma` operational details here.

## Safety Rules

- Never assume redesign permission when mode is strict.
- Separate behavior changes from style/structure changes unless the selected mode explicitly allows it.
- Preserve accessibility baselines during all modes unless the user directs otherwise.
- Escalate quickly when design artifacts are incomplete, conflicting, or stale.

## When to Load References

- Load [references/design-sync-checklist.md](references/design-sync-checklist.md) for concrete UI alignment checks.
- Load [references/polish-mode-contract.md](references/polish-mode-contract.md) to enforce strict mode boundaries.
- Load [references/figma-alignment-workflow.md](references/figma-alignment-workflow.md) when working from Figma artifacts.
