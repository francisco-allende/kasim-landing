# 06 — Build Prompts and Iterations

Spec: `docs/HW5_Landing_Page_Instructions.md`, section 6. Built with **Claude Code** (plain HTML/CSS).

---

## Build prompt (step 4)

```
Go with step 4, the build (spec section 6):
- index.html + styles.css + assets/. Plain HTML/CSS, no framework.
- Use docs/04_copy.md exactly. Don't rewrite it, and don't render the italic build notes.
- Only the 3 palette colours, PT Serif + Lato via Google Fonts, Lucide icons only
  (inline SVG from lucide-static).
- The 9 sections in order. The hero works alone above the fold: promise, proof
  number, CTA, footnote.
- One CTA style, same link everywhere, opens paretotalent.com/matching.
  No navigation that leaves the page.
- Mobile-first, semantic HTML, alt text on every image, favicon in <head>,
  <title> + meta description.
- If references exist, match their spacing and hierarchy, not their content.
Then run the QA checklist from spec section 6, tell me what fails, and log this
prompt in docs/06_prompts.md. Don't commit yet.
```

**Result (first build):** `index.html` + `styles.css`. Nine sections in order. Dark hero and final
CTA with a split layout on desktop (text on a solid Forest Ink column, image beside it) and
stacked on mobile. Lucide icons inlined from `lucide-static` v1.48.0. There are no references in
`docs/references/` yet, so none were matched.

## Iterations

| # | Change | Why | Prompt / trigger |
|---|---|---|---|
| 1 | Desktop hero: h1 capped at `clamp(2.25rem, 1rem + 2.4vw, 3.125rem)`, logo margin 40 → 28 px, lead 1.1875 → 1.125rem | QA: at 1280×720 the proof line (774 px) and the footnote (799 px) fell below the fold. After the change they end at 637 and 662 px | Self-QA during the step 4 build (no separate user prompt) |
| 2 | More personality, still premium: italic Brass hero line, editorial section markers, dark social-proof band with count-up, pull quote, check / shield-check icons, dark price block, scroll fade-ups, card hover lift, mobile sticky CTA | Personality without breaking the brand rules or the copy | Prompt below |

| 3 | Section markers added to `04_copy.md`; sticky bar hidden while the final CTA is in view; community dividers fixed on wrap | Keep the copy file the source of truth; avoid two CTAs on screen at the bottom; no stray divider | Prompt below ("Iteration 3 prompt") |

### Iteration 3 prompt

```
Decisions:
- Add the section markers to docs/04_copy.md so the copy file stays the source of truth.
- Hide the sticky bar when the final CTA section is in view.
- Fix the stray divider when the community names wrap.
- Favicon confirmed in a real browser (Edge tab shows the RH monogram).
Log this as iteration 3 in docs/06_prompts.md and commit: "Step 4: iteration 3".
```

**Implementation notes (iteration 3):**
- `04_copy.md`: a `**Section marker:**` line in sections 2–9 (01 — Track record … 08 — Next step).
- Sticky bar: a single IntersectionObserver watches the hero and the final CTA. The bar shows only
  when neither is in view.
- Community row: each name has its own left rule. The list is shifted left 17 px inside an
  `overflow: hidden` wrapper, so the rule of whichever name starts a line is clipped. The " · "
  separators stay in the text but are visually hidden (screen-reader only).

**QA after iteration 3:** copy 84/84 lines (now including the 8 markers). Sticky bar: hidden on
the hero, shown mid-page, hidden at the final CTA. Dividers checked at 320, 375, 414, 768 and
1280 px: the first name on every line has its rule clipped. Favicon confirmed by the user in Edge.

### Iteration 2 prompt

```
Iteration 2: more personality, still premium and corporate.
Keep every brand rule (3 colours, PT Serif + Lato, Lucide only) and the copy word for word.

1. Hero: set "Or your next month is free." in PT Serif italic 400, in Brass.
   Add a subtle fade-up on load for the hero text (staggered, 0.6s).
2. Editorial eyebrows: add small section markers above each h2, like "01 — The problem",
   in uppercase Lato with a short Brass rule (Brass only on dark sections;
   Forest Ink on light).
3. Social proof: turn it into a dark band. Big Brass numbers with a count-up animation
   when they scroll into view. Community names in a row, separated by thin rules.
4. Problem: pull the line "Someone who gets 9 out of 10 things done isn't 90% useful."
   into a large italic serif pull quote with a Brass left border (it's already in the
   copy, so no new words).
5. Offer: use Lucide "check" icons instead of bullets, and make the price the visual
   anchor of the card (big serif). Guarantees: add Lucide "shield-check" to each card.
6. Motion: gentle fade-up on scroll for every section (IntersectionObserver),
   subtle hover lift on cards. Everything off under prefers-reduced-motion.
7. Mobile: a sticky bottom bar with the same CTA, shown only after the hero
   scrolls out of view.

Keep the hero above the fold at 375×667 and 1280×720. Re-run the QA checklist,
log this prompt as iteration 2 in docs/06_prompts.md, then commit:
"Step 4: build (iterations 1–2)".
```

**Implementation notes (iteration 2):**
- Section markers `01 — Track record` … `08 — Next step` sit above the 8 h2s (the hero has an h1
  and already has its eyebrow). **These marker labels are the only words on the page that are not
  in `04_copy.md`.**
- The pull quote is the existing sentence moved out of its paragraph (not duplicated). It is a
  styled `<p>`, not a `<blockquote>`, so it isn't presented as a quote from someone else.
- Count-up: the final values (100+, 93%, 650+) are in the HTML, and JS only animates them. $0 stays static.
- Community separators: the " · " stays in the text for screen readers and the copy; a 1 px rule
  replaces it visually.
- Price: moved into a Forest Ink block at the bottom of the offer card (big PT Serif, Paper text,
  Brass CTA).
- Reveal-on-scroll hides content only when JS runs (`html.js`). With reduced motion or no
  IntersectionObserver, everything is visible immediately.
- Sticky bar: under 720 px only. It's hidden (`visibility: hidden`, `aria-hidden`, `tabindex=-1`)
  until the hero leaves the viewport. Body gets 80 px bottom padding so the bar never covers the final CTA.

**QA after iteration 2:** hero above the fold at 375×667 (footnote ends at 576 px), 1280×720
(662 px) and 1440×900 (720 px). Copy 76/76. Sticky bar hidden at the top and shown after the
hero, never on desktop. Count-up ends at 100+ | 93% | 650+ | $0. Reveals 8/8 visible after
scrolling. Under reduced motion: no hero animation, reveals at opacity 1, card transitions 0 s.

## QA method (step 4)

- Rendered with headless Microsoft Edge via `puppeteer-core` at 375×667 (mobile emulation),
  1280×720 and 1440×900. Measured the bottom of the CTA, proof and footnote against the viewport height.
- Copy check: every copy line in `04_copy.md` (excluding italic notes and Sources) was compared
  with the rendered page text: 76/76 lines match.
- Checked: CTA hrefs, non-CTA links, alt attributes, `<title>`, meta description, favicon link,
  colours used in the CSS, external URLs, `<nav>` count.
