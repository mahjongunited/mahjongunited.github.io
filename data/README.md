# Content

Every tile on the wall is one markdown file. Add a file, list it in `index.json`, done.

```
data/
  index.json        ← the list of files, in the order they appear on the wall
  events/*.md       ← events (upcoming or past — decided by the date)
  classes/*.md      ← open classes and private lessons
  about.md
```

## File format

```
---
title: Autumn Open Tournament
kind: event            # event | open | private | about
date: 2026-11-22       # one-off events; a date in the past moves it to "Older events"
recurring: Every Friday   # instead of a date, for things that repeat
time: 1:00–6:00 pm
location: Riverdale Community Hall
glyph: 中              # the big faint character on the tile
kicker: Event          # optional; defaults from kind
---

Body text in markdown. Shown when the tile is expanded.
```

The tile's URL is made from its title: "Autumn Open Tournament" → `#events/autumn-open-tournament`.

Note: the page loads these files with `fetch`, so it needs to be served over http (any static host, or `python3 -m http.server` locally). Opened directly from disk it falls back to the sample content baked into `index.html`.
