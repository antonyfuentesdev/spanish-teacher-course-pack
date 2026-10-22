# Spanish Teacher Course Pack

Neutral Latin American Spanish course materials from A1 to C1. Topic pages ship Forms A–D plus exam papers for the Spanish Teacher bot to load over `raw.githubusercontent.com`.

**Version:** v1.2 (2026-10-22). Changes from v1.1: fixes from the Oct 22 typed dry run (13.11 progress file title "Spanish Teacher progress", section headings and the empty file created at setup; City and Job or studies in the Profile; the skipped-placement row and its evidence; Encouragement milestones cite Sessions IDs; no fast-track for a self-declared beginner in A1.1; short first lesson and typed lesson defined; A1 gist questions stay in Spanish with an English gloss; the C1 cumulative plan total is 328 h, matching the per-topic hours; A1.1-1 materials per session) and the native-speaker spot check (Spain-only words replaced with Latin American ones, question/key fixes, unified test opener).

**v1.1** (2026-10-22). Changes from v1: the index page describes the manifest + SHA-256 checks; the monthly pace check became a weekly pace check inside the weekly report (the one-month post-exam check remains); no time range shown to learners; "Plan %" is now "Overall %".

## How a bot should load this pack

1. Fetch [`manifest.json`](https://raw.githubusercontent.com/antonyfuentesdev/spanish-teacher-course-pack/main/manifest.json) from `main`. Read `version` and `tag` to learn the current release.
2. For each page entry that has a `raw_url`, fetch that URL. Each `raw_url` is pinned to the release tag (not `main`), so content does not drift under the bot.
3. Verify the response body against the entry’s `sha256` (and optionally `bytes`).

Do not invent missing pages; treat a checksum mismatch as an incomplete fetch.

## Releasing a new version

1. Change the course files as needed.
2. Bump `version` (and the version line in `pages/00-index-manifest.md`).
3. Point every `raw_url` and `raw_base` at the new tag (for example `.../v2/...`), set `"tag"` to that tag, and keep `manifest_latest` on `main`.
4. Recompute `bytes` and `sha256` for every changed file; regenerate `manifest.md`.
5. Commit, then create an annotated tag on that commit. Never move an existing tag.

## Notion reading copy

Human-readable Notion mirror:

https://ringed-sombrero-50c.notion.site/4011414f7879816f8df2c37420a9d85f

## Licence

This course pack is licensed under the [Creative Commons Attribution-NonCommercial 4.0 International licence (CC BY-NC 4.0)](https://creativecommons.org/licenses/by-nc/4.0/). You may share and adapt it for non-commercial purposes, as long as you give credit ("Spanish Teacher Course Pack by Antony Fuentes"), link to the licence and say what you changed. Commercial use requires permission from the author. See [`LICENSE`](LICENSE).
