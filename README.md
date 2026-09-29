**Preview URL:** [https://kasim-landing.vercel.app/](https://kasim-landing.vercel.app/)

# HW5 — Landing Page for Kasim Aslam: Right Hand Program

Day 5 · Funnels, Vibe Coding & Branding · Pareto Talent Bootcamp

**One offer:** the Right Hand Program (Pareto Talent) · **One audience:** 7- and 8-figure founders
who are the bottleneck in their own company · **One action:** Apply for a free Matching Call →
every button scrolls to the embedded GoHighLevel lead form at
[#apply](https://kasim-landing.vercel.app/#apply)

Built with Claude Code: plain HTML + CSS + a small inline script, no framework. The lead form is a
GoHighLevel embed (iframe + `form_embed.js`). Every fact comes from
the Kasim Aslam Second Brain (HW3) and cites its source file. The Second Brain itself is not in
this repo.

---

## 1. Process files (in the order they were made)

| Step | File | What's in it |
|---|---|---|
| Spec | [docs/HW5_Landing_Page_Instructions.md](docs/HW5_Landing_Page_Instructions.md) | The homework instructions followed |
| 1 · Brief | [docs/01_brief.md](docs/01_brief.md) | One offer, one audience, one action, 3 proof points, UNVERIFIED list |
| 2 · Offer | [docs/02_offer.md](docs/02_offer.md) | Grand Slam Offer: 5 cards, value equation, stack, guarantee type, MAGIC name |
| 3 · Inverse interview | [docs/03_inverse_interview.md](docs/03_inverse_interview.md) | Prompt + 20 questions with sourced answers |
| 4 · Copy | [docs/04_copy.md](docs/04_copy.md) | Copy for all 9 sections, written before the build |
| 5 · Brand | [docs/05_brand.md](docs/05_brand.md) | Logo, favicon, palette, fonts, icons, image prompts + log |
| 6 · Build prompts | [docs/06_prompts.md](docs/06_prompts.md) | Build prompt, iterations 1–4, QA results |
| Page | [index.html](index.html) · [styles.css](styles.css) | The landing page |

## 2. Prompts

| Prompt | Where |
|---|---|
| Brief | [docs/01_brief.md](docs/01_brief.md) (top of file) |
| Inverse interview | [docs/03_inverse_interview.md](docs/03_inverse_interview.md) (top of file) |
| Copy | [docs/04_copy.md](docs/04_copy.md) (top of file) |
| Build + iterations 1–4 | [docs/06_prompts.md](docs/06_prompts.md) |
| Image prompts (3) | [docs/05_brand.md](docs/05_brand.md), section 6 |

## 3. Assets

| Asset | File / value | Notes |
|---|---|---|
| Logo | [assets/logo.svg](assets/logo.svg), [assets/logo-light.svg](assets/logo-light.svg) | Wordmark "Right Hand Program" in PT Serif Bold, converted to vector paths. Original, not Pareto's logo |
| Favicon | [assets/favicon.svg](assets/favicon.svg) | "RH" monogram, Brass on Forest Ink. Checked at 32 px and in an Edge tab |
| Palette | Forest Ink `#1C2B25` · Brass `#C99A56` · Paper `#F5F0E7` | Ink ↔ Paper 13.01:1, Ink ↔ Brass 5.80:1. Brass is never text on Paper (2.25:1) |
| Fonts | **PT Serif & Lato** ([fontpair.co](https://fontpair.co/fonts/google/pt-serif)) | PT Serif 700 + italic 400 for headings, Lato 400/700 for body. Both OFL, via Google Fonts |
| Icon set | **Lucide** (`lucide-static` v1.48.0, ISC) | Inline SVG only: calendar-check, clipboard-list, users, handshake, clock, eye-off, graduation-cap, user-cog, bot, check, shield-check |
| Image 1 | [assets/img/hero.jpg](assets/img/hero.jpg) | Hero. AI-generated (ChatGPT), prompt in [05_brand.md](docs/05_brand.md) |
| Image 2 | [assets/img/problem.jpg](assets/img/problem.jpg) | Problem. AI-generated (ChatGPT), prompt in [05_brand.md](docs/05_brand.md) |
| Image 3 | [assets/img/final-cta.jpg](assets/img/final-cta.jpg) | Final CTA. AI-generated (ChatGPT), prompt in [05_brand.md](docs/05_brand.md) |

Same office across the three images, telling the story: calm (hero) → overwhelmed (problem) →
handoff (final CTA).

The images are scenes only: no faces, no real people, no text, nothing from Google Search.

## 4. Offer summary

Full version: [docs/02_offer.md](docs/02_offer.md).

| Card | Summary |
|---|---|
| Audience | 7- and 8-figure founders/CEOs who are the bottleneck in their own company |
| Problem | "You don't have a people problem. You have a delegation problem." Nobody trains the founder, and a 9/10 assistant still has to be watched |
| Solution | A full-time, AI-powered Right Hand inside a complete delegation system, targeting 40+ hours back in 30 days |
| Bonuses | The 7 real components, plus one **Proposed** bonus (a written delegation plan after the Matching Call) |
| Guarantee | Freedom 40 (lead) · Matching · Lifetime Replacement. All three are real |

- **Value equation:** Dream outcome = 40+ hours back in 30 days, and nobody to monitor ·
  Likelihood = 93% retention at 12 months, 100+ founders, top 1% of 1,000+ applicants ·
  Time delay = 3 candidates within 24 hours · Effort = no contract until you're excited; a
  Success Manager runs HR.
- **Stack:** Product (the Right Hand) → System (Mastermind, bootcamp + training, Second Brain OS,
  Success Manager) → Community (100+ founders, 250+ operators).
- **Guarantee type:** Conditional. Freedom 40 applies when the founder follows the plan.
- **Scarcity / urgency:** selectivity only (top 1% of 1,000+ applicants). No fake deadlines or spot counts.
- **Name:** the official "Right Hand Program" is used on the page, with "Freedom 40" as the hook. A MAGIC
  variant is documented as **Proposed**.
- **Price shown:** $36,000 a year ($3,000 a month) + a one-time $3,000 placement fee.

## 5. What works / what doesn't / what I'd improve

**What works**
- The hero stands alone above the fold (375×667, 1280×720, 1440×900): promise, one proof number,
  CTA, and the guarantee condition as a footnote.
- Every claim is traceable to a Second Brain file. Where sources disagree, the number stays off
  the page (exit count, businesses count, founding year, CEO title).
- One CTA, one destination, everywhere: every button scrolls to the embedded lead form (`#apply`),
  so the visitor never leaves the page.
- A consistent brand system: 3 colours, 1 font pair, 1 icon set. Motion is subtle and switched
  off under `prefers-reduced-motion`.
- QA was automated: the rendered page was checked line by line against `04_copy.md` (84/84), and
  hero fold heights were measured at each size.

**What doesn't (yet)**
- No testimonials or case studies. There are none in the Second Brain, so social proof relies on
  numbers and community names.
- The "Trusted by" communities are named as on paretotalent.com, but the exact relationship with
  each is unverified.
- Section 4 shows the Matching Call as step 1, before the PI assessment. That order is inferred,
  not sourced.
- No design references were collected, and the palette wasn't pulled with CSS Peeper. It was
  designed directly and contrast-checked.
- The embedded GoHighLevel form keeps its own styling (white card, blue button) until its colours
  are changed in GoHighLevel; the page's CSS can't restyle the iframe.
- Content below the hero fades in on scroll, so some full-page screenshot tools capture those
  sections blank unless the page is scrolled first.

**What I'd improve**
- Ask Kasim to settle the open conflicts (exits, businesses built, founding year, CEO title) and
  for 2–3 real client results or testimonials.
- Add a real case study to section 6 next to Ivan's story.
- Collect references and check the palette and spacing against them.
- Convert the images to WebP/AVIF and add `srcset`.
- Add Microsoft Clarity to see real scroll depth, and A/B test the hero headline.

## 6. UNVERIFIED / Proposed items

| Item | Label | Where |
|---|---|---|
| Written delegation plan after the Matching Call | **Proposed — not part of the current offer** | Offer section (labelled on the page) |
| MAGIC name "The Freedom 40 Right Hand Program: 40 hours back in 30 days for 7- and 8-figure founders" | **Proposed** | [02_offer.md](docs/02_offer.md) only, not on the page |
| Relationship with Genius Network, Lifestyle Investor, Front Row Dads, Driven Mastermind | UNVERIFIED | Social proof (names only) |
| Matching Call as the first step before the PI assessment | UNVERIFIED (inferred order) | How it works |
| Matching Call length and format | UNVERIFIED | Not described |
| Weekly Mastermind calls required or optional | UNVERIFIED | Not stated |
| What the audience's week looks like | UNVERIFIED | Left out |
| Contents of the 7 Laws of Delegation | UNVERIFIED | Name only |
| "Not for founders who won't delegate" | Our framing | [03_inverse_interview.md](docs/03_inverse_interview.md), not on the page |
| Exit count, businesses count, Pareto founding year, CEO title | Open source conflicts | Kept off the page |
