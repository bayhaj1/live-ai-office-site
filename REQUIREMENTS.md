# Live AI Office — showcase site requirements

Hand-over spec for the static showcase (repo `bayhaj1/live-ai-office-site`, GitHub Pages from `main`).

## Purpose and framing
- Public showcase for the Burundi Ministry of Finance, Budget and Digital Economy talent census (submission 15 Nov 2026;
  national meeting 19 Nov 2026) and for offices / public-sector buyers.
- Framing: **a local, private security intelligence dashboard** — but every feature shown is **employee-only**: presence now,
  arrivals and late arrivals, attendance timesheets (day/week, CSV), employees per area, camera health, existing incidents and
  alerts, and the owner's decision (audit) log. No visitor tracking, no unknown-person alerts, no new detection types.
- Future security modules appear **only as roadmap**, described as optional modules added to the same modular dashboard.

## Languages
- French first at `/`, English at `/en/`; a FR / EN toggle in the header on both; `hreflang` alternates.

## Sections (in order)
1. Hero: "Live AI Office" — local AI for office attendance and supervision; eyebrow "Intelligence de sécurité · conçu au
   Burundi"; two CTAs (screens, contact); stat strip (100 % local, 0 cloud subscription, FR/EN, real time).
2. Problem: paper/Excel attendance, unwatched video, costly offshore biometric/cloud solutions.
3. How it works: architecture diagram (cameras → office computer [detection & tracking, intelligent matching engine, rules,
   encrypted DB] → dashboard; "no cloud"), plus six privacy points (no cloud, encrypted at rest, locked-down access, human in
   control, minimisation, existing hardware).
4. Features with demo-mode screenshots: Aujourd'hui, Présence (week), Personnel, Alertes + journal, Paramètres, and a phone view.
5. Impact for offices, SMEs and the public sector (punctuality, fair payroll/HR, useful security, data sovereignty, low cost,
   local digital jobs).
6. Roadmap: v1 now; Dec 2026 guided enrolment + one-command start; Q1 2027 pilot, monthly reports, multi-site, roles; Q2 2027
   optional security modules; then DPIA, certification, rollout.
7. Contact: Alex Nahimana · POPEKI SURL · alex@popeki.com.
- Footer: © 2026 POPEKI SURL; note that illustrations are AI-generated (fictional people) and screens come from demo mode.

## Visual design
- Same Material 3-inspired look as the app (blue primary #2b59c3 / #5b8cff, soft surfaces, rounded 16–28 px cards), modern
  typography with tight tracking, dark "how it works" band, tinted impact band.
- Motion: hero slow drift, hero text rise, animated data-flow lines in the diagram, scroll reveal via CSS
  `animation-timeline: view()` (progressive enhancement); everything off under `prefers-reduced-motion`.
- Visuals: Higgsfield (gpt_image_2_6), **synthetic people only**, a modern African office setting; **no real photos or faces,
  no camera frames, no IPs, no office names, no flags, national symbols, ministry logos or
  official seals**. Every image is checked by eye before it is pushed. App screenshots come only from `python -m
  business_watch.demo` (fictional employees, generated silhouettes, simulated day).

## Performance, privacy and security
- Static HTML + inline CSS, **no JavaScript, no trackers, no analytics, no external fonts or CDNs**; every asset same-origin.
- Meta CSP: `default-src 'none'; img-src 'self'; style-src 'unsafe-inline'; base-uri 'none'; form-action 'none'`;
  `referrer: no-referrer`.
- Images in WebP (hero ≈1344 px, sections ≈880 px, screenshots 1200 px), width/height set, lazy loading below the fold, hero
  preloaded; total page weight well under 1 MB.
- `.nojekyll`; no secrets, no real data, nothing from the private code repo except demo screenshots.
