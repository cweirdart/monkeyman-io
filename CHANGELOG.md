# Changelog

All notable changes to monkeyman.io. Versions with `-live` in the git tag were what was live at the time.

---

## [v3.1] — 2026-04-14 — Purple glow, lifted polaroids, expanded venues, structured data, OG card

### Added
- **Custom OG share card** (`img/og-card.jpg`, 1200×630, 57 KB) — brand-black background with purple radial glow behind the hand-drawn MONKEYMAN logo, tagline "HOUSE · FUNK · SOUL · NO REQUESTS" and "MONKEYMAN.IO" in gold. Replaces the cropped purple hero photo that iMessage was using. Wired into `og:image`, `twitter:image`, MusicGroup JSON-LD `image`, press.html, and sitemap.xml image:image.
- **OG title simplified** — `og:title` / `twitter:title` changed from "MonkeyMan — Oakland DJ" to just "MonkeyMan" so iMessage/Slack/Twitter cards lead with the brand name (the browser `<title>` kept the long SEO-friendly string for search results). `og:description` updated to "Bay Area DJ. House · Funk · Soul · No Requests."
- **Structured venue + collab data** — two new JSON-LD `ItemList` blocks: `#venues` (20 `Place` entities with city/state) and `#shared-decks` (5 `MusicGroup` entities). Both reference `#musicgroup` via `about`, so Google connects the lists to MonkeyMan's main entity without hard outbound links cluttering the page.
- **Contact form placeholder** updated: "Tell us about your event, date, venue…" → "What's the event, venue, vision, vibe…?"
- **Electric purple glow system** — new `--glow: #b24dff;` + `--glow-rgb` CSS variables drive a unified hover treatment across the site.
  - Hero logo now pulses a soft purple drop-shadow (`@keyframes logoPulse`, 3.2s ease-in-out; disabled under `prefers-reduced-motion`).
  - `Get Groovy` hero CTA, `Send It` form button, social-links sidebar, nav links, venue names in the marquee, shared-decks cards, and music cards all pick up the purple glow on hover.
- **Polaroid lift + tilt hover** — every polaroid in the main gallery now lifts (`translateY(-8px)`), scales (`1.03`), and tilts more pronounced (odd −1.5°, even +1.5°, 3n −0.8°) on hover. About-polaroid unchanged.
- **New venues** in the marquee + press page + llms.txt: Monterey Pride (inserted after Days Like This), Kilowatt, MHAH Gallery, Paris 75, Oakland Art Library, Asiento, Free*Party, High 5 Rooftop Bar, Town Bar & Lounge. Existing venue order preserved; new ones appended after.
- **Cherry Pie** added to Shared the Decks With (San Francisco, CA). Bio and llms.txt updated to include Cherry Pie.

### Changed
- **"Shared the Stage With" → "Shared the Decks With"** (index + press + llms.txt + bios).
- **Removed the "Email Directly" sidebar card** from the Connect section. Booking now flows through the form only. Orphan CSS (`.email-display`, `.copy-email-btn`) removed.

### Notes
- v3.1 snapshot saved to `versions/index-v3.1-purpleglow-20260414.html`.

---

## [v3.0] — 2026-04-14 — Rebrand: logo, tagline, Fugaz One, flyers

### Added
- **Hand-drawn MONKEYMAN logo** (`DJMonkeyMan_logo.png` → `img/logo.png` + `.webp`; trimmed whitespace, optimized for web). Used in hero (replaces text h1) and footer.
- **Small footer variant** (`img/logo-footer.png` + `.webp`).
- **New "M" favicon** — regenerated all sizes (16, 32, 180, 192, 512, .ico) from `MonkeyMan_M_Favicon.png`, centered on brand-black background with comfortable padding. Old text-M `favicon.svg` reference removed.
- **Poster / flyer artwork** in the carousel — five event flyers (`img/poster-*.jpg` + `.webp`) alternating with digital performance shots. Originals preserved in `posters-flyers/`.

### Changed
- **Tagline** — "Funk · Disco · Underground House · Classics" → **"House · Funk · Soul · No Requests"** everywhere it appears (title, OG/Twitter, JSON-LD, hero sub, about tags, press quick facts, EPK alt, webmanifest, llms.txt summary).
- **Bios updated** (index + press + llms.txt) — "rooted in house, funk, and soul — no requests."
- **Hero CTA** — "Listen Now" → **"Get Groovy"**
- **Section title font** — Space Grotesk → **Fugaz One** (heavier, more bold-poster feel that matches the new logo)
- **Carousel moved** — was nested inside Gallery (below polaroids). Now its own `#carousel` section between Shared the Stage With and Music.
- **Tightened vertical rhythm** — reduced section padding across the board to tighten the desktop flow:
  - `#about` 120 → 80/60
  - `.shared-section` 80 → 50/20
  - `#music`, `#video`, `#gallery` 100 → 60
  - `#connect` 100/60 → 70/50
  - `.venues-section` margin-top 80 → 60

### Notes
- Original `posters-flyers/` folder kept untouched; optimized copies live in `img/`.
- Original full-size `DJMonkeyMan_logo.png` and `MonkeyMan_M_Favicon.png` preserved at repo root per request.
- v3.0 snapshot saved to `versions/index-v3.0-rebrand-20260414.html`.

---

## [v2.0] — 2026-04-13 — SEO, discoverability, and performance overhaul

Site is fully live and functional at this point. No content was dropped — this is a pure additive / polish pass.

### Added
- **SEO meta tags** — full canonical, Open Graph, Twitter Card, theme-color, description
- **JSON-LD structured data** — `MusicGroup` + `WebSite` schemas so Google/LLMs can surface MonkeyMan as an artist (genres, booking email, Oakland location, social profiles)
- **robots.txt** — allow all, explicit allow for major AI crawlers (GPTBot, ClaudeBot, PerplexityBot, Google-Extended), sitemap reference
- **sitemap.xml** — homepage + press page + image sitemap
- **llms.txt** — emerging standard (Jeremy Howard proposal) for LLMs: full bio, genres, venues, booking, socials, site structure
- **humans.txt** — team/site credits in the classic humans.txt format
- **Favicons** — SVG + PNG at 16, 32, 180 (Apple touch), 192, 512, plus .ico; generated from a branded `M` glyph
- **site.webmanifest** — PWA manifest so the site can be saved to home screen on mobile
- **404.html** — branded "Track not found" page with back-to-home CTA
- **press.html** — full EPK / press kit page: quick facts, 50-word bio, 100-word bio, venues, shared stages, radio features, EPK poster download, press photos grid, booking CTAs
- **Skip-link + `<main>` landmark** — accessibility for keyboard + screen reader users
- **Keyboard + touch/swipe lightbox nav** — Esc to close, arrow keys to paginate, swipe on mobile, focus returned to invoking image on close
- **WebP hero images** — served via `<picture>` element with JPG fallback; ~40% smaller than JPG on average
- **LCP preload** — hero-scenic preloaded (both WebP and JPG) with `fetchpriority="high"` for instant largest-contentful-paint
- **`prefers-reduced-motion` support** — disables carousel animation for users who request it
- **Print styles** — `@media print` hides decorative elements, keeps bio/contact readable
- **Footer nav** — Booking, Press, Sitemap links for discoverability
- **versions/ folder** — snapshots of index.html at each milestone

### Changed
- Footer credit updated to "web design + photos by cweird" linked to cweird.com

### Pending (user action)
- Push to GitHub: `git push origin main --tags`
- Enable "Enforce HTTPS" in GitHub Pages settings once the TLS cert finishes provisioning (10–60 min after custom domain setup)

---

## [v1.0-live] — 2026-04-13 — Initial live site

First version pushed to monkeyman.io via GitHub Pages with custom domain.

### Included
- Single-page portfolio: Hero carousel (5 digital shots), About, Polaroid gallery, Digital carousel, Music (SoundCloud + Twitch + Linktree + radio), Video, Venues marquee, Connect form
- Brand system: Space Grotesk + Inter, dark `#0a0a0a` with gold accent `#e8a849`
- Hero carousel with 5 images on 30s crossfade loop, brightness/saturation toned down
- Polaroids retain their authentic in-camera borders — no fake CSS borders added
- Digital photos displayed in a separate horizontal-scroll carousel (no fake borders)
- Subtle tilt/angle on the first Polaroid
- Lightbox for Polaroids and digital shots
- 5 selected hero images: IMG_6789, IMG_6467, IMG_4849, IMG_6476, IMG_4839
- All photography by cweird
