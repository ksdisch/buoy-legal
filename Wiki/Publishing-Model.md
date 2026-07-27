# Publishing Model

## Purpose
Documents how Buoy's legal pages are actually structured, served, and cross-linked in the published site — detail that lives in the HTML files themselves and is not captured in PROJECT.md, README.md, or Decisions.md.

## Key understanding

### Site structure

**Fact** (source: `index.html`, `privacy-policy/index.html`, `terms-of-service/index.html`): The published site consists of exactly three `index.html` files, one per directory level:

| URL path | File | Page title |
|---|---|---|
| `/` | `index.html` | "Buoy — Legal" |
| `/privacy-policy/` | `privacy-policy/index.html` | "Privacy Policy — Buoy" |
| `/terms-of-service/` | `terms-of-service/index.html` | "Terms of Service — Buoy" |

**Fact** (source: `index.html`): The root landing page links to both sub-pages and states the contact email. It is the entry point app-store reviewers and linked URLs would reach if pointed at the root (`https://ksdisch.github.io/buoy-legal/`).

**Decision D2** (source: `Decisions.md`): The site is served by GitHub Pages from the `main` branch as a plain static export with `.nojekyll` — no build system, no framework, no Jekyll processing.

### Cross-linking within the site

**Fact** (source: `privacy-policy/index.html` footer, `terms-of-service/index.html` footer): Each sub-page footer contains a `<nav>` that links back to "Legal home" (`../`) and to the sibling document. The privacy policy links to the terms of service; the terms of service links to the privacy policy.

**Fact** (source: `terms-of-service/index.html` §1, §3, §7): The terms of service links to the privacy policy in-text at three points — the acceptance clause (§1), the account deletion section (§3), and the location/notifications section (§7). This creates a dependency: the terms refer users to the privacy policy for data-handling specifics.

### External dependencies at render time

**Fact** (source: all three `index.html` files): All three pages are self-contained HTML with inline CSS. There are no external CSS frameworks, no JavaScript libraries, no CDN dependencies, no analytics scripts, and no external fonts loaded. The only external network calls at page load are OpenStreetMap tile requests — and those only occur when the app is running, not on these static pages.

### Canonical URLs

**Fact** (source: `README.md`):
- Privacy Policy: `https://ksdisch.github.io/buoy-legal/privacy-policy/`
- Terms of Service: `https://ksdisch.github.io/buoy-legal/terms-of-service/`

**Inference** (rests on GitHub Pages behavior for `index.html` files): Both URLs resolve to their respective `index.html` without needing explicit routing; GitHub Pages serves `index.html` automatically for directory paths.

### Update path

**Decision D1** (source: `Decisions.md`): Legal content must never be edited directly in this repo. The source of truth is `DogHood/docs/legal/*.md`; changes are made there and re-rendered here.

**Fact** (source: `PROJECT.md`): The re-render workflow is: edit in `~/Projects/DogHood/docs/legal/`, re-render the corresponding `index.html`, and republish to this repo. No build tooling automates this — it is a manual step.

### What must stay in sync on update

**Inference** (rests on the cross-linking structure and effective dates): When either document is updated, the following must be kept in lockstep:
1. The `index.html` content for the changed document
2. The `<title>` and `<meta name="description">` tags if the document scope changes
3. The "Effective date" visible at the top of both affected pages
4. The upstream `status: draft` front matter in `DogHood/docs/legal/` (currently unresolved — see Uncertainties)

## Sources
- [index.html](../index.html)
- [privacy-policy/index.html](../privacy-policy/index.html)
- [terms-of-service/index.html](../terms-of-service/index.html)
- [Decisions.md](../Decisions.md)

## Uncertainties & contradictions
- **Unresolved:** Whether the stable published URLs (`https://ksdisch.github.io/buoy-legal/privacy-policy/`, `/terms-of-service/`) are currently referenced in any app-store listing or in-app link within the DogHood repo is not confirmed from this repo alone.
- **Unresolved:** The upstream source docs carry `status: draft` while the rendered copies are live and effective as of 2026-07-11. Whether the draft status has been lifted upstream is unknown.

## Related pages
- [History](History.md)
- [Document-Inventory-And-Obligations](Document-Inventory-And-Obligations.md)

## Relevance to current work
This repo is maintenance-mode. When a re-render is needed (the next likely action per PROJECT.md), this page identifies which files to touch, what must stay in sync, and what the canonical URLs are — so the re-render doesn't inadvertently break cross-links or drift effective dates.

_Last reviewed: 2026-07-26_
