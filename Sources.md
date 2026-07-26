# Sources

| Source | Location | Type | Authoritative for |
|--------|----------|------|-------------------|
| Buoy privacy policy (source) | `~/Projects/DogHood/docs/legal/privacy-policy.md` | spec (markdown, front-matter `status: draft`, last_updated 2026-07-11) | The legal content rendered at `privacy-policy/index.html` |
| Buoy terms of service (source) | `~/Projects/DogHood/docs/legal/terms-of-service.md` | spec (markdown, front-matter `status: draft`, last_updated 2026-07-11) | The legal content rendered at `terms-of-service/index.html` |
| README.md | `README.md` | brief | Repo intent: rendered copies only; source of truth in the app repo; do-not-edit-here rule |
| Published site | <https://ksdisch.github.io/buoy-legal/> (+ `/privacy-policy/`, `/terms-of-service/`) | export (rendered HTML) | What users and app-store reviewers actually see |

Notes:
- **Fact:** README states the source of truth is the app repo's `docs/legal/*.md`.
- **Inference:** That app repo is `~/Projects/DogHood` — it is the only local repo with `docs/legal/`, and its legal docs are tagged `buoy` in their front matter.
