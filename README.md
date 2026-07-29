# Play Studies

**Twelve tiny browser toys in four families, each turning one gesture into a small workout for a specific cognitive skill.** A play-based-learning study by aaryaa, built as a portfolio piece toward the IDEO Play Lab lane.

Open it cold, pick a card, and press, drag, or let go. The label under each card names the cognitive skill it exercises.

**Live:** https://play-studies.vercel.app  ·  **Source:** github.com/aaryaa8/play-studies (private)

Redeploy after changes with `npx vercel@latest deploy --prod --yes` from this folder. Media for the portfolio page lives at stable URLs like `https://play-studies.vercel.app/assets/gifs/turn.mp4`, and `assets/embed-snippet.html` is a ready-to-paste WordPress block that uses them.

---

## What it is

One self-contained page with a hub and twelve toys behind it. The toys are grouped into four families: three by their core gesture (Hold, Draw, Let go) and one about perception (Look). Each toy is one screen, one interaction, tuned to a real cognitive action. The thesis sits at the top: some skills are better played than taught.

| # | Family | Toy | Interaction | Cognitive skill |
|---|--------|-----|-------------|-----------------|
| 01 | Hold | Patience | Hold to grow a bloom you cannot rush | Impulse control |
| 02 | Hold | Steady | Keep a light lit by holding your hand still | Sustained attention |
| 03 | Hold | Count | Hold for a target length with no clock | Time perception |
| 04 | Draw | Melody | Trace a line that loops back as sound | Cross-sensory mapping |
| 05 | Draw | Recall | Watch a pattern light up, then redraw it | Working memory |
| 06 | Draw | Continue | Extend a hidden rule, then see the true path | Pattern prediction |
| 07 | Let go | Constellations | Fling seeds that settle into constellations | Systems thinking |
| 08 | Let go | Aim | Curve a seed through gravity to a target | Mental simulation |
| 09 | Let go | Tinker | Change one rule until the seeds obey | Causal reasoning |
| 10 | Look | Follow | Keep your hand on a wandering, quickening light | Visual tracking |
| 11 | Look | Fog | Wipe away fog to find a hidden light | Visual search |
| 12 | Look | Turn | Rotate a shape to match a faint silhouette | Mental rotation |

The connecting idea is embodied inquiry: exercising a skill by doing it, not reading about it.

## How to run

The page is fully self-contained. Two ways to open it:

**Simplest.** Double-click `index.html` to open it in your browser. Everything runs locally. An internet connection loads the display font on first open; without it the page falls back to a system font and still works.

**As a local server** (useful if a browser blocks anything on `file://`):

```bash
cd CxD-Builds/03-play-toy
python3 -m http.server 8137
```

Then visit `http://localhost:8137`.

Sound plays in several toys and starts on your first click, so browsers allow it. Best with the volume up.

## Design notes

- **Type.** The whole game runs on Nunito, a rounded humanist sans chosen from calm-typography research. Rounded letterforms read as warm and safe (the curvature effect), and Nunito keeps that quality while staying readable and shipping true italics for the accent words. The font is self-hosted in `assets/fonts/`, so the page makes no external requests and works offline.
- **One visual language.** Warm-ink background, one accent tint per family (coral for Hold, iris for Draw, jade for Let go, rose for Look), a subtle skill label on every card and every toy.
- **One dial, everywhere.** Each toy carries a single quiet control that shifts one variable of its skill (wait length, stillness tolerance, gravity, and so on), so every toy reads as a small system you can retune. A global sound toggle sits in the top bar.
- **Motion is the product.** Time-based growth in the Hold family stays frame-rate independent. Physics in the Let go family uses softened gravity and light damping so play settles rather than flies apart.
- **Generative, not scripted.** Blooms, memory layouts, and hidden rules are drawn from a seeded random function, so repeats stay fresh.
- **Reduced motion.** The page respects `prefers-reduced-motion` and trims particle bursts and idle animation.

## Files

- `index.html`: the whole thing, markup, styles, and the nine toys in vanilla JS.
- `README.md`: this file.
- `CASE-STUDY.md`: a one-paragraph summary to adapt for the portfolio page.
- `PORTFOLIO.md`: the content and flow plan for the aaryaakamdar.com case-study page, with draft copy and a private competency map.

## Open questions for aaryaa

Done since the last pass: a per-toy sub-dial on all nine (one quiet control each), a visible mute in the top bar, and `PORTFOLIO.md`. Remaining reads:

1. **Dial tuning.** Each toy has one dial with three presets. Play them and tell me if any preset should shift (for example Aim's heavy gravity, or Count's long span).
2. **The 3x3 map.** Are these the right nine skills, or would you swap any (for example add creativity)?
3. **Font.** Nunito is applied. Keep it, or try Quicksand or Comfortaa for more roundness (they would drop the italic accents)?
4. **Portfolio assets.** Want me to capture the GIFs and build the 3x3 matrix graphic that `PORTFOLIO.md` calls for?
5. **Placement.** Standalone page, or embedded in your portfolio site (which would change the top bar and framing)?
