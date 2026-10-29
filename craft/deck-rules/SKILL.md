---
name: deck-rules
description: Rules for building and reviewing research-backed decks, from slide labels and voice to how claims, numbers and scenario slides are structured. Use when drafting, restructuring or QA-ing any presentation built on Wayfinder research (a panel case, a client readout, a diagnostic findings deck), when turning findings into slides, or when checking a deck before it goes out.
---

# Deck rules

These rules turn research into slides a skeptical executive can test. Every slide is checked against them before a deck goes out.

## 1. Plain labels, meaning first

Name each thing by what it is. Add the industry term only where the audience expects it, and define it once.

Evidence lanes carry plain labels on slides:

| Instead of | Use |
|---|---|
| Measured | Custom research |
| Observed | [Client] public sources |
| Reported | [Client]-reported |
| Vendor | Third-party tool |
| Outcome | Data result |
| Outside-in snapshot | One-week snapshot of public AI answers; no [client] internal data (adjust the duration) |

Define each product the first time it appears ("[Product] ([what it is in plain words])"), then use the short name. Use the client's own names for their teams and departments once you know them.

Why: the panel spends its attention on the argument, not on decoding your vocabulary. Jargon that the audience doesn't use reads as distance.

## 2. Objective voice

No "I" on slides. The slides state what the data shows. The call is labelled **"Recommendation."** You speak in the first person; the slides don't.

Why: it separates evidence from judgment visibly, so the audience can accept the evidence while arguing with the call.

## 3. Falsifiable, with humility

Each claim says three things: what the data shows, how much data stands behind it, and what would prove it wrong.

Why: a claim with its own disconfirmation test reads as confident. One without reads as advocacy.

## 4. Every number earns its place

Each number on a slide has a visible "so what" for the case. If you can't write the so-what in one line, the number comes off the slide. Every number also carries surface, sample, dates and lane (see `instruments/reference-denominators` and `research/evidence-lanes`).

## 5. Charts over words

Use data visuals and priority scoring wherever a chart can carry the point. A priority score makes a recommendation comparable and arguable; prose makes it rhetorical.

## 6. Scenario pairs

Each scenario gets two slides that read as one story.

**Light slide, labelled "Situation and insight."** Research only.
- A falsifiable headline.
- The buyer and their question.
- The buyer path as bubbles (for example Be Found, Present, Believed, Preferred), bubble size equal to the size of the gap, each tagged Data result or Signal.
- One insight.
- One "Would be wrong if" line.

**Dark slide, labelled "Why it matters · What happens first."**
- Impact: why it matters to the client.
- Priority score bars on the scoring tests used across the deck.
- The first steps.
- The owner, by function.

Tie the two slides together visibly (same scenario name, same bubble), so the audience can see the dark slide answers the light one.

## 7. Diagnostics

The diagnostics section says, for each gap, what is a search problem and what is something else (a naming problem, a packaging problem, a proof problem), and gives a test for each. A gap labelled a search problem without a test that could show otherwise is an assumption.

## 8. Causal language

"Cite," never "retrieve," unless the Closed Book Live API Model has run. "Working explanation" or "leading hypothesis," never "cause." Payoffs need a number or a reason a CFO would accept.

## Review pass

Before a deck goes out, check each slide for: a plain label on every lane; no "I"; a "would be wrong if" on every claim slide; a so-what on every number; every number in the ledger and not on the retired list; scenario pairs tied together; diagnostics with a test per gap. Then have someone who did not build it read it cold.
