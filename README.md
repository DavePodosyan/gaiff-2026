# GAIFF 2026 — Program & Schedule

Unofficial browser for the 23rd Golden Apricot Yerevan International Film Festival (July 12–19, 2026). Static site, no build step, hosted on Cloudflare Pages.

## Files

- `index.html` — the app (design, views, logic)
- `data.json` — all content: festival dates, sections, films, screenings

## Updating data

Edit `data.json` only:

- **Film details**: fill `country`, `runtime` (minutes, number), `year` — currently `null` for most films.
- **Schedule**: when GAIFF announces it, add entries to `screenings`:

```json
{ "film": "babystar", "date": "2026-07-14", "time": "19:00", "venue": "Moscow Cinema, Red Hall", "note": "Q&A" }
```

`film` must match a film `id`. Screenings appear automatically in the Schedule tab and on film cards.

## Deploy

Upload both files to Cloudflare Pages (dash.cloudflare.com → Workers & Pages → the project → upload). Local preview: `python3 -m http.server` (fetch won't work from `file://`).

Film data source: [gaiff.am/program](https://gaiff.am/program)
