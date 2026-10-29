# Study design: AI answer naming

Applies to studies that measure whether and how AI answers name a company or product across a frozen prompt set.

These rules come from early calibration runs and are revised as volume grows. Each figure below is scoped to the run that produced it; none has been replicated across engines or categories yet.

| Run | What it was |
|---|---|
| Rubric runs, Sep 2026 | Two categories (a local HVAC trade, growth-marketing help), 60 Perplexity calls: 24 rubric answers and 6 recommendation answers per category |
| HVAC shortlist run, Sep 2026 | One category, 10 wordings by 3 repetitions, 30 answers, one OpenAI model |
| Validation, Sep 29 2026 | Resampling on the stored answers above, 1,000 draws, fixed seed (`validate.mjs` in rubric-stability) |

## 1. Phrasing drives most of the variation

In the HVAC shortlist run, on average 62% of a company's variation in being named sat between wordings rather than between repeated asks of the same wording. In both rubric runs, answers to the same wording overlapped far more than a frequency-preserving null (no permuted draw of 1,000 matched, so p < 0.002). Across wordings, only a small core was stable.

**Rule:** use about a dozen phrasings per scenario rather than one prompt asked many times. The calibration used 10; a dozen is a judgment that adds a margin. Freeze the phrasings and hash the set before the first pull. A change to one word after the first pull is a new prompt set.

## 2. A naming rate belongs to its prompt set

Because phrasing moves the rate this much, a naming rate is a property of the prompt set that produced it, not of the company or the category.

**Rule:** freeze the prompt set, record its hash on every figure, and publish the set with the findings so a reader can see what was asked.

## 3. Volume decides how far you can rank

In the HVAC shortlist run (30 answers), the leader came out on top in both halves of random splits 88 to 89% of the time. Rank agreement for the rest of the field was about 0.50, below the usual 0.70 bar for reliability. Projecting from that, the ranking would need about 68 answers to reach 0.70 and about 117 to reach 0.80. The projection is an estimate, not an observed result.

**Rule:** report "named or not" rates at the volume you have, and rank only the leaders the volume supports. Do not order the field below them. When splitting answers to test stability, split by phrasing, not by answer, so runs of one wording do not land in both halves.

## 4. Fuzzy categories need a human clustering pass

Exact-label matching fails when engines describe the same concept in different words. In the rubric runs, HVAC produced 114 distinct labels for 19 concepts, and growth 166 for 22.

**Rule:** where labels are fuzzy, a person clusters concepts as a separate, recorded pass, with who did it and when. Where possible, replace fuzzy labels with explicit claims checked against a truth sheet (for example: standalone or not, price, what it works with).

## 5. Repetition and run schedule

Live tracking at 2 runs a day is a design choice for watching direction. It has not been shown to detect small changes, and the minimum detectable change is stated once a baseline's variance is known.

**Rule:** state "direction, not a score" on live tracking figures, and use more repetitions in any Closed Book Live API Model run, where two arms are compared directly.

## 6. Failures and answers without search

An engine error, a timeout or an empty answer is recorded as a failure. It is never scored as "not named," and it is left out of the denominator.

An answer given without searching is a real answer a buyer would see. It stays in the denominator, flagged. Report, by engine, the count of failures and the share of answers that did not search.

## Checklist before the first pull

- [ ] About a dozen phrasings per scenario, written in the buyer's framing
- [ ] Prompt set frozen and hashed; hash recorded
- [ ] Surfaces, engines, models and settings recorded
- [ ] Days and repetitions per day fixed
- [ ] Truth sheet written for claim matching, each fact checked against a primary source
- [ ] Baseline product line chosen and on the same surfaces
- [ ] Domain list for citation classes dated
- [ ] Human Audit sample plan written
