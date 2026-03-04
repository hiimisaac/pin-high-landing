# Topbar Center Alignment Spec

Status: Approved
Date: 2026-03-03
Owner: Codex

## Problem Statement
The hero top navigation appears visually off-center on desktop because the nav links are centered in leftover space between asymmetric left and right controls, not the true hero midpoint.

## In Scope
- Desktop alignment fix for hero topbar so primary nav links are centered relative to the full hero width.
- Preserve current mobile behavior and content.

## Out of Scope
- Copy changes.
- New sections/components.
- Any redesign outside topbar alignment rules.

## Constraints
- CSS-only change (no new dependencies).
- Keep existing Svelte structure intact.
- Do not regress small-screen layout.

## Acceptance Criteria
1. At desktop widths (>= 860px), the nav link group is centered on the topbar midpoint, independent of brand/button width mismatch.
2. Brand remains left-aligned and Download button remains right-aligned.
3. Mobile layout behavior remains unchanged.
4. Build succeeds.

## File Impact Plan
- `.agentic/specs/active/2026-03-03-topbar-center-alignment.md`
- `src/app.css`

## Test Plan
- Run `npm run build`.
- Manual visual check:
  - Desktop (~1440px): topbar nav appears truly centered.
  - Mobile (~390px): topbar still wraps/flows as before.

## Risks
- Centering adjustment might affect spacing at intermediate widths near breakpoint.

## Verification Evidence
- AC1 (desktop nav truly centered): Updated desktop topbar grid to `minmax(0, 1fr) auto minmax(0, 1fr)` so center nav uses balanced side tracks in `src/app.css`.
- AC2 (brand/button edge alignment): Added desktop `justify-self` rules for `.topbar .brand` (start) and `.topbar .chip-btn` (end) in `src/app.css`.
- AC3 (mobile unchanged): Alignment rules were scoped to `@media (min-width: 860px)` only, leaving base/mobile topbar behavior intact.
- AC4 (build succeeds): `npm run build` passed on 2026-03-03. Existing `href="#"` a11y warnings remain expected placeholders.

### UI State-Matrix Verification
- Touched segment: Hero topbar (`brand`, `primary nav`, `download CTA`).
- Role-visible paths touched: Public landing page only.
- Loading state: N/A (static section, no async data).
- Empty state: N/A (no conditional content source).
- Error state: N/A (no runtime fetch path in touched scope).
- Data/default state: Verified via build output and CSS inspection for desktop breakpoint behavior.
