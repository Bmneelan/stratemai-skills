---
name: offline-sensitivity-test
description: Spec for a test that separates two failure points in AI answers, the engine never retrieving a fact versus retrieving it and not using it, before any claim that fixing source pages will change answers. Use when a diagnosis says a client is missing from answers because of what its pages say, when designing a fix-and-measure test, or when anyone wants to use the word "retrieve" or "cause" about an engine's behaviour. Status is spec; it has not been run.
---

# Offline sensitivity test

Status: spec. Designed in Oct 2026; not yet run. Treat the protocol as the plan to follow, and update this file with what the first run teaches.

## What it measures

Whether supplying the verified facts changes the answer. That separates two failure points that look identical from the outside:

1. **Not retrieved.** The engine never saw the fact. Fixing source pages, and getting them read, should help.
2. **Retrieved, not used.** The engine had the fact and still left the client out. Fixing source pages will not help much; the problem is elsewhere (how the engine weighs sources, competing claims, naming).

A study of public answers sees only what an answer cites, not everything the engine read. Some engines answer without searching a large share of the time. So "the client's pages do not say X" is a leading hypothesis for an omission, never a demonstrated cause, until this test runs.

## When to use it

Before telling a client that page changes will move their visibility, and before spending engineering time on content fixes as the primary lever.

## Design

### Stage 1, offline

1. Take the frozen prompt set for the scenario.
2. Write a truth sheet: the verified facts the answer should contain (for example, that a product is available standalone, its price, what it works with). Each fact is checked by hand against a primary source.
3. Run each prompt through the model by API with search off, in two arms:
   - **Without facts:** the prompt alone.
   - **With facts:** the prompt plus the truth sheet supplied as context.
4. Use more repetitions than the live study (at least 7 per prompt per arm, and 8 if the test measures citations), because the arms are compared directly and live designs with 2 runs a day are too noisy for small effects.
5. Score both arms in code on the same labels the live study uses (named, claims matched against the truth sheet), with the Human Audit applied.

Reading: if naming and claim accuracy rise materially in the "with facts" arm, the model uses the facts when it has them, which supports "not retrieved" as the failure point. If they do not rise, "retrieved, not used" (or a naming problem) is more likely, and page changes alone are a weak bet.

### Stage 2, live before-and-after

1. Change the target pages so the verified facts are present and readable in raw HTML (run the rendering check first).
2. Keep a set of baseline prompts untouched: prompts about a product line whose pages did not change. They control for engine drift over the same period.
3. Run the frozen prompt set and the baseline prompts on the live engines before the change and on a fixed schedule after.
4. Compare the change on target prompts against the change on baseline prompts. Movement on both is engine drift; movement only on target is evidence the pages mattered.

Do not promise movement inside 30 days. Engines adopt page changes on their own schedule.

## Pass bar

Stage 1 needs a pre-registered threshold before it runs (for example, a rise of at least 15 points in naming rate with non-overlapping intervals). Set it in the run's design note, not after seeing the result.

## Language rule

This is the rule the test exists to enforce, and it applies everywhere in the workbench:

- Say **"cite,"** never **"retrieve,"** unless this test has run on the scenario.
- Say **"working explanation"** or **"leading hypothesis,"** never **"cause."**

## What it does not claim

- Stage 1 tests a model by API with search off. It shows what the model does with the facts, not what the live product does with the web.
- Stage 2 shows association with the page change against a baseline, not proof that the change alone moved answers.
- A null result in Stage 2 inside a short window is not evidence the pages do not matter.

## What to record

Store with the run: prompt-set hash, truth sheet with sources, model and version per arm, repetitions, the pre-registered threshold, scores per arm with intervals, the date of the page change, baseline prompt set, and the before and after series for both.
