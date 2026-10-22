# Spanish Teacher Course Pack

Neutral Latin American Spanish course materials from A1 to C1. Topic pages ship Forms A–D plus exam papers for the Spanish Teacher bot to load over `raw.githubusercontent.com`.

**Version:** v1.4.1 (2026-10-22). Changes from v1.4: removed named external sources.

**v1.4** (2026-10-22). Changes from v1.3: standard object pronouns instead of leísmo — B2 exam reading ("lo he llamado" to señor Arce, "le informé por teléfono que"), C1.1-1 ("¿qué lo llevó a…? / ¿qué la llevó a…?" by the referent's gender; the model dialogue now asks "¿Qué motivó ese cambio?"; the key accepts both forms), C1.1-2 key ("lo van a operar"), B1 exam voicemail ("Le dejo este mensaje…") and C1 exam role-play ("Me comunico con usted…") where the listener's gender is unknown, and the C1.1-3 key (models llamarlo / llamarla; still accepts llamarle as a regional form); 13.1 adds a note that 650–800 h is the external research benchmark, while the course frame is 328 guided lesson hours, about 1–2 years at 6 h a week.

**v1.3** (2026-10-22). Changes from v1.2: GitHub is now the only home of the pack (the Notion reading copy is retired), so the manifest and the index page no longer carry Notion page IDs, public Notion links or the Notion landing-page entry (72 entries, all files); the learning plan overview no longer offers a rough time range (no time ranges, even when asked, as in 13.11); 13.1 states the lesson core as 328 h only; the release steps below describe the pull-request flow on the protected `main` branch.

**v1.2** (2026-10-22). Changes from v1.1: fixes from the Oct 22 typed dry run (13.11 progress file title "Spanish Teacher progress", section headings and the empty file created at setup; City and Job or studies in the Profile; the skipped-placement row and its evidence; Encouragement milestones cite Sessions IDs; no fast-track for a self-declared beginner in A1.1; short first lesson and typed lesson defined; A1 gist questions stay in Spanish with an English gloss; the C1 cumulative plan total is 328 h, matching the per-topic hours; A1.1-1 materials per session) and the native-speaker spot check (Spain-only words replaced with Latin American ones, question/key fixes, unified test opener).

**v1.1** (2026-10-22). Changes from v1: the index page describes the manifest + SHA-256 checks; the monthly pace check became a weekly pace check inside the weekly report (the one-month post-exam check remains); no time range shown to learners; "Plan %" is now "Overall %".

## How a bot should load this pack

1. Fetch [`manifest.json`](https://raw.githubusercontent.com/antonyfuentesdev/spanish-teacher-course-pack/main/manifest.json) from `main`. Read `version` and `tag` to learn the current release.
2. For each page entry that has a `raw_url`, fetch that URL. Each `raw_url` is pinned to the release tag (not `main`), so content does not drift under the bot.
3. Verify the response body against the entry’s `sha256` (and optionally `bytes`).

Do not invent missing pages; treat a checksum mismatch as an incomplete fetch.

## Releasing a new version

`main` is protected (ruleset "protect main": changes only through a pull request with 1 approval; force pushes and branch deletion are blocked; repository admins may bypass the approval).

1. On a new branch from the current `origin/main`, change the course files as needed.
2. Bump `version` and `tag` in `manifest.json` and the version line in `pages/00-index-manifest.md`.
3. Point every `raw_url` and `raw_base` at the new tag (for example `.../v1.5/...`), and keep `manifest_latest` on `main`.
4. Recompute `bytes` and `sha256` for every changed file; regenerate `manifest.md`.
5. Open a pull request, review it, and merge it into `main`.
6. Create an annotated tag with the new version on the merge commit and push only the tag. Never move or reuse an existing tag.
7. Check that all `raw_url`s at the new tag download and match their `sha256`.

## Licence

This course pack is licensed under the [Creative Commons Attribution-NonCommercial 4.0 International licence (CC BY-NC 4.0)](https://creativecommons.org/licenses/by-nc/4.0/). You may share and adapt it for non-commercial purposes, as long as you give credit ("Spanish Teacher Course Pack by Antony Fuentes"), link to the licence and say what you changed. Commercial use requires permission from the author. See [`LICENSE`](LICENSE).
