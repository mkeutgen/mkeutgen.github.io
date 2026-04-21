# mkeutgen.github.io — Claude context

Personal academic blog for Maxime Keutgen De Greef (Princeton AOS PhD student).
Hugo static site, theme: archie, deployed to GitHub Pages.

---

## Key content files and how they relate

| File | Purpose |
|---|---|
| `content/posts/welcome.md` | Main landing post — bio, research summary, links to published work |
| `content/publications.md` | Canonical list of all publications |
| `content/about.md` | Short bio page |
| `content/cv.md` | CV |
| `content/notes/*.md` | Seminar and reading-group notes |

**Consistency rule**: whenever a publication status changes (preprint → published,
new paper added, citation corrected), update **both** `publications.md` and every
mention in `posts/welcome.md`. Check both files automatically — do not wait to be asked.

---

## Notes conventions

### Frontmatter fields (all required)

```toml
+++
title   = "Full descriptive title"
kicker  = "Seminar notes — Speaker Name (Institution)"
deck    = "One sentence: what the talk was about and why it matters."
date    = "YYYY-MM-DD"          # use the event date, not today
tags    = ["tag1", "tag2"]
author  = "Maxime Keutgen De Greef"
toc     = true
+++
```

### Filename convention

`[speaker-lastname]-[short-topic].md` — e.g. `morel-foundation-models.md`,
`wennberg-northern-forests.md`. Never use spaces or special characters.

### Acronyms

Every acronym must be defined on first use in the **body text** (not just in a
section heading or the deck). Format: full form first, abbreviation in parentheses —
e.g. "Solar-Induced Chlorophyll Fluorescence (SIF)". On subsequent uses, the
abbreviation alone is fine.

### References

Use Hugo footnote syntax `[^key]` with full citation at the bottom of the file.
If a full citation is not available at note-taking time, add a `_(to be filled in)_`
note rather than omitting the reference.

### Math

KaTeX is enabled. Use `$ … $` for inline and `$$ … $$` for display math.

### Sidenotes

Available via `{{< sidenote >}} … {{< /sidenote >}}`. Use for asides, Q&A
exchanges, or caveats that would interrupt the main flow.

---

## Writing standards

- All prose is in **English**.
- No unexplained jargon — define technical terms on first use.
- Prefer short, declarative sentences over hedged ones.
- Do not leave stub placeholders in published notes; mark them `draft = true`
  in the frontmatter until they are complete.

---

## Publication record

Author name appears as **Keutgen De Greef, M.** on recent work.
Early publications may appear as *Keutgen* or *De Greef* — this is noted in
`publications.md`.

Current papers (keep this list up to date):

1. **Keutgen De Greef, M.**, Resplandy, L., & Poupon, M. A. (2026). Global eddy
   subduction carbon pump from Argo floats. *Global Biogeochemical Cycles*, 40,
   e2025GB008912. https://doi.org/10.1029/2025GB008912
   — Press: [Phys.org](https://phys.org/news/2026-04-ocean-eddies-carbon.html),
   [Eos](https://eos.org/research-spotlights/eddy-or-not-do-eddies-actually-transport-that-much-carbon)

2. **Keutgen De Greef, M.**, Weltje, G.J., & Gijbels, I. (2024). Estimating rock
   composition from replicate geochemical analyses. *Mathematical Geosciences*, 56,
   1539–1604. https://doi.org/10.1007/s11004-024-10138-5

3. Bouvart, T., et al. (2024). Alunite and kaolinite as geochemical markers in
   active acid sulfate alterations of southern Italy. *Geochemistry*, 126204.
   https://doi.org/10.1016/j.chemer.2024.126204

---

## Git workflow

- Commit and push after every set of changes.
- Commit messages: imperative mood, describe what changed and why in one line.
- Never commit build output (`public/`) or `node_modules/`.
