# Pickup note — Disciple-Making Pathway (vision-cast tool)

_Drop this into a fresh chat to resume._

## BUILD LOG — 2026-06-03 (design pass on index.html)
Major build-out beyond the earlier icon/brand work. All in `index.html`:
- **Hero rebuilt:** eyebrow `SOUTHEAST · DISCIPLE-MAKING PATHWAY` + h1 "Build a
  Disciple-Making Culture from the life of Christ." (Fraunces serif).
- **Hand-drawn squiggle underlines** (SVG, orange `#e07a4f`, `stroke-dashoffset`
  draw animation triggered on scroll-into-view via IntersectionObserver, `.drawn`
  class). One under hero "Culture" (thick, gentle wave), a DIFFERENT-shaped one
  under "Relationships" in the foundation h2 (bouncy multi-hump). Respects
  reduced-motion.
- **Instruction sequence** (`.howto`): left-aligned numbered steps above the
  on-ramps ("Tap a chair… / Tap a tool…"), replaced the old centered hero hint.
- **Chair role** sized to 17px + `white-space:nowrap` so "Disciple-Maker" fits one
  line (all four uniform).
- **Chair icons:** card-background fill + 2.5px ring in each chair's `--cc` (was a
  tinted disc).
- **Circles of Concern** (in the Circles card): luminous→ then flattened to mock
  reference look — flat translucent overlapping circles, **mock names** (Tim/Greg/
  Jason · Mark/Aaron · Joseph Kerr), labels in dark margins (no dots), no glow.
  Fully proportional (aspect-ratio + container queries) → scales TV↔phone.
- **Foundation = "underneath" band:** recessed warmer band w/ inset top shadow +
  a down-chevron chip at the seam (pathway visually rests on it).
- **Responsive chair reflow (4 stages):** each chair+its tools wrapped in `.unit`
  (`display:contents` on wide so the linear spread is unchanged). Breakpoints:
  >1180 linear · ≤1180 2×2 · ≤680 1-col side-by-side · ≤440 1-col stacked.
  On-ramps (thought bubbles) hidden ≤1180 (wide-only flourish — could reflow later).
- **Copy:** closing para → "same pathway / Jesus' next challenge / shared framework";
  Chair-4 detail win → "helping others look more like Jesus"; on-ramp tags → chair
  names (Seeker/Believer/Worker/Disciple-Maker).
- Static design proofs rendered to `/tmp/read/` during the session (not committed).

## RESOLVED 2026-06-03 — icon mapping + contrast
Rendered all six icons (14/15/16/17/10/11). Findings:
- 16 & 17 are GOLD but **incomplete** chairs (16 = floating seat+back cushions, no
  legs; 17 = frame with a stub back). They read as broken — do NOT use.
- 14/15/11/10 are four **complete** copies of the same chair in a clean value ramp
  (pale gray → mid gray → charcoal → black; 10 even leans forward = "sent").
Fix applied, then corrected per Justin: **Chair 1 → `10`** (bold, forward-leaning),
**Chairs 2/3/4 → `11`**. Each sits on a per-chair tinted disc (--cc-tint) for contrast.
Note: Chairs 2–4 share the same icon (11) — distinguished only by color/number, not
shape. Justin confirmed this is fine for now.
Image-budget script path is `~/Desktop/CoWork/scripts/resize-for-read.py`
(the bare `~/CoWork/...` in old notes does not resolve).

## RESOLVED 2026-06-03 — brand reskin to real Southeast brand
Pulled SE's real brand from se.church (Webflow CSS tokens). Applied to BOTH
`index.html` + `inventory.html`. SE token set now baked in:
- **Type:** headlines = serif (SE uses **Ivy Journal**, Adobe Fonts/Typekit — paid,
  won't embed in a standalone file). Substituted **Fraunces** (Google Fonts, free,
  near-identical high-contrast editorial serif). Body = **Inter** (matches SE).
- **Core colors:** `--bg #fef0e4` (linen) · `--surface #fffbf7` (warm white) ·
  `--ink #1d1f21` (warm near-black) · `--ink-soft #616264` · `--line #d2d2d3` ·
  `--accent #112b52` (navy) · `--accent-2 #233e96` (royal blue).
- **Chair ramp:** sky→navy — c1 `#2f9bc4` · c2 `#3f7fae` · c3 `#233e96` · c4 `#112b52`
  (c1 darkened from mockup's pale sky so the small Seeker label stays legible).
- SE's foundational identity is **warm/editorial/minimal** (linen + near-black + serif);
  the navy/sky blues are campaign+seasonal accents (token names: move-*, easter-2026).
Before/after mockup saved at `brand-mockup.png` in this folder.

## OPEN design calls for Justin (next session)
- **Value-ramp direction:** light Seeker → bold Maker. Reversible if Reid wants opposite.
- **Real assets still needed:** SE logo SVG (se.church has `logo-black.svg`/`logo-white.svg`)
  and, ideally, a real set of chair icons (current ones are grayscale line-art on tinted
  discs — they don't fight the brand but aren't *of* it). Gold partials (16/17) unusable.
- **Fraunces weight:** currently heavy. If too decorative, Newsreader/Spectral are calmer
  — one-line swap.

## What this project is
A single-page, vision-cast web tool for Reid/Leadership casting ONE unifying
discipleship pathway across all ministries — "one journey, many on-ramps."
Sits ABOVE the 10 AIM 3 pathways as the shared spine. Deadlines are flexible.

## The model (baked into the page)
- 4 Chairs across the top: Seeker(Reach) → Believer(Build) → Worker(Equip) → Disciple-Maker(Multiply)
- Catalysts in the gaps that move people forward:
  - 1→2: Alpha · Baptism Class · Next Steps Room
  - 2→3: Rooted · Unleashed Workshop
  - 3→4: Like Jesus Content (Walk/Live Like Jesus, 4-Chair Book — trains all ministries' leaders the same)
- On-ramps: "I want to explore Jesus / grow in Jesus / explore my calling / make disciples"
- Foundation layer: Circles of Concern (3/2/1) + 4-Chair Assessment
- "One at a time" = the church vision ("Unleash the full force of the church to love people one at a time")

## Files (all in ~/CoWork/southeast/disciple-pathway/)
- `index.html`   — the pathway diagram (interactive, click-to-reveal)
- `inventory.html` — the 28-question assessment, ported to vanilla JS, light brand
- `images/`      — chair icons; IN USE: `10` (Chair 1), `11` (Chairs 2–4). 16,17 broken gold partials
- `brand-mockup.png` — before/after of the SE brand reskin
- Open with: `open ~/CoWork/southeast/disciple-pathway/index.html`

## Brand status
✅ Reskinned to **real Southeast brand** (from se.church) on 2026-06-03 — see the
RESOLVED brand section above for the exact token set. All values are CSS variables at
the top of each file, so future tweaks are a one-line swap. Still outstanding: real SE
logo SVG + a true SE chair-icon set. (Ignore the old "Newjoy" template in ~/Downloads —
that was never Southeast's brand.)

## Open items
1. ~~Confirm icon mapping + fix contrast~~ ✅ DONE 2026-06-03 (see top of file).
2. ~~Real Southeast brand assets → reskin~~ ✅ DONE 2026-06-03 (SE token set applied).
   Remaining sub-item: obtain real SE logo SVG + true chair-icon set.
3. Tune copy (chair "win" lines, closing paragraph).
4. Licensing: inventory.html reproduces Sonlife's 28 questions — fine for internal
   demo, needs clearance before public/digital release.
5. Possible next builds: "pick your ministry" plug-in interaction; port to Vercel.

## Source project
The original (React/Next) lives at ~/Desktop/discipleship — `app/inventory/page.tsx`
(assessment) and `app/components/FourChairs.tsx` / `ChairCard.tsx` (chairs).
Craft project of record: "Discipleship Pathways" (PROJECTS collection in ✱ BACKEND).

## Image-read rule going forward
Always run images through `~/CoWork/scripts/resize-for-read.py` (caps at 1500px,
`--sheet` to combine many) before reading. Prefer text extraction over rendering
whole PDFs to images. Do heavy visual work in its own session.
