# The Yowie Festival — Bellbrook

Static site for The Yowie Festival, a Macleay Valley Hospice & Bellbrook
Community Fundraiser, 2–4 October 2026 in Bellbrook, NSW. Plain HTML/CSS, no
build step, no framework — deploys as-is to GitHub Pages or any static host.

## Status

**Live** — the DRAFT banners have been removed from every page. A few details
are still genuinely TBC with the committee (fishing competition location,
specific stallholder names, Friday's live music lineup, some activity times)
and are shown as plain "TBC" text in context rather than as `[[TOKEN]]`
placeholders.

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
been added, linked from every footer.

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

## Remaining TBC items

No `[[TOKEN]]` placeholders are left in the site — everything still unknown
is written as plain "TBC" text in context instead. Still outstanding with the
committee:

- Fishing competition location and entry details
- Specific market stallholder names (`vendors.html`)
- Friday's live music lineup and a few other activity times (`schedule.html`)

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

## Pointing a custom domain at this site

1. **Buy the domain** (if not already done) from any registrar — GoDaddy,
   Namecheap, Crazy Domains, VentraIP, etc. all work fine for `.com`/`.com.au`.
2. **Add DNS records** at the registrar (or wherever DNS is managed for the
   domain). Two options:
   - **Apex/root domain** (`bellbrookyowiefestival.com`) — add four **A**
     records, all pointing to GitHub Pages' IPs:
     ```
     185.199.108.153
     185.199.109.153
     185.199.110.153
     185.199.111.153
     ```
   - **www subdomain** (`www.bellbrookyowiefestival.com`) — add one **CNAME**
     record pointing to `mayhem82.github.io`.
   - Most people set up both: A records on the apex, CNAME on `www`, so either
     version works.
3. **Add a `CNAME` file** to the root of this repo containing just the domain,
   e.g. `bellbrookyowiefestival.com` (no `http://`, no trailing slash) — send
   me the actual domain and I'll add this file and commit/push it for you.
4. In the repo, go to **Settings → Pages → Custom domain**, enter the same
   domain, and save. GitHub will verify the DNS records (can take a few
   minutes to a few hours).
5. Once verified, tick **Enforce HTTPS** in that same Pages settings screen —
   GitHub issues a free SSL certificate automatically. This checkbox is
   greyed out until DNS propagates, so it may need a revisit a bit later.
6. DNS changes can take anywhere from a few minutes up to ~24-48 hours to
   fully propagate worldwide, depending on the registrar and the DNS record's
   TTL. The site keeps working at `mayhem82.github.io/Bellbrook-Yowie-Weekend/`
   the whole time, so there's no downtime while this propagates.

Send me the domain name once it's purchased and I'll do step 3 immediately.
