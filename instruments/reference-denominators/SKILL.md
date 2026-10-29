---
name: reference-denominators
description: Rules for stating and comparing rates from AI answer research so every number carries its surface, sample and dates, and comparisons are only made like for like. Use whenever a naming rate, citation rate or any share from a research run goes into a deck, readout, memo or message, when comparing one product or company against another, or when a figure rests on a small denominator.
---

# Reference denominators

## What it measures

Nothing directly. This is the instrument that makes every other rate readable. It fixes how a rate is stated and what it can be compared with.

## When to use it

Every time a rate leaves a research run and goes anywhere a reader will see it.

## Protocol

### 1. Every number carries surface, sample and dates

Write the numerator and denominator, the surface, and the dates every time:

> Named in 4 of 62 unbranded questions, Google AI Overviews, US desktop, Oct 18 to 20.

A percentage without its denominator can't be checked, and a rate without its surface invites comparison with a number from a different engine.

### 2. Compare only on the same surface

Engines differ in how often they name anyone, how many sources they cite and whether they search at all. A rate on ChatGPT and a rate on AI Overviews are not comparable even for the same prompt set. Compare rates only when the surface and the dates are the same. Within that, the prompt set should match too; the one exception is a baseline product line (rule 3), which by nature is asked different questions and is labelled as a baseline wherever it appears.

A rate pooled across engines is its own surface. Name it as such ("three engines pooled"), report the per-engine rates beside it, and compare it only with another rate pooled the same way.

### 3. Size every gap against a baseline product line

A gap means little without a reference point the reader already trusts. Pick a product line from the same company that buyers already associate with it, measure it on the same surface and days, and put the two side by side. The baseline shows what "normal" looks like for this company on this surface, so the gap reads as a gap and not as a property of the engine.

### 4. Never compare products measured on different surfaces

If the baseline only ran on one surface, it is compared only on that surface. Say so wherever the baseline appears.

### 5. Compute an interval for every rate; show it when the sample is small

Compute a 95% interval for every rate and store it in the numbers ledger, whatever the sample size. It costs nothing, and anyone challenging a number can see how firm it is.

Use the method that matches how the answers were collected:

- **One answer per prompt:** a Wilson interval.
- **Several answers per prompt (repeated runs, several days, several engines):** resample whole prompts (a bootstrap over prompts, 1,000 or more draws, fixed seed), or use a Wilson interval on the effective sample size. Repeated answers to one prompt tend to agree, so counting each as independent makes the interval too narrow. In the calibration work most variation sat between wordings, which is exactly the case where this matters.

Record which method was used beside the interval.

Show the interval on the slide or page when the denominator is under about 100, or when fewer than about 10 answers had the result being counted. These cutoffs are a working heuristic: they mark where the interval is wide enough to change what a reader should believe. On larger samples the interval stays in the ledger, because on a slide it is clutter.

Use 95%, not 90%. It is the standard a reviewer expects, and a narrower interval reads as shading the number.

A small count can lead a slide if it is the like-for-like comparison, but the reader must see how wide it is. Name a larger-denominator figure as the operating baseline for tracking.

## Pass bar

A figure passes if a reader can answer, from the text alone: how many out of how many, on which surface, on which dates, and compared with what on the same surface.

## Reference result

Zoom case, Oct 2026 (enterprise SaaS), Google AI Overviews, same days: Zoom Workplace (the established line) was named in 76% of unbranded questions (34 of 45), the Zoom AI Receptionist in 6% (4 of 62). The 4 of 62 carries a Wilson interval of roughly 2 to 16 percent; it led because it was the like-for-like comparison. The two product lines were asked different prompt sets, so Workplace is labelled as the baseline, not as a matched comparison. The operating baseline for weekly tracking was 25 of 215 answers (12%), three engines pooled (ChatGPT, Gemini, Perplexity), with the per-engine rates reported beside it. Workplace ran on Google only, so it was never compared with the three-engine figures.

## What it does not claim

- A same-surface comparison controls for the engine, not for the prompts. The two product lines are asked different questions. State that the comparison is of naming rates on matched surfaces, not of identical prompts.
- An interval covers sampling noise inside one prompt set. It does not cover a different prompt set, which can move rates further than sampling does.

## What to record

For every figure that leaves the run: numerator, denominator, surface, prompt-set hash, dates, level (answer or citation), the 95% interval and its method (always), whether it was shown, and the baseline it is compared with.
