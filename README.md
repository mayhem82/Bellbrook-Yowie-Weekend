# The Yowie Festival — Bellbrook

Static site for The Yowie Festival, a Macleay Valley Hospice & Bellbrook
Community Fundraiser, 2–4 October 2026 in Bellbrook, NSW. Plain HTML/CSS, no
build step, no framework — deploys as-is to GitHub Pages or any static host.

## Status

Core event details are confirmed (name, tagline, dates, town, cause, and the
weekend's activity list). Entry is free — stalls and activities are run by
local community clubs and groups as their own fundraisers. Still to fill in:
exact venue address, day-by-day times, stallholder/sponsor names, any camping
fee, and a contact email.

## Structure

```
index.html      Home / about the event
schedule.html   Weekend program (Day 1 / Day 2 / Day 3 tables)
vendors.html    Market stalls, food vendors, sponsors
tickets.html    Free entry, camping, volunteering, "get involved" form
assets/
  styles.css    Shared styling for all pages
```

## Filling in the remaining placeholders

Every page uses `[[TOKEN]]` markers for content that isn't decided yet. Search
the whole repo for `[[` to find them all, e.g.:

- `[[FISHING_LOCATION]]` — where the fishing competition is held
- `[[VENDOR_NAME_*]]`, `[[SPONSOR_NAME_*]]` — stallholder and sponsor names
- `[[CONTACT_EMAIL]]`

Exact times weren't on the event poster, so `schedule.html` uses "TBC" in the
time column — replace those once the official running order is published.

A quick way to replace one token everywhere once you have the real value:

```bash
grep -rl '\[\[EVENT_NAME\]\]' . | xargs sed -i 's/\[\[EVENT_NAME\]\]/Your Real Event Name/g'
```

The "get involved" form on `tickets.html` doesn't submit anywhere yet — it's a
placeholder until you pick a real submission method (embedded form service,
mailto link, or similar).

## Running locally

No build step needed. Either open `index.html` directly in a browser, or serve
the folder so relative links behave normally:

```bash
python3 -m http.server 8000
```

## GitHub Pages setup

Repository **Settings → Pages → Deploy from a branch → `main` → `/root`**.
The `.nojekyll` file is included so GitHub Pages serves the files as-is.

Because it's plain static HTML/CSS with no build tooling, this repo can also
be deployed as-is to Netlify, Vercel, Cloudflare Pages, or any static file
host — just point the host at the repo root.
