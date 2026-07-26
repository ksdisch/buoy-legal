# Decisions

| ID | Decision | Status | Date | Source/Rationale |
|----|----------|--------|------|-----------------|
| D1 | Legal content source of truth lives in the app repo (`DogHood/docs/legal/*.md`); this repo holds rendered static copies only and must never be edited directly — edit upstream and re-render. | Approved | 2026-07-11 | Stated explicitly in README.md |
| D2 | Publish as a plain static site on GitHub Pages (main branch) with `.nojekyll` — no build system, no framework. | Approved | 2026-07-11 | Inference from repo structure and initial publish commit 7ae1953 |
