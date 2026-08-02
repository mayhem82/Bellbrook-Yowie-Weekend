# Bellbrook Yowie Weekend

Static site for the Yowie Weekend festival. Plain HTML/CSS, no build step, no
framework — deploys as-is to GitHub Pages or any static host.

## Status

Draft scaffold only. Event name, dates, venue, schedule, vendors, sponsors and
ticket prices are all placeholders and need to be filled in.

## Structure

```
index.html      Home / about the event
schedule.html   Weekend program (Day 1 / Day 2 tables)
vendors.html    Market stalls, food vendors, sponsors
tickets.html    Ticket options, volunteering, "get involved" form
assets/
  styles.css    Shared styling for all pages
```

## Filling in the placeholders

Every page uses `[[TOKEN]]` markers for content that isn't decided yet. Search
the whole repo for `[[` to find them all, e.g.:

- `[[EVENT_NAME]]` — the festival's actual name
- `[[EVENT_TOWN]]`, `[[EVENT_VENUE]]`, `[[EVENT_DATES]]`
- `[[DAY_1_DATE]]`, `[[DAY_2_DATE]]`
- `[[TICKET_PRICE_WEEKEND]]`, `[[TICKET_PRICE_DAY]]`, `[[TICKET_PRICE_FAMILY]]`, `[[TICKETING_LINK]]`
- `[[VENDOR_NAME_*]]`, `[[SPONSOR_NAME_*]]`
- `[[CONTACT_EMAIL]]`

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
