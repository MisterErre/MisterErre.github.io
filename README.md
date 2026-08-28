# MisterErre.github.io

Personal site for **Adrian Lorente** — IAM Engineer (Identity Governance & Privileged Access).

Live at <https://misterErre.github.io>.

## What's here

| File | Purpose |
|---|---|
| `index.html` | The whole site. Single file, inline CSS and JS, no build step and no dependencies beyond Google Fonts. |
| `cv-adrian-lorente.pdf` | Full two-page CV (generated from LaTeX). The only CV published here. |

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

- Palette and type live in the `:root` block at the top of the `<style>` tag.
  `--red` is the primary neon, `--cyan` the secondary, `--violet` the accent.
- Fonts: `Bevan` (display), `Share Tech Mono` (labels and data), `Inter` (body).
- Motion (grid drift, flicker, scroll reveals) is disabled automatically under
  `prefers-reduced-motion`.
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

  The legend under *Arsenal* documents the first three for the reader. In the
  timeline each tag row carries a `.taglabel` (`Stack` / `Sectors`) so a row of
  technologies is never confused with a row of industries.
