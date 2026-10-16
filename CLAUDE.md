# CLAUDE.md

## Claude tooling for this repo

Global commands (`.claude/commands/`) and skills (`.claude/skills/`) vendored from `ksdisch/claude-config` via `/claudify-repo`, so they work in cloud/web sessions and for collaborators. ✅ = cloud-safe (pure reasoning + repo edits). 💻 = **local-only** — needs local tools (browser MCP, Chrome, local TTS/voice, or the local `nlm` CLI / NotebookLM MCP) and will NOT work in a cloud/web session.

### Commands

- ✅ `/autonomous-milestone` — plan/build/test/verify a target end-to-end, or triage the backlog into ranked candidates; ultracode multi-agent orchestration.
- ✅ `/begin` — open a session: orient on branch/commits/open PRs, recap the last `/wrap` log, route into the session-start spec. (Optional audio recap is local-only.)
- 💻 `/boot_server` — detect how the project is served, start the dev server in the background, open it in Chrome.
- ✅ `/brainstorm` — multi-mode structured brainstorm (Moonshot default; QuickWin, Subtract, Harden, Premortem, Friction, Delight, Positioning, Reach); blind agent teams + critic gate → `docs/ideas/` vision docs + backlog stubs.
- 💻 `/catchup` — mid-session audio catch-up as an MP3 (local TTS); keeps working after.
- ✅ `/claudify-repo` — vendor global commands/skills into this repo and/or brainstorm repo-specific automations.
- 💻 `/envsetup` — open `.env` in the editor + the credential's generation page in Chrome, with a key stub pre-added.
- ✅ `/explore-plan` — explore → plan → confirm before any code; proposes 2–3 ranked approaches and waits for a pick.
- ✅ `/handoff` — generate a paste-ready handoff prompt for a fresh session; captures lessons + plan state. (Optional audio is local-only.)
- ✅ `/prompt-optimize` — one-shot prompt rewrite: diagnose, pick a workflow archetype + model + effort, return a ready-to-paste prompt. Advisory only.
- ✅ `/reframe-orchestrator` — reframe `.claude/orchestrator.md` into a mode-independent invariants & gates doc; docs-only.
- 💻 `/screenshot-iterate` — visual loop: implement against a mock, screenshot the running app, compare, iterate.
- 💻 `/smoke-test` — set up a manual smoke test: opens the needed pages in Chrome (auto-boots the dev server) and hands over a do-this-see-that checklist saved under `docs/smoke/`.
- ✅ `/tdd` — test-first loop: write failing tests, confirm they fail for the right reason, commit, then code until green without touching the tests.
- ✅ `/trim-context` — find and fix Claude Code token bloat (oversized CLAUDE.md, bloated memory, `.claude/` cruft); auto-applies fixes.
- ✅ `/wrap` — end-of-session recap: the why, vocabulary, active-recall quiz, next moves; saves a dated file. (Optional audio is local-only.)

To vendor more global tooling or brainstorm repo-specific automations, run `/claudify-repo`.

## Operating Constraints

@.claude/operating-constraints.md

## Project Wiki

This project uses the project-wiki skill. When integrating new sources, recording decisions, or pausing work:
- Update `PROJECT.md` status and next actions
- Update `HANDOFF.md` with what changed and what's next
- Add durable understanding to `Wiki/` topic pages
- Record decisions in `Decisions.md`
- Keep `Wiki/_index.md` current

(`Wiki/`, `Decisions.md`, and `Sources.md` are created on first need — templates live in the skill.)

Invoke the `project-wiki` skill when wiki updates are needed.
