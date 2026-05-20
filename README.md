# youtube-archive

Personal YouTube watch-history archive — daily-ingested transcripts + 2-paragraph summaries.
Tracked per PLAN.md §14.99.W in the parent `current-focus` repo.

## Layout

```
youtube-archive/
  README.md            # this file
  CLAUDE.md            # routing rules for this repo
  index.md             # auto-generated catalog of all videos (writes on each ingest run)
  videos/
    YYYY-MM-DD-<video-id>-<slug>.md   # one file per video; frontmatter + summary + transcript
  .gitignore
```

## Per-video file

Frontmatter:
```yaml
---
video_id: dQw4w9WgXcQ
title: <title>
channel: <channel>
url: https://www.youtube.com/watch?v=<id>
watched_date: 2026-05-19
watched_at: 2026-05-19T15:30:42Z
watch_count: 1
duration_seconds: 1234
summary_model: Qwen/Qwen3-14B            # or claude-haiku-4-5 on fallback
tagging_model: claude-haiku-4-5
proposed_tags: [health, immunosenescence]
proposed_entities: [ent-intervention-rapamycin]
status: new                               # new | reviewed | routed-to-<surface> | archived | rejected
routed_to: null                           # PR URL or destination path once introduced into a function set
---
```

Body:
```
## Summary
<2 paragraphs from W.C>

## Transcript
[00:00:00] First cue...
[00:00:04] Second cue...
...
```

## Writes flow

1. `ai-clients/scripts/youtube_archive_write.py` reads W.C's `--out` JSON + the cached transcripts and writes / updates per-video markdown files here.
2. The cron job (W.F, PLAN §14.99.W) commits + opens a PR per ingest pass.
3. Dashboard (W.E) renders the archive — list of recent + per-video detail with introduce-to-function-set buttons.

## Privacy

Public by default. The pipeline doesn't filter content; the user can re-mark individual files private (`status: archived`, or move into a separate private repo) after they review on the dashboard. No portfolio / financial / health-PII leakage expected from watch history alone, but the user is the final filter.

## Branch protection

`main` is PR-required + 0-review (admin bypass for solo merges) per the §14.99.I pattern — applied via `gh api repos/.../branches/main/protection` (see ai-clients PR #294 family for the spec).
