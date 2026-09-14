# The Yowie Festival — Bellbrook

Static site for The Yowie Festival, a Macleay Valley Hospice & Bellbrook
Community Fundraiser, 2–4 October 2026 in Bellbrook, NSW. Plain HTML/CSS, no
build step, no framework — deploys as-is to GitHub Pages or any static host.

## Status

**Live** at [yowiefest.com](https://yowiefest.com) (and still reachable at
`mayhem82.github.io/Bellbrook-Yowie-Weekend/`). No DRAFT banners or
`[[TOKEN]]` placeholders remain anywhere on the site.

Core event details are confirmed (name, tagline, dates, venue, town, cause,
contact email, market days/hours). Entry is by gold coin donation. Camping
is hosted solely by Bellmeadow Homestead (a second option at Bellbrook
Cabins was pulled — not yet approved). The Bellbrook Hotel's own cabins are
sold out. `vendors.html` has 9 confirmed stallholders and the full
sponsorship tier structure. `safety.html` has confirmed first aid (Slim
Dusty Room), defibrillator location, a named muster point (Bellbrook Park —
the map pin itself is still centred on the hotel pending real coordinates),
heat safety, camp chair and "cash is king" notes. A `disclaimer.html` page
carries the committee's official disclaimer text, linked from every footer.

`schedule.html` has the committee's full three-day live music running order
and entertainment program (Official Opening, Best Yowie Screach, Yowie
Queen Presentation, Post Ripping, Bucking Bull Sunday 1-4pm, Football Sunday
7:30pm, and more) — see that file's own notes on the "single start-time per
act" format used for the live music table. Still outstanding with the
committee: Wood Chopping's finish time, Slim Dusty Tours and gumboot
throwing (day/time), and Bucking Bull's exact location.

Sponsors/organisers still needing an external link once one's available:
Kempsey Stock & Land Pty Ltd, Macleay Pumps & Irrigation, the Bellbrook
Fishing Club, Laughing Stock Productions, NSW Axemen, and Flash Ratz with
Jo Lane.

The homepage's "Getting There" map is a static screenshot image
(`assets/img/getting-there-map.jpg`), not a live embed — replaced after
repeated Google Maps iframe issues (pins, DNS-dependent embeds, zoom limits).
The detailed festival-grounds pin map and the old map-planner tool have both
been removed until a custom map is ready; only the regional Kempsey-Bellbrook
image and the `safety.html` muster-point embed remain.

## Structure

```
index.html      Home / about the event
schedule.html   Weekend program (Day 1 / Day 2 / Day 3 tables, live music lineup)
safety.html     Emergency info, first aid, defibrillator, heat and fire safety
vendors.html    Market stalls, food vendors, sponsors, become a stallholder/sponsor
disclaimer.html Committee's official disclaimer text, linked from every footer
camping.html, whip-cracking-display.html, live-music.html,
face-painting.html, wood-chopping-competition.html,
fishing-competition.html, yowie-hunt.html
                Individual activity pages, linked from the poster and
                the homepage highlight cards
assets/
  styles.css    Shared styling for all pages
  img/          Yowie icon artwork and photos, including getting-there-map.jpg
```

## Remaining TBA items

No `[[TOKEN]]` placeholders are left in the site — everything still unknown
is written as plain "TBA" text in context instead. Still outstanding with the
committee:

- Wood Chopping Competition's finish time (`schedule.html`)
- Slim Dusty Tours and gumboot throwing, day/time (`schedule.html`)
- Bucking Bull's exact location (`schedule.html`)
- Bellbrook Park's map coordinates for the muster point pin (`safety.html`)

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

## Custom domain

`yowiefest.com` is registered (via Namesilo) and live — DNS is configured with
four A records on the apex pointing to GitHub Pages' IPs
(`185.199.108/109/110/111.153`) and a `www` CNAME to `mayhem82.github.io`.
The `CNAME` file in this repo's root points GitHub Pages at the domain, and
HTTPS is enforced with GitHub's free auto-issued certificate. Nothing further
needed here unless the domain is ever moved to a new registrar or DNS
provider, in which case the same records need re-adding there.
