# HANDOFF.md

_Last updated: 2026-07-26_

## What was just done
- Initialized the project wiki (PROJECT.md, HANDOFF.md, Sources.md, Decisions.md) and wired the Project Wiki section into CLAUDE.md.
- Prior work: legal documents (privacy policy + terms of service, effective 2026-07-11) published via GitHub Pages (commit 7ae1953); global Claude tooling vendored via /claudify-repo (commit 14e515d, PR #1).

## Where things stand
The site is live and stable: a landing page plus rendered privacy-policy and terms-of-service pages at https://ksdisch.github.io/buoy-legal/. This repo holds static copies only — the authoritative markdown lives in the DogHood app repo at `docs/legal/`. Nothing is in flight; this is a maintenance-mode repo that only changes when the upstream legal docs change.

## Immediate next move
Nothing required. The next real work is a re-render whenever `DogHood/docs/legal/privacy-policy.md` or `terms-of-service.md` is updated — keep the effective dates and content in lockstep with upstream.

## Open questions / blockers
- **Unresolved:** The upstream source docs in DogHood (`docs/legal/privacy-policy.md`, `terms-of-service.md`) carry `status: draft` in their front matter (last_updated 2026-07-11) even though the rendered copies here are published and live. Confirm whether the published copies match the final upstream text and whether the draft status should be lifted upstream.

## Files touched recently
- `PROJECT.md`, `HANDOFF.md`, `Sources.md`, `Decisions.md` — wiki initialization (2026-07-26)
- `CLAUDE.md` — appended Project Wiki section (2026-07-26)
- `privacy-policy/index.html`, `terms-of-service/index.html`, `index.html` — the published site (initial publish, 2026-07-11)
