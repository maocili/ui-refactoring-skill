# Polish Mode Contract

Apply this contract before proposing edits. Ask the user to choose one mode first.

Required gate question:
"Choose polish mode: strict behavior-preserving refactor, minor visual polish, or broader redesign."

## Strict Behavior-Preserving Refactor

Intent:
- Improve maintainability and design alignment without changing user-visible behavior.

Allowed:
- Refactor component structure for clarity.
- Normalize tokens and styling implementation when output is visually and behaviorally equivalent.
- Remove duplication and clarify naming in UI code.

Not allowed:
- Intentional layout shifts that alter UX flow.
- Interaction changes (timing, state logic, navigation paths).
- New visual treatments that were not present in existing design intent.

Required verification:
- Confirm no behavior regressions.
- Confirm visual output remains equivalent except for bug fixes explicitly requested by user.

## Minor Visual Polish

Intent:
- Preserve core behavior while allowing low-risk visual consistency improvements.

Allowed:
- Small spacing/typography consistency fixes.
- Token normalization that slightly improves visual cohesion.
- Minor state styling improvements (focus/hover/disabled) that do not change product logic.

Not allowed:
- Re-architecting flows, page IA, or major layout patterns.
- Behavior changes requiring product sign-off unless explicitly requested.

Required verification:
- Identify each polish change and justify low-risk scope.
- Confirm no core flow disruption.

## Broader Redesign

Intent:
- Permit structural and visual changes to better match a new or significantly changed design direction.

Allowed:
- Layout hierarchy changes.
- Component variant redesigns.
- Intentional interaction refinements tied to updated design context.

Required constraints:
- Declare intended behavior changes before implementation.
- Keep a traceable mapping from design deltas to code edits.
- Call out migration risks and staged rollout considerations when relevant.

## Escalation Rules

- Pause and ask for clarification when artifacts conflict (for example, Figma vs screenshots).
- Pause when requested mode and requested edits conflict (for example, strict mode plus redesign requests).
- State what is blocked, what can proceed safely, and what decision is needed.
