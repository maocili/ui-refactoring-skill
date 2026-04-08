# Design Sync Checklist

Use this checklist to convert design intent into concrete, verifiable refactor work.

## 1) Tokens And Variables

- Confirm color, spacing, radius, shadow, and typography values use shared tokens where available.
- Replace hard-coded UI constants with project token references when this is safe for the selected polish mode.
- Confirm semantic token intent (for example, surface/background/text roles) rather than matching raw hex values only.

## 2) Layout And Spacing

- Compare container hierarchy to the design structure before changing internals.
- Validate gap, padding, margin, and alignment relationships at component and page levels.
- Check responsive breakpoints and ensure mode-specific constraints remain intact.

## 3) Typography

- Verify font family, size, line-height, weight, letter spacing, and text transform against design context.
- Confirm heading/body hierarchy remains coherent after refactor.
- Ensure truncation, wrapping, and overflow behavior still support real content.

## 4) Components And States

- Align variants (default, hover, focus, active, disabled, loading, error) with design intent.
- Ensure repeated patterns reuse shared components instead of duplicating markup/styling logic.
- Confirm icon sizing, spacing, and placement consistency inside interactive elements.

## 5) Interaction And Behavior Guardrails

- In strict mode, preserve all user-visible behavior and interaction flows.
- In minor polish mode, limit changes to visual consistency or low-risk interaction quality improvements.
- In redesign mode, document intentional behavior or structure changes before implementation.

## 6) Accessibility And Quality

- Preserve or improve keyboard access, focus visibility, semantic roles, and label relationships.
- Re-check contrast after token or style updates.
- Verify error/help/status messaging remains clear and discoverable.

## 7) Final Verification Output

- List matched items: what now aligns with the design context.
- List unresolved items: what still differs and why.
- List risk notes: what may require product or design sign-off.
