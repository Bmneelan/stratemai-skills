---
name: human-audit
description: Run a Human Audit, where a person reads a sample of AI answers to check the labels code assigned, before reporting any rate built on those labels. Use after a research run has labelled answers in code (named or not, recommended or not, recommendation strength) and before any naming rate, recommendation rate or similar figure goes into a deck, readout or client message. Also use when someone asks how reliable a label is, whether a recommendation rate can be reported, or when a new label or classifier is introduced.
---

# Human Audit

## What it measures

Agreement between the labels code assigned to AI answers and the labels one person assigns by reading the same answers. It tells you which labels the instrument measures reliably enough to report, and which it does not.

The point is that a rate is only as good as the label underneath it. Naming is usually easy for code to get right; judging whether an answer recommends something, and how strongly, is not. Without this check, a confident-looking recommendation rate can rest on a label that is wrong a third of the time.

## When to use it

Run it once per labelling scheme per study, before any rate is reported. Run it again if the labelling code, the prompt set or the category changes, since agreement on one category does not transfer to another.

## Protocol

1. Draw the sample in two parts, and record how each was drawn:
   - **Named answers:** at least 50 answers where the code says the client is named, spread across engines, scenarios and days. Recommendation labels only mean something on these, and a proportional draw would hold too few when the client is rarely named.
   - **Not-named answers:** at least 30, to check that the code is not missing mentions.

   Spread each part across engines, scenarios and days so one engine's quirks do not dominate.
2. Hide the machine labels from the reader. Reading with the labels visible pulls the reader toward agreeing.
3. The reader labels each answer on every label in use. At minimum:
   - **Named:** is the subject named, yes or no.
   - **Recommended:** does the answer recommend the subject, yes or no.
   - **Recommendation level:** the four-level label: top pick; recommended among others; mentioned, not recommended; N/A (subject not named, so no level applies). Use the same definitions the code uses, written down before reading.
4. Compare reader and machine label by label. Score agreement separately for each label, and score the two recommendation labels on named answers only; on not-named answers they agree automatically, which would inflate the figure. Never pool labels into one agreement figure, because a pooled figure hides the label that fails.
5. For each label, report raw agreement, its 95% interval, and Cohen's kappa. Kappa corrects for agreement that would happen by chance when one answer is far more common than the other.
6. Write down every disagreement with a one-line note on why. The notes are what fixes the labeller.

## Pass bar

80% agreement per label, judged on the sample above. The 80% figure is a working standard, not a statistical law.

- **Passes:** agreement is 80% or above on the full sample (at least 50 named answers for recommendation labels). The label can be reported, with the Human Audit cited.
- **Fails:** agreement is below 80%. The label is not reported. It is deferred to a two-reader baseline: two people label the same sample independently, their agreement with each other is measured first, and the machine is then scored against their consensus. Until that runs, the figure stays out of the deliverable, and the deliverable says it is deferred and why.
- **Too small to judge:** if the sample falls short of the sizes above, the result is recorded but no pass or fail is declared, and the label is not reported.

Below about 50 items, one or two disagreements swing agreement by several points, which is why the sample sizes are part of the bar.

## Reference result

Zoom case, Oct 2026 (enterprise SaaS), one reader, 30 answers drawn before this protocol required a split sample:

| Label | Agreement | Outcome at the time |
|---|---|---|
| Named or not | 30 of 30 (100%) | Reported |
| Recommended, yes/no | 25 of 30 (83%) | Passed (would be too small to judge now) |
| Four-level recommendation | 21 of 30 (70%) | Failed (would be too small to judge now) |

Consequence: the deliverable reported naming rates and deferred recommendation rate (both labels) to a two-reader baseline at Day 30. Citation figures were reported on the strength of the citation-class protocol, not this audit, which did not test them. 

## What it does not claim

- It does not show the reader is right. One reader is a check on the code, not ground truth. That is why a failed label goes to two readers, not to a better single read.
- It does not validate labels it did not test. A pass on naming says nothing about claim matching or citation class.
- It does not transfer across categories or prompt sets.

## What to record

Store this with the run, not in this repo:

- Reader name and date.
- Run identifier and prompt-set hash.
- How each part of the sample was drawn, and the answer identifiers.
- Per label: agreement as counts and percent, its 95% interval, and Cohen's kappa.
- Every disagreement with its note.
- The decision per label: reported, or deferred with the reason.

The deliverable cites the Human Audit by reference ("Human Audit, [n] answers, one reader, [date]") wherever a rate built on a checked label appears.
