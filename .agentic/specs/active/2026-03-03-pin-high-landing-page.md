# Pin High Landing Page Spec

Status: Approved
Date: 2026-03-03
Owner: Codex

## Problem Statement
The landing page must feel intentionally designed, cohesive, and visually compelling while clearly explaining Pin High and driving prelaunch download intent.

## In Scope
- Full from-scratch redesign in a cohesive visual language inspired by high-polish mobile app landing pages.
- End-to-end section rhythm and component consistency.
- Core narrative:
  1. Hero
  2. Value/features
  3. How-it-works
  4. Story/supporting visuals
  5. Social proof
  6. Final download CTA + footer utilities
- App Store / Google Play links remain placeholders (`#`).
- Add directly accessible legal pages for Privacy Policy and Terms & Conditions.

## Out of Scope
- Backend/API integrations.
- Real store URL integration.
- Multi-page marketing IA.

## Constraints
- Keep Svelte + Vite.
- Preserve truthfulness of feature claims.
- No new runtime dependencies.

## Acceptance Criteria
1. One cohesive visual system is used across the page (type, spacing, color, component shape, motion).
2. Landing page feels intentionally art-directed and non-boilerplate.
3. CTA hierarchy is clear and repeated in hero + final download section.
4. Messaging clearly communicates what Pin High is and how it works.
5. Responsive behavior remains solid at 390px and 1440px.
6. Build succeeds.

## File Impact Plan
- `.agentic/specs/active/2026-03-03-pin-high-landing-page.md`
- `src/App.svelte`
- `src/app.css`
- `privacy-policy.html`
- `terms-and-conditions.html`

## Test Plan
- Run `npm run build`.
- Manual QA on 390px and 1440px for:
  - visual cohesion,
  - spacing/hierarchy,
  - CTA prominence,
  - readability,
  - no overlap/clipping.

## Risks
- Placeholder `#` links trigger expected Svelte a11y warnings.
- CSS-only mock visuals stand in for production brand imagery.

## Verification Evidence
- AC1 (cohesive system): Implemented unified style system in `src/app.css` with shared tokens, consistent component radii, button family, and section rhythm.
- AC2 (intentional art direction): Implemented near-1:1 inspired composition in `src/App.svelte` + `src/app.css` (framed shell, hero grid, floating feature cards, modular sections, bright accent system).
- AC3 (CTA hierarchy): Hero and final download section include App Store + Google Play links in `src/App.svelte`.
- AC4 (clear product message): Copy centers playability score, best tee window, and crew alignment across hero/features/steps.
- AC5 (responsive behavior): Mobile-first CSS plus desktop scaling in `@media (min-width: 860px)`.
- AC6 (build): `npm run build` succeeded on 2026-03-03; assets emitted to `dist/`.
  - Expected warnings remain for `href="#"` placeholders.
