# CLAUDE.md — My Vast Oceans Website

This file gives Claude Code everything it needs to update the myvastoceans.com website. Read this before making any changes.

---

## Project Overview

- **Live site:** https://myvastoceans.com
- **Repo:** https://github.com/christopherflintoft-hash/mvo-site
- **Hosting:** GitHub Pages (auto-deploys from `main` branch)
- **DNS/CDN:** Cloudflare
- **Branch to edit:** `main` — changes go live automatically after a few minutes

---

## File Structure

```
mvo-site/
├── index.html   ← The entire website (single HTML file, all CSS and JS inline)
├── CNAME        ← Sets the custom domain (myvastoceans.com) — do not edit
└── CLAUDE.md    ← This file
```

Everything — HTML, CSS, and JavaScript — lives inside `index.html`. There are no separate stylesheets or script files.

---

## Design System

**Colours**
- Background dark navy: `#0d1117` (approx)
- Primary accent (gold/amber): `#c9a84c` (used for highlighted text, numbers, borders)
- Body text: `#e8e8e8` / white
- Section backgrounds alternate between dark navy and slightly lighter dark tones
- Card backgrounds: semi-transparent dark with subtle border

**Fonts**
- Google Fonts: `Cormorant Garamond` (headings/display) and `Inter` (body)
- Headings use light/thin weights for elegance
- Body text uses Inter at regular weight

**Tone & style**
- Premium, nautical-inspired, understated luxury
- Minimal decorative elements; whitespace-heavy
- All copy is professional and direct — avoid buzzwords and fluff

---

## Site Sections (in order)

1. **Nav** — Logo (top left, links to `#hero`), menu links, "Get in touch" CTA button
2. **Hero** — Full-screen with background image, main headline and subheadline, CTA button
3. **The Reality** — Stats section with key metrics (73%, 80%, 5x, 25+)
4. **What We Do (Services)** — Three service cards: AI Strategy & Readiness, Fractional AI Leadership, Transformation & Capital Advisory
5. **How We Work (Approach)** — Four steps: Understand → Prioritise → Mobilise → Sustain
6. **Where We Operate (Sectors)** — Industry tags: Healthcare, Media & Sport, Commercial Property, Creator Economy, SaaS & Platforms, Ecommerce, Retail & Consumer
7. **Who We Are (The Navigators)** — Team bios for Christopher Flintoft and Patrik Molander with circular profile photos
8. **Contact/Footer** — Email, LinkedIn link, copyright

---

## Navigation Menu Items

- The Reality
- Services
- Approach
- Sectors
- The Navigators
- Get in touch (CTA button, styled differently)

Each nav item links to its section via anchor (e.g. `#services`, `#approach`).

---

## Team Members

**Christopher Flintoft** — Principal
- 25 years navigating technology inflection points
- Founded and exited 3 businesses, operated across 40+ countries
- LinkedIn: https://www.linkedin.com/in/christopherflintoft/

**Patrik Molander** — Senior Technology Executive
- Deep experience across start-ups, global consulting, large enterprise transformation
- Background in IT architecture, system modernisation, Media & Entertainment and Insurance
- LinkedIn: https://www.linkedin.com/in/pmolander/

---

## Images

Profile photos and the hero background image are embedded as base64 data URIs directly inside `index.html`. There is no separate `/images/` folder.

To update an image:
1. Get the new image file
2. Convert it to base64 (use `base64 -i yourimage.jpg` in Terminal, or an online tool)
3. Replace the existing base64 string in the `src="data:image/jpeg;base64,..."` attribute

---

## Common Update Tasks

### Update body copy or headlines
Find the relevant section by searching for the visible text string. Edit the text directly in the HTML. Keep the same tone — direct, professional, no jargon.

### Add or remove a service card
Services are in the section with `id="services"` (or similar). Each card follows the same HTML pattern with a number, title, and description paragraph. Copy an existing card and modify.

### Add or remove a sector tag
Sector tags are simple `<span>` or similar elements inside the sectors section. Add or remove inline.

### Update team bios
Find the team member's name and edit the surrounding paragraph text. Profile photo updates require a base64 image replacement (see Images section above).

### Add a new nav item
Add a new `<a>` tag in the `<nav>` element, then make sure the target section has a matching `id` attribute.

### Change a colour
Search for the hex code (e.g. `#c9a84c`) and replace. Consider using Find & Replace to catch all instances.

### Update contact details
Email address and LinkedIn URL appear in the footer/contact section. Search for `christopher@myvastoceans.com` to find them.

---

## Deployment

1. Edit `index.html` in this repo (on the `main` branch)
2. Commit the change with a clear message (e.g. "Update hero headline")
3. GitHub Pages auto-deploys — site is live within 2–5 minutes
4. Cloudflare caches the site — if changes don't appear immediately, a cache purge may be needed (log into Cloudflare → myvastoceans.com → Caching → Purge Everything)

---

## Things to be careful about

- The entire site is one file — always make targeted edits and avoid accidentally deleting surrounding HTML
- Base64 image strings are very long — be careful when editing nearby code not to truncate them
- Don't edit the `CNAME` file — it controls the custom domain
- The site uses no build tools, no npm, no frameworks — just plain HTML/CSS/JS
