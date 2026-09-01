# R3 Electric & HVAC

Static marketing site for R3 Electric & Hvac LLC (Huber Heights, OH). Plain HTML/CSS/JS, no build step.

## Local preview

```bash
python3 -m http.server 8962
```

Then open http://localhost:8962

## Contact info

- Phone: `(937) 559-6685` — confirmed by Kyle, matches BBB and every directory listing.
- Address: `8235 Old Troy Pike, Suite 134, Huber Heights, OH 45424` — per BBB/Yelp, not yet
  confirmed directly by Kyle.
- Owner: Robert Smith III — per BBB.
- Founded January 1, 2014 (12 years in business per BBB). BBB Accredited since November 4, 2020,
  A+ rating.
- Hours: Mon–Fri, 9am–5pm — per a directory listing, not yet confirmed by Kyle.
- Rating: 4.8★ / 133 reviews (Birdeye); some sources show 5.0★ off a smaller review count. Used
  the higher-volume 4.8★/133 figure on the site as the more representative number.
- No email found for the business in any listing.
- Described everywhere as a "family owned Christian company" — used directly in the About/Why Us
  copy.
- **No real custom website** — the only "website" listed anywhere is a free Google Business
  auto-site (`r3-electric-hvac-llc.business.site`), which currently 404s. Good cold-call hook:
  they don't actually have a working site despite 130+ reviews and BBB A+ accreditation.

## Services

Full list supplied directly by Kyle (high confidence): A/C system maintenance, A/C system repair,
electric car charger installation, electrical fixture installation, electrical fuse changing,
electrical heat resistor changing, electrical inspections, electrical outlet & switch repair,
electrical panel replacement/upgrading, electrical parts assembly, electrical power restoration,
electrical wiring installation, fan installation, fan repair, ground wire installation, HVAC
system maintenance, heating system installation, heating system maintenance, heating system
repair, install AC, install thermostat, light fixture repair, outdoor lighting installation,
remodeling, repair HVAC, A/C tune-up & safety inspection.

Condensed into 6 service rows on the site (Electrical Wiring/Panels/Remodels; Lighting, Fixtures &
Fans; EV Charger Installation; Heating & AC Repair; AC & Heating Installation; Tune-Ups/
Maintenance/Safety Inspections) to keep the page scannable — every item from Kyle's list is
covered under one of these six.

## Logo & colors

No real logo found or supplied — `assets/logo.svg` is a hand-built placeholder: a bold "R" and "3"
overlapping slightly, per Kyle's direction. Swap in the real logo if R3 has one. Accent palette:
electric blue (`--brand: #1f6feb`) for the "R", red (`--spark: #e0262c`) for the "3".

## Hero slideshow

The hero has a crossfading photo-slideshow background (`.hero-slideshow`/`.hero-slide` in
styles.css, 5s rotation in script.js), same pattern as greenspace-pros. Uses 10 real R3 job-site
photos Kyle pasted inline (`assets/work/work-1.png` through `work-10.png`) — a mix of residential
and commercial electrical panels, AC condensers, and furnace/ductwork installs.

Kyle pasted 14 photos total; 3 were left out of the rotation and moved to `assets/work/unused/`:
two bathroom/shower remodel shots (not clearly R3's own work — electrical/HVAC panels and
equipment felt like a stronger, unambiguous "this is our trade" fit for the hero) and one
near-duplicate commercial ductwork shot. Easy to add any of the three back into the slideshow if
Kyle wants — just move the file back into `assets/work/` and add a matching `<div class="hero-slide">`
line in `index.html`.

Note: the images couldn't be saved directly from the chat (no tool captures inline pasted image
bytes to disk), so Kyle dragged them into Finder himself — they first landed in
`greenspace-pros/assets/work/` by mistake (a stale Finder location) and briefly overwrote that
site's own real work photos. Recovered via `git checkout -- assets/work/` in that repo before
moving the correct files over to `r3-electric-hvac/assets/work/`.

**Image quality**: the pasted photos came through at thumbnail resolution (173px wide) rather than
their original size — no full-res originals were found anywhere on disk (checked Downloads,
Desktop, and system temp/cache dirs). Raw 173px files are kept in `assets/work/originals-lowres/`
for reference. The in-use files were upscaled with `sips --resampleWidth 900` (smooth resampling,
no real detail added — just removes blockiness) and the CSS pairs that with a light `blur(2px)` +
`scale(1.04)` and a slightly darker scrim (`.hero-slide`/`.hero-scrim` in styles.css) so the
background reads as an intentionally soft, moody photo rather than a pixelated one. This is the
practical ceiling without genuine full-resolution source photos — if Kyle finds the originals
later (e.g. on his phone's camera roll), drop them into `assets/work/` with the same filenames for
a real sharpness upgrade.

## Contact form

The quote request form posts to Formspree. Before it will actually send email, replace
`YOUR_FORM_ID` in the form's `action` attribute in `index.html` with a real Formspree form ID
(sign up free at https://formspree.io).

## Deploy

Static site — deploys to Vercel, Netlify, or GitHub Pages with zero configuration.
