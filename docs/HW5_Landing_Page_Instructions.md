# HW5 — Landing Page for Kasim Aslam: Build & Deploy Instructions

Day 5 · Funnels, Vibe Coding & Branding
Deliverable: a live **preview URL** + the **prompts** + the **assets** used (one submission link).

> **Order matters.** Brief → Offer → Copy → Brand → Build → Deploy → Package.
> Nothing gets built until the copy for every section is written.
> "A landing page is an offer. Every section on it exists to fight one objection." (Day 5 slides)

---

## 0. Checklist map (what proves each point)

| Checklist point | Proof in the submission |
|---|---|
| Brief from Kasim's Second Brain (1 offer, 1 audience, 1 action) | `01_brief.md` with Second Brain file citations |
| Grand Slam Offer defined first | `02_offer.md` (5 cards + value equation + stack + name) |
| Inverse interview (20 questions, answered) | `03_inverse_interview.md` (prompt + 20 Q&A) |
| Copy for every section before building | `04_copy.md` (committed before the first build commit) |
| Brand system: logo + favicon | `/assets/logo.svg`, `/assets/favicon.svg` |
| Palette of 2–3 colours | `05_brand.md` + CSS variables |
| One font pair from Google Font Pairs | `05_brand.md` (pair name + link) |
| 3+ images, AI-generated or licensed stock | `/assets/img/*` + prompt or licence for each |
| One icon set (not one-off icons) | Single set, named in `05_brand.md` |
| 8+ sections | Live page (9-section anatomy below) |
| Preview URL + prompts + assets | `SUBMISSION.md` linking all of the above |

---

## 1. Brief (one offer, one audience, one action)

Run it inside the **Kasim Aslam — Second Brain** Project (HW3). Every fact needs a `Source:` line.

**Prompt:**
```
Using only the Second Brain files, write a one-page landing page brief for Kasim Aslam.
Output exactly:
- ONE offer (name, what it is, price) — cite the file
- ONE audience (business stage, role, what a normal week looks like) — cite the file
- ONE action (the single CTA the visitor takes)
- 3 proof points we can show (numbers, stories, credentials) — cite each
- Anything you had to assume, listed under "UNVERIFIED"
Do not use general knowledge. If something isn't in the files, say so.
```

**Starting draft (verify against the Second Brain before using):**

| Field | Draft | Source / status |
|---|---|---|
| Offer | Right Hand Program (Pareto Talent) | `right-hand-program-pricing` (HW3) |
| Price | $36,000/yr + $3,000 one-time placement fee | `right-hand-program-pricing` (HW3) |
| Audience | Founders who are the bottleneck in their own business | ⚠️ UNVERIFIED — confirm in `02_Offer` |
| Action | Book a call | ⚠️ UNVERIFIED — confirm the real CTA on paretotalent.com |

Rules:
- One offer only. Don't mix Pareto Talent, Driven Mastermind and Kasim's consulting on one page.
- Known conflicts (founding year, number of EAs placed, number of exits): keep those numbers off
  the page unless `source-conflicts` resolves them.
- This is a **landing page** (one page, one goal), not a funnel or a website. No nav links that
  pull people away from the one action.

---

## 2. Grand Slam Offer (Alex Hormozi)

Define the offer before any design. Save as `02_offer.md`.

**A. The five cards** (from the slides)

| # | Card | Rule | Answer + source |
|---|---|---|---|
| 1 | Audience | The exact person: business stage, role, a normal week. Not "everyone who wants to grow." | |
| 2 | Problem | The ONE pain they'd pay to remove, in their own words. Not a list of five. | |
| 3 | Solution | The outcome they walk away with, not the tool or feature. | |
| 4 | Bonuses | Real value that knocks out the next objection. Nothing bolted on. | |
| 5 | Guarantee | Removes risk from their side. Say plainly what happens to their money or time. | |

**B. Value equation** (push the top up, push the bottom down)
```
Value = (Dream Outcome × Perceived Likelihood) ÷ (Time Delay × Effort & Sacrifice)
```
| Lever | Slide rule | Our version | Source |
|---|---|---|---|
| Dream outcome ↑ | Big and specific ("inbox zero by 9am"), not "save time" | | |
| Likelihood ↑ | A number beats an adjective ("312 founders placed") | | |
| Time delay ↓ | "First draft brief tomorrow morning" beats "results in 90 days" | | |
| Effort ↓ | "Answer five questions, we handle the rest" | | |

**C. Value stack** (solve every problem, not just one)
1. **The product:** the core offer (they don't have it yet).
2. **The system:** step-by-step so they know what to do first.
3. **The community:** why people quit even when the product works.

**D. Guarantee type** — pick one and say why: Unconditional · Conditional · Outcome-based · Anti-guarantee.

**E. Scarcity / urgency** — only if real (cohort size, a real deadline). Fake scarcity is off.

**F. Name the offer (MAGIC)** — use 3–5 of: Magnet · Avatar · Interval · Container · Goal.

⚠️ Any bonus, guarantee, scarcity, urgency or new name that isn't in Kasim's real offer must be
labelled **"Proposed — not Kasim's current offer"** in `02_offer.md` and in the submission.

---

## 3. Inverse interview (20 questions)

Claude asks, you answer. Run it in the Second Brain Project so answers stay sourced.

**Prompt:**
```
You are a direct-response copywriter trained on Alex Hormozi's Grand Slam Offer.
Ask me 20 questions you'd need to build me a perfect offer for Kasim Aslam's [OFFER].
Cover the five cards (audience, problem, solution, bonuses, guarantee), the four
value-equation levers, the value stack, scarcity/urgency and the offer name.
Number them. Ask all 20 at once.
```
Answer each using the Second Brain. Add `Source:` or `UNVERIFIED` to every answer.
Save prompt + 20 Q&A as `03_inverse_interview.md`.

---

## 4. Copy for every section (write it all before building)

**Hero rule from the slides:** fewer than 6 in 10 visitors scroll to the form. Assume nobody
scrolls. The hero must carry the promise, the proof and the action on its own.

**Prompt:**
```
Using 01_brief, 02_offer and 03_inverse_interview, write the full landing page copy
in Kasim's voice (HW2 voice rules). For each section below: the objection it fights,
headline, subhead, body, CTA text if any. One CTA only, same text everywhere.
No invented numbers, testimonials or guarantees. Mark anything unverified.
```

**Sections (9-section anatomy from the slides; minimum 8 required):**

| # | Section | Objection it fights | Must contain |
|---|---|---|---|
| 1 | Hero | "Is this for me?" | Dream outcome headline, subhead, primary CTA, one proof number, hero image |
| 2 | Social proof | "Can I trust them?" | Names, logos or a number, each sourced. No fake testimonials |
| 3 | Problem | "Do they get me?" | The one pain, in the audience's words |
| 4 | How it works | "What happens next?" | 3–4 steps, icons from the set |
| 5 | Benefits | "What changes for me?" | Outcomes, not features, icons |
| 6 | More social proof | "Still not sure." | Deeper proof (story, case, quote from a public source) |
| 7 | The offer | "What do I get?" | Value stack + price (sourced) |
| 8 | Guarantees | "What if it fails?" | Guarantee (real or labelled "Proposed") |
| 9 | Final CTA | — | Same action as the hero |

Save as `04_copy.md`.

---

## 5. Brand system

"80% inspiration, 20% creativity." Save everything in `05_brand.md` + `/assets`.

**Inspiration first**
- Collect 2–3 reference pages: Dribbble, Behance, or the Facebook Ads Library (proof a page converts).
- Capture full pages with the **Awesome Screenshot** extension to feed into the build prompt.
- Optional: a design-system prompt file (markdown) from the GitHub repo shown in class.
- List the references in `05_brand.md`.

**Logo + favicon**
- A clean **wordmark** is a real logo (slides: Ray-Ban, Chanel). Minimum viable logo, can change later.
- SVG wordmark in the heading font + a monogram mark for the favicon (legible at 32px).
- Don't copy Pareto Talent's real logo.

**Palette (2–3 colours)** — pull real hex codes from a reference site with **CSS Peeper**:
```css
:root {
  --primary:  #______;  /* brand / CTA */
  --dark:     #______;  /* text / backgrounds */
  --accent:   #______;  /* highlights (optional 3rd) */
}
```
Check text contrast ≥ 4.5:1.

**Font pair** — ONE pair from **Google Font Pairs** (fontpair.co). Record heading font, body font, link.

**Images (3 minimum)**
- Licensed stock: **Pexels, Unsplash, Freepik** (save the photo URL + licence).
- Or AI: **ChatGPT**, Midjourney or Freepik AI. Give it a description + style guide + palette
  screenshot, then iterate. Save each prompt.
- **Never from Google Search** (the slides mention a cease-and-desist within 48h).
- No AI images of Kasim's face. Use scenes (calm founder, clean calendar, team call…).
- Log per image: file · section · prompt **or** source URL + licence.

**Icon set** — ONE set: a **Flaticon set**, or Lucide/Phosphor. Emojis are allowed if used
consistently, but a real set proves the checklist more clearly. No mixing.

---

## 6. Build

Slides: **Lovable** (fastest) or **Claude Code** (full control, real files). Using Claude Code.
Expect ~70% on the first attempt and plan **3–5 iterations**. Log every prompt.

**Stack:** `index.html` + `styles.css` + `/assets` (plain HTML/CSS, no framework needed).

**Build prompt (master prompt):**
```
Build a responsive one-page landing page from these files:
- 04_copy.md (use the copy exactly, don't rewrite it)
- 05_brand.md (colours as CSS variables, the font pair via Google Fonts,
  icons only from [ICON SET])
- /assets (logo, favicon, images)
- References: [screenshots] — match their spacing and hierarchy, not their content.
Sections in this order: hero, social proof, problem, how it works, benefits,
more social proof, the offer, guarantees, final CTA.
The hero must work on its own above the fold: promise, proof number, CTA.
One CTA button style, same link everywhere. No navigation that leaves the page.
Mobile-first, semantic HTML, alt text on every image, favicon in <head>,
<title> and meta description set. Only local images from /assets.
```

**Iteration prompts:** keep them one change at a time ("Make the hero headline bigger and move
the proof number under the CTA"). Save them in `06_prompts.md`.

**QA before deploy:**
- [ ] 8+ sections in order (9 planned)
- [ ] Hero stands alone above the fold on desktop and at 375px mobile
- [ ] Copy matches `04_copy.md`
- [ ] Only the palette colours, the 2 fonts, one icon set
- [ ] Favicon shows in the tab
- [ ] Every CTA goes to the same place
- [ ] No unverified fact shown as fact; "Proposed" labels where needed

---

## 7. Deploy (preview URL, no domain needed)

Any tool is accepted. Same workflow as the slides' pipeline, with Vercel in place of Cloudflare:

**Vercel (recommended):**
1. `git init` → commit → push to a **public** GitHub repo `kasim-landing`.
2. vercel.com → Add New → Project → import the repo → Framework: **Other** → Deploy.
3. URL: `kasim-landing.vercel.app`. Every push to `main` redeploys in ~1 minute.

**Netlify (backup, fastest):** app.netlify.com/drop → drag the project folder → instant URL.
(No auto-redeploy; re-drag after each change.)

Daily loop (from the slides): pull → change with Claude Code → check locally → commit + push → live.

Open the URL in an incognito window to confirm it's public.

---

## 8. Submission package (one link)

A screenshot is **not** a submission. Submit ONE link: the public GitHub repo (its README =
`SUBMISSION.md`) or a PDF in HW2 style. It must contain:

1. **Preview URL** (top, clickable)
2. **Prompts:** brief, inverse interview, copy, build + iterations, image prompts
3. **Assets:** logo, favicon, palette, font pair, images (prompt/licence each), icon set
4. **Offer summary:** 5 cards, value equation, stack, guarantee type, name
5. **What works / what doesn't / what I'd improve**
6. **Unverified / Proposed items** list

Repo layout:
```
kasim-landing/
├── index.html
├── styles.css
├── README.md            ← = SUBMISSION.md (preview URL on line 1)
├── assets/  (logo.svg, favicon.svg, img/)
└── docs/
    ├── 01_brief.md
    ├── 02_offer.md
    ├── 03_inverse_interview.md
    ├── 04_copy.md
    ├── 05_brand.md
    └── 06_prompts.md
```

Then: post in **#Homework** (3–5 lines, link, one highlight, "What would you change?") and share
one thing you liked about the class in **#General**.
