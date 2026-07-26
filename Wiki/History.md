# History — buoy-legal

> How this project got here: a chronological narrative of eras and milestones,
> reconstructed from merged PRs, git history, wrap logs, and ADRs.
> PR numbers, merge dates, tags, and SHAs are **Fact** by construction; rationale
> lines carry explicit labels (**Fact** when quoted from a PR body/ADR, **Inference**
> when reconstructed). Decisions are anchored by ID to the project's decision
> ledger — never restated here. **Append-only:** new milestones are added at the
> bottom (above the Mining coverage footer); existing entries are never rewritten.

## Origin — 2026-07
Created to give **Buoy** (the hyperlocal dog-park coordination app built in the
DogHood repo) stable public URLs for its legal pages — a plain static GitHub Pages
site holding rendered copies of the privacy policy and terms of service. First
commit 7ae1953 on 2026-07-11 was the full initial publish. No kickoff brief exists;
the repo was born as a publishing target, not a project in its own right
[Inference — no brief found in-repo or in `~/Projects/_kickoffs/`].

## Era: Publish & housekeeping (2026-07)
The repo's entire life so far: one substantive publish, then two rounds of repo
housekeeping. By the end of the era the site is live and the repo is in
maintenance mode, changing only when the upstream legal docs change.

### Initial publish — 2026-07-11
- **Landed:** Landing page + rendered privacy policy and terms of service (effective 2026-07-11), `.nojekyll`, README (commit 7ae1953, direct to `main` — pre-dates the branch/PR workflow here)
- **Why:** Stable public URLs for Buoy's legal pages; content authored upstream in `DogHood/docs/legal/*.md` and only rendered here [Fact — README.md] — see D1, D2 in `Decisions.md`

### Claude Code tooling vendored — 2026-07-18
- **Landed:** Fleet-wide `/claudify-repo` sweep: global commands/skills vendored into `.claude/`, CLAUDE.md tooling reference added (PR #1, commit 14e515d)
- **Why:** Make global tooling work in cloud/web sessions and for collaborators [Fact — PR #1 body]

### Project wiki initialized — 2026-07-26
- **Landed:** PROJECT.md, HANDOFF.md, Sources.md, Decisions.md created; CLAUDE.md wired with the Project Wiki section (PR #2, commit 7d62382, merge ac9fba9)
- **Why:** Fleet-wide wiki initialization per the project-wiki skill's INIT mode [Fact — PR #2 body]

---

## Mining coverage
_Backfilled 2026-07-26 by project-wiki BACKFILL. Entries after this date are
appended live by MAINTAIN._
- PR title sweep: all 2 merged PRs — no cap
- Deep reads: 2 of 2 PRs (below the ~5-PR threshold, so milestones derive from the commit log + existing docs; cap 20 not reached)
- Also swept: git log (merges/no-merges: 3 commits + 1 merge), tags (none), wrap logs (none — no `docs/` or session-log dirs), ADRs (none), decision ledger (`Decisions.md`, D1–D2, read for anchors), README.md, kickoff briefs (none found)
- Not mined: closed-unmerged PRs, issues
