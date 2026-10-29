# Study design: AI answer naming

Applies to studies that measure whether and how AI answers name a company or product across a frozen prompt set.

From calibration runs in Sep 2026: two unrelated categories (a local HVAC trade and growth-marketing help), 60 Perplexity calls, 10 phrasings by 3 repetitions each, plus a resampling validation (1,000 draws, fixed seed).

## 1. Phrasing drives most of the variation

About 62% of the variance in whether a company was named sat between wordings, not between repeated asks of the same wording. Within one wording, answers were consistent well above a frequency-preserving null (p about 0.001 in both categories). Across wordings, only a small core of companies was stable.

**Rule:** use about a dozen phrasings per scenario rather than one prompt asked many times. Freeze the phrasings and hash the set before the first pull. A change to one word after the first pull is a new prompt set.

## 2. A naming rate belongs to its prompt set

Because phrasing moves the rate this much, a naming rate is a property of the prompt set that produced it, not of the company or the category.

**Rule:** freeze the prompt set, record its hash on every figure, and publish the set with the findings so a reader can see what was asked.

## 3. Volume decides how far you can rank

A category leader is dependable at about 30 answers: in random half-splits it came out on top in both halves 88 to 89% of the time. The rest of a ranking needs roughly 70 answers to reach 0.70 reliability.

**Rule:** report "named or not" rates at the volume you have, and rank only the leaders the volume supports. Do not order the field below them.

## 4. Fuzzy categories need a human clustering pass

Exact-label matching fails when engines describe the same concept in different words (a company's capability, a product type, a claim).

**Rule:** where labels are fuzzy, a person clusters concepts as a separate, recorded pass, with who did it and when. Where possible, replace fuzzy labels with explicit claims checked against a truth sheet (for example: standalone or not, price, what it works with).

## 5. Repetition and run schedule

Live tracking at 2 runs a day is enough to see direction, not small changes.

**Rule:** state "direction, not a score" on live tracking figures, and use more repetitions in any Closed Book Live API Model run, where two arms are compared directly.

## 6. Failures are recorded as failures

An engine error, a timeout or an answer without search is recorded as what it is. It is never scored as "not named." Report the count of failures and of answers that did not search, by engine.

## Checklist before the first pull

- [ ] About a dozen phrasings per scenario, written in the buyer's framing
- [ ] Prompt set frozen and hashed; hash recorded
- [ ] Surfaces, engines, models and settings recorded
- [ ] Days and repetitions per day fixed
- [ ] Truth sheet written for claim matching, each fact checked against a primary source
- [ ] Baseline product line chosen and on the same surfaces
- [ ] Domain list for citation classes dated
- [ ] Human Audit sample plan written
