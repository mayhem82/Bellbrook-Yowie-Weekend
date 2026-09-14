# The Yowie Festival — Bellbrook

Static site for The Yowie Festival, a Macleay Valley Hospice & Bellbrook
Community Fundraiser, 2–4 October 2026 in Bellbrook, NSW. Plain HTML/CSS, no
build step, no framework — deploys as-is to GitHub Pages or any static host.

## Status

**Live** at [yowiefest.com](https://yowiefest.com) (and still reachable at
`mayhem82.github.io/Bellbrook-Yowie-Weekend/`). No DRAFT banners or
`[[TOKEN]]` placeholders remain anywhere on the site. A few details are still
genuinely unconfirmed with the committee (specific stallholder names,
Friday's live music lineup, a handful of activity times) and are shown as
"TBA" in context rather than as placeholders.

Core event details are confirmed (name, tagline, dates, venue, town, cause,
contact email, market days/hours, and the weekend's activity list). Entry is
free — stalls and activities are run by local community clubs and groups as
their own fundraisers. Two camping options are confirmed on `camping.html`:
Bellmeadow Homestead (pricing and booking contact confirmed) and Bellbrook
Cabins (pricing/booking still TBA) — The Bellbrook Hotel's own cabins are
sold out. Stallholder fees, policies and the full sponsorship tier structure
(Platinum through Supporting) are confirmed on `vendors.html`. `safety.html`
has confirmed first aid (Slim Dusty Room), defibrillator location, heat
safety and fire safety content. A `disclaimer.html` page carries the
committee's official disclaimer text, linked from every footer.

Sponsors/organisers still needing an external link once one's available:
Kempsey Stock & Land Pty Ltd, Macleay Pumps & Irrigation, Smithtown
Sporties, the Bellbrook Fishing Club, Laughing Stock Productions, NSW
Axemen, and Flash Ratz with Jo Lane.

Entertainment lineup is still being finalised by the committee. Confirmed so
far: whip cracking, trick pony and donkeys with Laughing Stock Productions
(Saturday, 11:30am and 2:30pm); wood chopping with NSW Axemen, sponsored by
Kempsey Stock & Land; face painting by Pepparific Parties, ongoing all
weekend; a Fishing Comp' organised by the Bellbrook Fishing Club, running
the whole weekend on the Macleay River (Friday 3pm to Sunday weigh-in); a
Yowie Hunt along Postman's Trail (Saturday, 8-9am registration at Bellmeadow
Homestead, own page `yowie-hunt.html`); a bucking bull organised by The
Bellbrook Hotel (day/time TBA); Slim Dusty Tours organised by Kate (times
TBA); and gumboot throwing (day/time TBA). The Saturday/Sunday live music
running order is confirmed — see `schedule.html`'s Live Music Lineup
section; Friday's lineup is still being finalised. Kids' activities are
still being organised.

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

- Specific market stallholder names (`vendors.html`)
- Friday's live music lineup and a few other activity times (`schedule.html`)
- Fishing Comp' presentation location (day/time and river location are confirmed)

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
