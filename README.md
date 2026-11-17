# What's Winning — Ad Intelligence

A static prototype that, given a brand or domain, shows its active ads and what is
winning — split by format and creator, with long-running flags, new launches, and a
sortable swipe file.

## What it is

- **Brand/domain lookup** that builds pre-filtered Meta Ad Library, Google Ads
  Transparency, and LinkedIn Ad Library links for any brand.
- **Top ads, shown inline** — compact visual cards (brand header with count, format
  tabs with counts, days-running badge, published reach where a library published
  it), in the style of a competitor playbook. No playbook/insights panel yet.
- **Sortable, filterable swipe file** of the captured ads, scoped to the searched
  brand, with a CSV download.
- **Screenshot-first capture** — drop, paste, or pick a screenshot, confirm the
  brand, and save. The screenshot becomes the ad's thumbnail ("Captured
  screenshot"). Missing fields show as "Not recorded". A full manual form sits
  underneath for adding details.
- **Ad-count recorder** — record the number of active ads exactly as a library page
  showed it, with its source and the date seen (e.g. "46 active (as seen in Meta
  Ad Library, 7 Nov 2026)"). Counts are snapshots, never live figures.

## Data

The file ships with the July 2026 audit snapshot baked in: **36 real ads**
(Amazon 22, TikTok 11, Google 3) across Meta, Google, TikTok, and LinkedIn, plus
format counts computed from the file at render time. The seven zero-presence
records from the audit are not shown in the page but are recorded in the
research notes.

Top ads are a curated set with a stated reason per ad, not a days-running ranking —
the July snapshot has no per-ad start dates. A true longest-running ranking becomes
possible once start dates are entered on cards.

## Honest limits — read this before using it

- **No backend, no live fetch.** This is a static page. It does not pull ads from
  any library. Typing a brand only filters the baked-in snapshot and builds links
  out to the libraries. Combing libraries live would need a backend, browser
  automation, or a paid ad-data service.
- **No spend, CTR, or conversions.** The libraries do not publish them for
  commercial ads (outside EU/UK, no age/gender targeting either). Any "estimated
  spend" in other tools is that tool's own modelled estimate, not a published
  figure — this tool shows none.
- **No real creative images.** The July data has no screenshot URLs, only text
  descriptions of each creative. Visual cards are labelled "Visual mock — based
  on audit notes, not the real creative". Real thumbnails only enter via a
  screenshot you attach when capturing.
- **Captures live in the browser tab only** and reset on reload. Download the
  swipe-file CSV to keep the text copy. The in-page text reader (OCR) is
  best-effort and untested on a real screenshot; its suggestions are never saved
  as fact unless accepted.
- **LinkedIn library link is live-unverified** (checked Nov 5, 2026: results
  failed to load). LinkedIn itself does filter by Country in its UI; the link the
  tool builds is global.

## Run it

Open `index.html` in a browser, or enable GitHub Pages (Settings → Pages →
Deploy from a branch, `main`, `/` root) and visit
`https://athyyna.github.io/whats-winning-ad-intelligence/`.

## Origin

Built Nov 7, 2026 as a clickable prototype from the July 2026 audit data in the
private `athyyna/ad-intelligence-launcher` repo (which holds the cross-platform
ad-library comparison and the `/launcher` link generator). The prototype is
deliberately separate from that repo's fixed dashboard.
