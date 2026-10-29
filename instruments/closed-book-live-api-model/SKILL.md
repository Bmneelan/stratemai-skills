---
name: closed-book-live-api-model
description: Closed Book Live API Model. Spec for a test of whether supplying a client's verified facts changes what an AI model says, run before any claim that fixing source pages will change answers. Use when a diagnosis says a client is missing or misdescribed in AI answers because of what its pages say, when designing a fix-and-measure test, or when anyone wants to use the words "retrieve" or "cause" about an engine's behaviour. Status is spec; it has not been run.
---

# Closed Book Live API Model

Status: spec. Designed in Oct 2026; not yet run. Treat the protocol as the plan to follow, and update this file with what the first run teaches.

## What it measures

Whether the model uses the client's verified facts when it has them. That separates two explanations that look identical from the outside:

1. **The facts are not in front of the model.** Given them, it names the client and describes it correctly. Getting the facts onto pages engines cite is then a plausible lever.
2. **The facts are not the bottleneck.** Given them, the answers barely change. The problem sits elsewhere (how the engine weighs sources, competing claims, naming), and page changes alone are a weak bet.

It does not show whether a live engine fetched a particular page. Search is off in both arms, so retrieval is never observed. A study of public answers sees only what an answer cites, and some engines answer without searching a large share of the time. So "the client's pages do not say X" stays a leading hypothesis for an omission, never a demonstrated cause.

## When to use it

Before telling a client that page changes will move their visibility, and before spending engineering time on content fixes as the primary lever.

## Design

### Stage 1, closed book vs open book on the live API

1. Take the frozen prompt set for the scenario.
2. Write a truth sheet: the verified facts the answer should contain (for example, that a product is available standalone, its price, what it works with). Each fact is checked by hand against a primary source.
3. Run each prompt through the live model by API with web search off, in two arms:
   - **Closed book:** the prompt alone. The model answers from what it already knows.
   - **Open book:** the prompt plus the truth sheet supplied as context.

   Search stays off in both arms so the only difference between them is the facts you supplied.
4. Run at least 7 repetitions per prompt per arm, and 8 if the test measures citations. More prompts add more certainty than more repetitions, because repeated runs of one prompt tend to agree; when choosing where to spend, add prompts first.
5. Score both arms in code on the same labels the live study uses (named, claims matched against the truth sheet), with the Human Audit applied.

### Stage 2, live before-and-after

1. Change the target pages so the verified facts are present and readable in raw HTML (run the rendering check first).
2. Keep a set of baseline prompts untouched: prompts about a product line whose pages did not change. They control for engine drift over the same period.
3. Run the frozen prompt set and the baseline prompts on the live engines before the change and on a fixed schedule after.
4. Compare the change on target prompts against the change on baseline prompts. Movement on both is engine drift; movement only on target is evidence the pages mattered.

Do not promise movement inside 30 days. Engines adopt page changes on their own schedule.

## Pass bar

The test answers one question: is there a real difference between the arms, or not? There is no fixed size of jump to hit.

1. **Name one primary measure before the first call** (usually naming rate). Other measures are secondary and reported as such. Testing several measures and leading with whichever one moved is how chance findings get through.
2. **Compute the difference per prompt:** open-book rate minus closed-book rate for each prompt. The prompt is the unit, because repeated runs of one prompt are not independent.
3. **Put a 95% interval on the average difference.** With fewer than about 20 prompts, use a t-interval on the per-prompt differences or a paired permutation test; a bootstrap over so few prompts gives intervals that are too narrow. With more prompts, a paired bootstrap over prompts (1,000 or more draws, fixed seed) is fine.
4. **The result counts when the interval excludes zero.** Report the difference with its interval, for example "open book named the client 14 points more often, 95% interval 6 to 22" (an illustration, not a result).
5. **When the interval includes zero, the result is "Inconclusive (not statistically significant)."** Record the estimate and its interval in the run's ledger under that label. It never goes on a client slide as a number. The finding is that no difference was shown at this volume, which points to a larger run or a different explanation.

Write the primary measure and the method in the run's design note before the first call, so nothing is chosen after seeing the result.

## Language rule

This is the rule the test exists to enforce, and it applies everywhere in the workbench:

- Say **"cite,"** never **"retrieve."** Retrieval is only observed when the engine's own search results are logged for that answer, and neither this test nor a study of public answers logs them.
- Say **"working explanation"** or **"leading hypothesis,"** never **"cause."**

## What it does not claim

- Stage 1 tests the live model by API with search off, not the consumer product. It shows what the model does with the facts, not what the live product does with the web.
- Stage 1 does not observe retrieval.
- Stage 2 shows association with the page change against a baseline, not proof that the change alone moved answers.
- A null result in Stage 2 inside a short window is not evidence the pages do not matter.

## What to record

Store with the run: prompt-set hash, truth sheet with sources, model and version per arm, repetitions, the primary measure and method as written before the first call, per-prompt results per arm, the difference with its interval and method, the label (counts, or Inconclusive), the date of the page change, baseline prompt set, and the before and after series for both.
