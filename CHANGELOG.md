# Changelog

All notable changes to monkeyman.io. Versions with `-live` in the git tag were what was live at the time.

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
