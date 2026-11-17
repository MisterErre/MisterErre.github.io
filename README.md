# MisterErre.github.io

Personal site for **Adrian Lorente** — IAM Engineer (Identity Governance & Privileged Access).

Live at <https://misterErre.github.io>.

## What's here

| File | Purpose |
|---|---|
| `index.html` | The whole site. Single file, inline CSS and JS, no build step and no third-party requests. |
| `cv-adrian-lorente.pdf` | Full two-page CV (generated from LaTeX). The only CV published here. |
| `fonts/` | Self-hosted WOFF2 fonts (Latin subset) with their SIL OFL licences. |
| `og-image.jpg` | 1200×630 preview shown when the link is shared on LinkedIn, Slack and so on. |
| `404.html` | Not-found page in the same style. GitHub Pages serves it automatically. |
| `robots.txt`, `sitemap.xml` | Search-engine housekeeping. Bump `<lastmod>` in the sitemap after real content changes. |
| `.nojekyll` | Tells Pages to serve files as-is and skip the Jekyll build. |

A one-page edition of the CV also exists but is deliberately **not** in this
repository. Anything committed here is publicly fetchable whether or not a link
points at it, so the short version stays local and gets sent by hand.

## Editing

Open `index.html` and edit it. There is nothing to compile and nothing to install —
push to `main` and GitHub Pages serves it.

The content mirrors the LaTeX CV, so **if you change a fact here, change it in the
CV too** (and on LinkedIn). Three copies of a career that disagree with each other
is worse than one that is slightly out of date.

## Design notes

**One idea: the neon sign and the paperwork.** The hero is the sign: the glowing
name, its flicker, the synthwave floor and CRT scanlines. That is the only loud
thing on the page. Everything below it is a calm CV on a dark page. Keep it that
way when adding content; most "make it pop" ideas belong in the hero or nowhere.

- Palette and type live in the `:root` block at the top of the `<style>` tag.
  `--red` is the primary neon, `--cyan` the secondary, `--violet` the accent.
  Below the hero, colour only carries meaning: dates (cyan), roles (soft red)
  and the semantic tag colours below.
- Fonts: `Bevan` for the name and headings, `Inter` (weight 400; 300 goes
  spindly as light-on-dark text on phones) for everything you read, and
  `Share Tech Mono` only for data: dates, tags and contact handles.
  They are self-hosted from `fonts/` on purpose: loading them from Google's CDN
  sends every visitor's IP to Google, which German courts have ruled a GDPR
  breach without consent. Do not reintroduce the Google Fonts `<link>`. Fresh
  copies come from the `@fontsource` npm packages.
- Things deliberately **not** on the page, because they read as a generated
  template: tracked ALL-CAPS labels, numbered section markers (the sections are
  not a sequence), stat tiles, a card around every block, fade-in on scroll,
  hover lifts, and role-play copy ("arsenal", "primary weapon", "access
  granted"). Labels are sentence case.
- Layout: on wide screens each section name sits in a left column with the
  content beside it, like a printed CV; under 900px they stack. The phone
  breakpoint (640px) sizes the hero to its content, keeps the nav on one line
  and turns contact rows into full-width tap targets (56px).
- The only motion is in the hero (grid drift, flicker), and it switches off
  under `prefers-reduced-motion`. The grid floor is `.horizon::before`: the
  perspective camera sits on the horizon (top edge of `.horizon`) and the drift
  animates `transform`, so it stays off the main thread.
- The headings keep the old anchor ids (`#background`, `#arsenal`, `#log`,
  `#credentials`) so links shared before the rename still land.
- There is a print stylesheet: printing the page gives an ink-on-white CV.
- If you change the hero, regenerate `og-image.jpg` (any 1200×630 screenshot of
  the hero will do).
- Company names in the experience timeline are deliberately **not** uppercased —
  brands like *iC Consult* carry their own casing.
- **Tag colours are semantic, not decorative.** Keep them that way or the whole
  thing reads as random:
  | Class | Colour | Means |
  |---|---|---|
  | `.tag.hot` | red | Platforms and products actually operated |
  | `.tag.cool` | cyan | Engineering, cloud and tooling |
  | `.tag` | grey | Standards, protocols and processes |
  | `.tag.sector` | violet | Industries delivered into |
  | `.tag.soft` | amber | Human skills — warm on purpose, so the one non-technical row does not read as another stack |

  The colour key under *Skills* documents the first three for the reader. In the
  timeline each tag row carries a label (`Stack` / `Sectors`) so a row of
  technologies is never confused with a row of industries.
