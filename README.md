# Spanish Teacher Course Pack

Neutral Latin American Spanish course materials from A1 to C1. Topic pages ship Forms A–D plus exam papers for the Spanish Teacher bot to load over `raw.githubusercontent.com`.

**Version:** v1 (2026-10-22)

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

Licence not yet chosen. All rights reserved until then.
