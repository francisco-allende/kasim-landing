# 05 — Brand System: Right Hand Program

Spec: `docs/HW5_Landing_Page_Instructions.md`, section 5.
Direction: **calm, premium, founder-to-founder.** Think a quiet private office, not a SaaS
dashboard. Deep forest ink, brass, warm paper. No generic SaaS blue.

---

## 1. Inspiration references

| # | Reference | Where | Why | Status |
|---|---|---|---|---|
| 1 | _to add_ | Dribbble / Behance | Premium dark-serif service page | **To do (you):** pick one and capture it with Awesome Screenshot |
| 2 | _to add_ | Dribbble / Behance | Calm hero with lots of negative space | **To do (you)** |
| 3 | _to add_ | Facebook Ads Library | A live, paid landing page for a high-ticket service (proof it converts) | **To do (you)** |

Note: the palette below was **not** pulled with CSS Peeper from a reference site. It was designed
directly and contrast-checked. Once you add references, you can check it against them with CSS
Peeper and adjust.

## 2. Logo + favicon

| File | What | Details |
|---|---|---|
| `assets/logo.svg` | Wordmark "Right Hand Program", Forest Ink `#1C2B25` | Set in **PT Serif Bold** (the heading font). The text is converted to vector paths, so it renders the same everywhere with no font loading. 717 × 77 viewBox. |
| `assets/logo-light.svg` | Same wordmark in Paper `#F5F0E7` | For dark sections (hero, final CTA). |
| `assets/favicon.svg` | "RH" monogram, Brass on Forest Ink, rounded square | PT Serif Bold, paths. Checked by render at 128, 32 and 16 px: legible at 32 px. |

- Original wordmark. It does not copy Pareto Talent's real logo (spec rule).
- How it was made: `opentype.js` converted PT Serif Bold (Google Fonts, OFL) glyphs to SVG paths.
  The generator script is not part of the repo.
- "A clean wordmark is a real logo" (Day 5 slides). Minimum viable logo: it can change later.

## 3. Palette (3 colours)

```css
:root {
  --dark:    #1C2B25;  /* Forest Ink: text on light, dark section backgrounds */
  --primary: #C99A56;  /* Brass: CTA buttons, highlights on dark */
  --light:   #F5F0E7;  /* Paper: page background, text on dark */
}
```

**Contrast (WCAG 2.x, computed):**

| Foreground on background | Ratio | Use | Pass |
|---|---|---|---|
| Forest Ink on Paper | **13.01 : 1** | Body text and headings on light sections | ✓ AA / AAA |
| Paper on Forest Ink | **13.01 : 1** | Text on dark sections (hero, final CTA) | ✓ AA / AAA |
| Forest Ink on Brass | **5.80 : 1** | CTA button label | ✓ AA |
| Brass on Forest Ink | **5.80 : 1** | Proof numbers, eyebrows, icons on dark | ✓ AA |
| Brass on Paper | 2.25 : 1 | **Never text or icons.** Decorative only (rules, fills behind dark text) | ✗ for text |

Rules for the build:
- Only these three colours. Tints and shades are not allowed; use opacity sparingly for borders only.
- On Paper sections, icons are Forest Ink. On dark sections, icons are Brass.
- The CTA button is always Brass with a Forest Ink label, on both light and dark sections.

## 4. Font pair

**PT Serif & Lato**: a pairing listed on fontpair.co.

| Role | Font | Weights | Licence |
|---|---|---|---|
| Headings | **PT Serif** | 700 (and 400 italic, if needed) | Open Font License |
| Body | **Lato** | 400, 700 | Open Font License |

- Pairing link: https://fontpair.co/fonts/google/pt-serif (the "PT Serif & Lato" pairing is shown
  there, linking to https://fontpair.co/fonts/google/lato). Checked 2026-09-28.
- Load via Google Fonts:
  `https://fonts.googleapis.com/css2?family=PT+Serif:ital,wght@0,700;1,400&family=Lato:wght@400;700&display=swap`
- Why: PT Serif gives the calm, bookish authority of a founder writing to a founder. Lato keeps
  the body easy to read on mobile.

## 5. Icon set

**Lucide** (lucide.dev), one set only, no mixing. Package `lucide-static` v1.48.0, **ISC licence**.
Stroke style, 1.75–2 px stroke, colours as in the palette rules above.

| Section | Item | Lucide icon |
|---|---|---|
| 4 · How it works | 1. Book your free Matching Call | `calendar-check` |
| 4 · How it works | 2. Get mapped | `clipboard-list` |
| 4 · How it works | 3. Meet 3 hand-picked candidates | `users` |
| 4 · How it works | 4. Integrate over 30 days | `handshake` |
| 5 · Benefits | Your time comes back | `clock` |
| 5 · Benefits | You stop checking | `eye-off` |
| 5 · Benefits | You get better at delegating | `graduation-cap` |
| 5 · Benefits | HR is off your plate | `user-cog` |
| 5 · Benefits | The AI is already handled | `bot` |

| 7 · The offer | Value stack items (instead of bullets) | `check` |
| 8 · Guarantees | Each guarantee card | `shield-check` |

All names checked against the lucide-static CDN (HTTP 200) on 2026-09-28. `check` and
`shield-check` were added in build iteration 2.

## 6. Images (3, AI-generated in ChatGPT)

Rules: scenes only. No real people's faces, no Kasim, no Ivan, no text, letters, numbers or logos
in the image. Never from Google Search. The files go in `assets/img/`. You generate them.

**Style guide (included in every prompt):** editorial photography, soft natural light, calm and
premium, shallow depth of field. Colour palette limited to deep forest green (#1C2B25), warm brass
(#C99A56) and warm off-white paper (#F5F0E7). No text of any kind, no logos, no faces.
Tip: attach a screenshot of the palette block above when you prompt.

### Image 1 · Hero → `assets/img/hero.jpg`
```
Editorial photograph of a calm, uncluttered founder's office in early morning light. A wide oak
desk with a closed laptop, a single cup of coffee and a closed leather notebook. Deep forest green
wall (#1C2B25), a brass desk lamp (#C99A56) glowing softly, warm off-white paper tones (#F5F0E7)
in the light through a tall window. The feeling: quiet, in control, time to think. Nobody in the
frame. Plenty of empty space on the left third of the image for a headline. Soft natural light,
shallow depth of field, premium and restrained. No text, no letters, no numbers, no logos, no
screens showing content, no faces. Landscape 16:9.
```

### Image 2 · Problem → `assets/img/problem.jpg`
```
Editorial photograph of the same kind of founder's desk late at night, overwhelmed: stacks of
papers, scattered blank sticky notes, an open laptop glowing, a phone lit up face-up on the desk
with blank notification shapes, a half-finished cold coffee. A pair of hands rests on the desk
edge (hands only, no face, no person visible above the wrists). Palette limited to deep forest green
(#1C2B25) shadows, dim brass (#C99A56) lamp light and off-white paper (#F5F0E7) highlights.
The feeling: everything still runs through one person. Moody, cinematic, but not dramatic or dark.
No readable text, no letters, no numbers, no logos, no faces. Landscape 3:2.
```

### Image 3 · Final CTA → `assets/img/final-cta.jpg`
```
Editorial photograph of a handoff: a warm, tidy table by a window at golden hour, two coffee cups
and two chairs facing each other, one closed leather notebook being slid across the table from one
side to the other. Show only the notebook and two hands (no faces, nobody visible above the
wrists). Deep forest green (#1C2B25) background wall, brass (#C99A56) accents in the light and
the cup details, warm off-white (#F5F0E7) linen and paper. The feeling: relief, trust, the work
is in good hands. Soft natural light, shallow depth of field, calm and premium. No text, no
letters, no numbers, no logos, no faces. Landscape 16:9.
```

### Image log (fill in after generating)

| File | Section | Source | Prompt | Iterations / notes |
|---|---|---|---|---|
| `assets/img/hero.jpg` | 1 · Hero | ChatGPT (AI-generated) | Image 1 above | 1 iteration. Empty office, forest-green wall, brass lamp, closed laptop, coffee, notebook. Empty space on the left as asked. No people, no text. |
| `assets/img/problem.jpg` | 3 · Problem | ChatGPT (AI-generated) | Image 2 above | 1 iteration. Night desk, paper stacks, blank sticky notes, blank laptop screen, hands only. No faces, no readable text. |
| `assets/img/final-cta.jpg` | 9 · Final CTA | ChatGPT (AI-generated) | Image 3 above | 1 iteration. Two hands passing a leather notebook across the table (handed rather than slid), two cups, golden hour. No faces, no text. |

## 7. Choices log

| Date | Choice | Why |
|---|---|---|
| 2026-09-28 | Palette: Forest Ink / Brass / Paper | Calm, premium, not SaaS blue. All text pairs pass 4.5:1 |
| 2026-09-28 | Brass never used as text on Paper | Fails contrast (2.25:1) |
| 2026-09-28 | Font pair PT Serif & Lato (fontpair.co) | A serif for authority, a readable sans for the body. Both OFL |
| 2026-09-28 | Wordmark as vector paths, plus a light variant | Renders the same in `<img>` with no font loading; the light variant is for dark sections |
| 2026-09-28 | Favicon "RH" monogram, Brass on Forest Ink | Checked legible at 32 px |
| 2026-09-28 | Icons: Lucide only (ISC) | One consistent stroke set for sections 4 and 5 |
| 2026-09-28 | 3 AI images, scenes, hands at most | Q10: no faces, no real people |
