# App Store Support Page Spec

Status: Approved
Date: 2026-03-04
Owner: Codex

## Problem Statement
Pin High needs a dedicated public support page for App Store listing requirements so users (and App Review) can find support contact information quickly.

## In Scope
- Add a new static support page at `/support`.
- Include support contact email: `pin-high@isaacbarham.com`.
- Add Netlify redirects for `/support` <-> `/support.html`, consistent with existing legal routes.
- Add a footer link to the support page from the main landing page.

## Out of Scope
- In-app support flow changes.
- Backend ticketing/chat integration.
- Changes to privacy policy or terms content.

## Constraints
- Match current static legal-page visual style.
- No new dependencies.
- Keep changes limited to the file impact plan.

## Acceptance Criteria
1. Visiting `/support` returns a support page with clear title and support instructions.
2. Page displays clickable email contact `pin-high@isaacbarham.com` using a `mailto:` link.
3. Footer on landing page includes a visible `Support` link to `/support`.
4. Netlify route handling works for both `/support` and `/support.html` forms.
5. Build succeeds.

## File Impact Plan
- `.agentic/specs/active/2026-03-04-app-store-support-page.md`
- `public/support.html`
- `netlify.toml`
- `src/App.svelte`

## Test Plan
- Run `npm run build`.
- Manual check:
  - open `/support` and verify support email link works,
  - verify footer contains `Support`,
  - verify redirect entries exist in Netlify config.

## Risks
- If footer spacing is tight at small widths, adding one extra legal link could wrap differently.

## Verification Evidence
- AC1 (`/support` page exists): Added static page at `public/support.html` with support heading and instructions.
- AC2 (clickable support email): Added `mailto:pin-high@isaacbarham.com` link in `public/support.html`.
- AC3 (footer support link): Added `Support` link to `/support` in `src/App.svelte` footer legal links.
- AC4 (route handling): Added Netlify redirects for `/support` and `/support.html` in `netlify.toml`.
- AC5 (build): `npm run build` succeeded on 2026-03-04.
