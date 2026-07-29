# Kandama · Melbourne market-entry model

An interactive financial model for a proposed Melbourne market entry by
**Kandama Collective**, a Philippine social enterprise selling handwoven Ifugao
clothing. Built as the companion to a university case-competition entry.

**Live: https://koala3353.github.io/kandama-model/**

Open it, change any assumption, and every figure recalculates. Click any figure
to see its formula, the live values substituted into it, where each input came
from, and what it feeds into.

## What it does

- **Nothing is hard-coded.** Every displayed number is computed from the inputs
  at runtime. There are no stored results to go stale.
- **Every input is tagged** 🟢 verified fact · 🔵 team decision · 🟡 our estimate,
  so you can see how much weight any given number can carry.
- **Capacity is a hard constraint, not a footnote.** 29 weavers at 110 loom-days
  each is 3,190 loom-days a year. Push the unit targets up and the plan turns
  red, with the three ways out costed.
- **Robustness three ways** — a tornado chart ranking every input by how much it
  moves the answer, a two-way grid over the two most fragile estimates, and a
  Monte Carlo simulation. All three point at capacity rather than margin as the
  real risk.
- **74 self-checks** run on load (bottom of the page) asserting the engine
  reproduces the derivation it was built from. If any figure drifts, they fail.

## Honesty notes

These are in the page itself, and repeated here because they matter:

- The programme ask funds the **Melbourne pilot only**. The Philippines domestic
  line is Kandama's existing, self-funding business, shown for capacity context.
  The ask does not buy company-wide revenue.
- **Loom-days per garment and loom-days per weaver are estimates**, and are the
  two inputs most likely to be wrong. Both are measured at a gate in October 2026
  before any edition is promised.
- **The Monte Carlo spread is not sourced.** No variance data exists for these
  inputs, so the distribution width is a choice we made and exposed as an
  editable input. Inputs are sampled independently; correlations and demand risk
  are not modelled. It shows how much the answer moves when the fragile estimates
  move together — it is **not** a probability of commercial success.
- The model does not cover working-capital timing within the year, tax, FX
  movement inside a drop, or inventory carried between years.

## Technical

One self-contained `index.html` — Tailwind via CDN plus vanilla JavaScript, no
build step, no framework, no dependencies to install. Opens by double-clicking.

- No `localStorage` or `sessionStorage`; all state is in memory, so it works
  inside sandboxed contexts.
- Scenarios are shareable via the URL hash (**🔗 Copy link**). Incoming values are
  validated against the input registry and clamped to range.
- Chart colours were validated for colour-vision deficiency separately for light
  and dark mode rather than chosen by eye.
- Keyboard operable, labelled controls, tabular numerals, respects
  `prefers-reduced-motion`, responsive down to 390px.

## Licence

No licence granted. This is coursework for a case competition, published so it
can be opened from a QR code during judging. Please don't reuse the model or its
figures without asking.
