# Footer Navigation Alignment Spec

Status: Approved
Date: 2026-03-03
Owner: Codex

## Problem Statement
The footer navigation links (`Home`, `Features`, `How it works`, `Download`) are visually out of place relative to the `PIN HIGH` brand block on desktop layouts, creating an unbalanced footer composition.

## In Scope
- Correct footer navigation positioning and spacing in the existing footer layout.
- Preserve existing footer content and link destinations.
- Maintain responsive behavior across mobile and desktop.

## Out of Scope
- Copy/content changes in footer.
- Redesign of footer structure or legal links.
- Changes to non-footer sections.

## Constraints
- CSS-only change unless a markup change is required.
- No new dependencies.
- Keep current visual system intact.

## Acceptance Criteria
1. Footer nav links are consistently aligned in desktop layout and no longer appear misplaced beside the brand block.
2. Footer nav links have intentional spacing between items.
3. Footer layout remains readable and non-overlapping on mobile.
4. Build succeeds.

## File Impact Plan
- `.agentic/specs/active/2026-03-03-footer-nav-alignment.md`
- `src/app.css`

## Test Plan
- Run `npm run build`.
- Manual visual verification of footer at desktop width and mobile width.

## Risks
- Small spacing changes could alter perceived balance with legal links; tune conservatively.

## Verification Evidence
- AC1 (desktop alignment): Added `.footer nav { display: flex; ... }` in `src/app.css`, which makes the existing desktop rule `.footer nav { justify-content: flex-end; }` apply as intended.
- AC2 (intentional item spacing): Added `gap: 14px` to `.footer nav` in `src/app.css` so footer links have consistent spacing.
- AC3 (mobile readability): Kept footer in stacked grid mode on mobile and added `flex-wrap: wrap` on `.footer nav` so links can wrap without overlap.
- AC4 (build): `npm run build` succeeded on 2026-03-03 (existing expected Svelte a11y warnings for placeholder `href=\"#\"` links only).
