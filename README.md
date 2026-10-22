# Spanish Teacher Course Pack

Neutral Latin American Spanish course materials from A1 to C1. Topic pages ship Forms A–D plus exam papers for the Spanish Teacher bot to load over `raw.githubusercontent.com`.

**Version:** v1 (2026-10-22)

## How a bot should load this pack

1. Fetch [`manifest.json`](https://raw.githubusercontent.com/antonyfuentesdev/spanish-teacher-course-pack/main/manifest.json).
2. For each page entry that has a `raw_url`, fetch that URL.
3. Verify the response body against the entry’s `sha256` (and optionally `bytes`).

Do not invent missing pages; treat a checksum mismatch as an incomplete fetch.

## Notion reading copy

Human-readable Notion mirror:

https://ringed-sombrero-50c.notion.site/4011414f7879816f8df2c37420a9d85f

## Licence

Licence not yet chosen. All rights reserved until then.
