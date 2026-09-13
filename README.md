# The Yowie Festival — Bellbrook

Static site for The Yowie Festival, a Macleay Valley Hospice & Bellbrook
Community Fundraiser, 2–4 October 2026 in Bellbrook, NSW. Plain HTML/CSS, no
build step, no framework — deploys as-is to GitHub Pages or any static host.

## Status

Core event details are confirmed (name, tagline, dates, venue, town, cause,
contact email, market days/hours, and the weekend's activity list). Entry is
free — stalls and activities are run by local community clubs and groups as
their own fundraisers. Two camping options are confirmed on `camping.html`:
Bellmeadow Homestead (pricing and booking contact confirmed) and Bellbrook
Cabins (pricing/booking still TBC) — The Bellbrook Hotel's own cabins are
sold out. Stallholder fees, policies and the sponsorship tier structure are
confirmed on `vendors.html`, now including Silver and Bronze sponsors.
`safety.html` has confirmed first aid (Slim Dusty Room), defibrillator
location, heat safety and fire safety content. A `disclaimer.html` page has
been added, linked from every footer. Still to fill in: day-by-day times for
some non-market activities, and stallholder names.

Entertainment lineup is still being finalised by the committee. Confirmed so
far: whip cracking, trick pony and donkeys with Laughing Stock Productions
(Saturday, 11:30am and 2:30pm); wood chopping with NSW Axemen; face painting
by Pepparific Parties; a bucking bull organised by The Bellbrook Hotel
(day/time TBC); a Yowie Hunt along Postman's Trail (~2hr car-drive activity,
day/time TBC); Slim Dusty Tours organised by Kate (times TBC); and gumboot
throwing (day/time TBC). The Saturday/Sunday live music running order is
confirmed — see `schedule.html`'s Live Music Lineup section; Friday's lineup
is still a draft. Kids' activities are still being organised.

## Structure

```
index.html      Home / about the event
schedule.html   Weekend program (Day 1 / Day 2 / Day 3 tables)
safety.html     Emergency info, first aid, weather, fire, alcohol, access
vendors.html    Market stalls, food vendors, sponsors
camping.html, whip-cracking-display.html, live-music.html,
face-painting.html, wood-chopping-competition.html,
fishing-competition.html
                Individual activity pages, linked from the poster and
                the homepage highlight cards
assets/
  styles.css    Shared styling for all pages
```

## Filling in the remaining placeholders

Every page uses `[[TOKEN]]` markers for content that isn't decided yet. Search
the whole repo for `[[` to find them all, e.g.:

- `[[FISHING_LOCATION]]` — where the fishing competition is held
- `[[VENDOR_NAME_*]]` — stallholder names on `vendors.html`
- `[[SPONSOR_NAME_3]]` — one remaining supporting sponsor name

Exact times weren't on the event poster, so `schedule.html` uses "TBC" in the
time column — replace those once the official running order is published.

A quick way to replace one token everywhere once you have the real value:

```bash
grep -rl '\[\[EVENT_NAME\]\]' . | xargs sed -i 's/\[\[EVENT_NAME\]\]/Your Real Event Name/g'
```

There's no contact form on the site — every "get involved" call to action is a
plain `mailto:` link to `bellbrook.yowie.fest@gmail.com`, so there's nothing to
wire up.

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
