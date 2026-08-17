# FAIR Model Study Tool

An interactive drill for the FAIR risk taxonomy: study the decomposition tree, then rebuild it
from memory — place all 13 components in the right positions, assign the right unit to each one,
and match all 22 testable definitions.

**Live:** https://rootcawsllc.github.io/fair-model-study/

![The FAIR decomposition tree in study mode with a real UK financial-services data-breach scenario loaded. Loss Event Frequency and Loss Magnitude are highlighted in amber carrying 0.43 / 0.65 / 0.69 events per year and £10K / £5.7M / £11.2M per event; the other eleven nodes from Threat Event Frequency down to Secondary Loss Magnitude remain empty. Below, a panel reading "2 of 13 nodes filled" explains that a published loss study reports how often the event happens and how much it costs, and nothing else](preview.png)

## What it does

- **Study mode** — the complete FAIR decomposition tree, from Risk down to Secondary Loss
  Magnitude, with the unit each factor carries: dollars (`$`), probability (`%`), or frequency (`#`).
- **Practice mode** — the tree comes back empty. Pick a component from the shuffled pool, tap where
  it belongs, then assign its unit before moving on. Placement accuracy and unit accuracy are scored
  separately, so you can see which half you actually know.
- **Definitions quiz** — 22 items in one pool: the 13 model components, the 6 forms of loss, and
  the 3 Probability of Action sub-factors. Match each name to its definition; colour-coded by category.

- **Worked example** — load a real, source-backed scenario onto the study tree and watch how
  little of it fills in. A published loss study reports an annualised event frequency and a
  per-event loss: in FAIR terms, Loss Event Frequency and Loss Magnitude, and nothing else. Two of
  thirteen nodes. Nobody measures contact frequency or resistance strength across a population, so
  the eleven empty nodes are not missing data — they are the analysis, which is the reason the
  decomposition is worth knowing cold. Each filled node shows the sources behind it, with their
  stated limitations.

The tree scales itself to fit the viewport, so the full 13-node model stays readable on a phone.

## Build

Single self-contained `index.html` — React 18 via UMD CDN, no build step, no dependencies.
Styled to match the palette and type system of the RootCaws design system: powder
rose surfaces, warm ink, rose accent, Fraunces for display and Inter for UI.

## Running locally

```bash
python -m http.server 8000
```

Then open http://localhost:8000. The worked example fetches the shard corpus over HTTPS at load;
if that is unreachable the panel says so and both drills work exactly as before, since nothing in
the study or practice modes depends on it.

## Status

Built as a training exercise — a study aid for learning the FAIR taxonomy, and for learning how
this kind of interaction is put together.

The taxonomy follows the FAIR Model Standard Artifact Version 3.0 (January 2025) published by the
FAIR Institute. This is a study aid, not a substitute for official FAIR training material.
The FAIR Model™ is a trademark of the FAIR Institute.

Worked-example data comes from [risk-benchmarks](https://github.com/RootCawsLLC/risk-benchmarks), which
derives it from [RiskShard](https://github.com/raviaxo/RiskShard) by
[raviaxo](https://github.com/raviaxo), AGPL-3.0. The mapping of a shard onto FAIR nodes is this
project's own, and it is deliberately shallow: the shard's frequency triangle is Loss Event
Frequency and its impact triangle is Loss Magnitude, with no attempt to derive the factors beneath
them, because nothing in the source supports that derivation.

## License

Copyright (c) 2026 RootCaws LLC.

[GNU AGPL v3 or later](LICENSE). If you modify this and run it as a network service, the AGPL requires you to offer your users the modified source under the same terms.
