---
name: answer-reliability-handcheck
description: Hand-check machine labels on AI answers before reporting any rate built on them. Use after a research run has labelled answers in code (named or not, recommended or not, recommendation strength) and before any naming rate, recommendation rate or similar figure goes into a deck, readout or client message. Also use when someone asks how reliable a label is, whether a recommendation rate can be reported, or when a new label or classifier is introduced.
---

# Answer reliability hand-check

## What it measures

Agreement between the labels code assigned to AI answers and the labels one person assigns by reading the same answers. It tells you which labels the instrument measures reliably enough to report, and which it does not.

The point is that a rate is only as good as the label underneath it. Naming is usually easy for code to get right; judging whether an answer recommends something, and how strongly, is not. Without this check, a confident-looking recommendation rate can rest on a label that is wrong a third of the time.

## When to use it

Run it once per labelling scheme per study, before any rate is reported. Run it again if the labelling code, the prompt set or the category changes, since agreement on one category does not transfer to another.

## Protocol

1. Draw 30 answers from the labelled set. Spread the draw across engines, scenarios and days in rough proportion to the full set, so one engine's quirks do not dominate. Record how the sample was drawn.
2. Hide the machine labels from the reader. Reading with the labels visible pulls the reader toward agreeing.
3. The reader labels each answer on every label in use. At minimum:
   - **Named:** is the subject named, yes or no.
   - **Recommended:** does the answer recommend the subject, yes or no.
   - **Recommendation level:** the four-level label (for example top pick, recommended among others, mentioned without recommendation, discouraged). Use the same definitions the code uses, written down before reading.
4. Compare reader and machine label by label. Score agreement separately for each label. Never pool labels into one agreement figure, because a pooled figure hides the label that fails.
5. Write down every disagreement with a one-line note on why. The notes are what fixes the labeller.

## Pass bar

80% agreement per label.

- A label at or above 80% can be reported, with the hand-check cited.
- A label below 80% is not reported. It is deferred to a two-reader baseline: two people label the same sample independently, their agreement with each other is measured first, and the machine is then scored against their consensus. Until that runs, the figure stays out of the deliverable, and the deliverable says it is deferred and why.

Thirty answers is a floor, not a precision target. At 30, one or two disagreements move agreement by several points, so treat results near the bar (77% to 83%) as provisional and say so.

## Reference result

Zoom case, Oct 2026 (enterprise SaaS), one reader, 30 answers:

| Label | Agreement | Outcome |
|---|---|---|
| Named or not | 30 of 30 (100%) | Reported |
| Recommended, yes/no | 25 of 30 (83%) | Passes, near the bar |
| Four-level recommendation | 21 of 30 (70%) | Failed |

Consequence: the deliverable reported naming and citation, which the instrument measured reliably, and deferred recommendation rate to a two-reader baseline at Day 30.

## What it does not claim

- It does not show the reader is right. One reader is a check on the code, not ground truth. That is why a failed label goes to two readers, not to a better single read.
- It does not validate labels it did not test. A pass on naming says nothing about claim matching or citation class.
- It does not transfer across categories or prompt sets.

## What to record

Store this with the run, not in this repo:

- Reader name and date.
- Run identifier and prompt-set hash.
- How the 30 were drawn, and the answer identifiers.
- Agreement per label, as counts and percent.
- Every disagreement with its note.
- The decision per label: reported, or deferred with the reason.

The deliverable cites the hand-check by reference ("hand-checked, 30 answers, one reader, [date]") wherever a rate built on a checked label appears.
