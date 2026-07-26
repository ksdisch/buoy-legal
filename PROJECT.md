# PROJECT.md

## Purpose
Publish the rendered legal documents (privacy policy + terms of service) for **Buoy** — a hyperlocal, real-time dog-park coordination app — as a static GitHub Pages site, so the app has stable public URLs for its legal pages.

## Scope
**IN scope:** Hosting rendered, static copies of Buoy's legal documents at
`https://ksdisch.github.io/buoy-legal/` (landing page + `/privacy-policy/` + `/terms-of-service/`), and re-rendering them when the upstream source changes.

**OUT of scope / never:** Authoring or editing legal content in this repo. The source of truth lives in the app repo (`DogHood`, `docs/legal/*.md`) — edit there and re-render here (Fact: stated in this repo's README). No build system, no app code, no analytics.

## Current status
Active (low-touch / maintenance). Legal documents effective 2026-07-11 are published and live; the site is a plain static export with `.nojekyll` (no Jekyll processing). Repo has two substantive commits: the initial publish and vendored Claude tooling.

## Next actions
1. When `~/Projects/DogHood/docs/legal/privacy-policy.md` or `terms-of-service.md` changes, re-render the corresponding `index.html` here and republish.
2. Resolve the draft-vs-published question (see HANDOFF.md open questions): upstream source docs still carry `status: draft` front matter while the rendered copies are live.

## Boundaries
- Static HTML only, served by GitHub Pages from `main`; no framework, no build step.
- Content changes must originate upstream in `DogHood/docs/legal/` — never edited directly here (Decision D1).
- Contact address for legal questions: buoy.dogparks@gmail.com.
