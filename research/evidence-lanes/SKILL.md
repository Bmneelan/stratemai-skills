---
name: evidence-lanes
description: Tag every number in research with its origin (who produced it), kind (what sort of evidence it is) and grade, then derive the lane label a reader sees from a fixed lookup. Use whenever writing or reviewing a deck, readout, memo, dossier or message that carries numbers, when entering a source into the evidence store or registry, before any figure reaches a client, and when deciding whether a number is fit to use at all.
---

# Evidence lanes

## Why

A reader weighs a number by where it came from. Your own measurement, a company's claim about itself and a vendor's model are different kinds of evidence, and one sentence that mixes them borrows the credibility of the strongest for the weakest.

Earlier versions used one word, "lane," to answer two questions at once: who produced this, and how. That hid gaps and let the same word mean different things in different files. Now each question gets its own field with a short fixed list, and the label a reader sees is looked up from those fields, never typed by hand.

## Every number carries three fields

### `origin`: who produced it

| Code | Meaning |
|---|---|
| `stratemai` | Brad's own collection or analysis |
| `client` | The client company itself |
| `vendor` | A commercial tool (Profound, Semrush, DataForSEO estimates) |
| `independent` | Researchers, analysts, test labs, regulators, courts |
| `public` | Customers, forums, Reddit, reviews |

### `kind`: what sort of evidence it is

| Code | Meaning |
|---|---|
| `observed` | Seen directly and stored as it was (an AI answer, a page as served, a count from either) |
| `modeled` | An estimate produced by someone's model |
| `stated` | A claim someone makes about themselves |
| `finding` | A conclusion from a test, study or ruling |
| `opinion` | A view or experience someone shares |

### `grade`: fitness for this specific use

A, B or C, as defined in the source registry. A grade belongs to a use, not to a source: one Reddit extract can be A for where Reddit appears and C for what a thread claims. The registry's rule stands: a claim needs one A, or two Bs from different owners.

## The lane is looked up, not chosen

| origin | kind | Lane (what the reader sees) | Example |
|---|---|---|---|
| `stratemai` | `observed` | Custom research | Zoom named in 12% of receptionist answers |
| `client` | `observed` | Client public sources | The start guide lists a Zoom Phone licence, read by hand on a date |
| `client` | `stated` | Client-reported | Zoom Virtual Agent customers up 256% |
| `vendor` | `modeled` | Third-party tool | About 18,000 purchase-intent prompts, modeled |
| `vendor` | `observed` | Third-party tool | Status codes from a vendor crawler on a stated date |
| `independent` | `finding` | Published research | A study's runs-per-prompt finding; an NAD ruling |
| `public` | `opinion` | Public commentary | What a Reddit thread says about setup |

A combination not in this table cannot reach a deliverable until a lane is decided and added here. That is the guardrail: nothing gets a label by feel.

Two cases that look alike and are not:

- **Counting Reddit citations** is `stratemai + observed`, so Custom research. **Quoting what a thread says** is `public + opinion`, so Public commentary.
- **A client's page as served** is `client + observed`. **A figure the client announces** is `client + stated`. The first shows what buyers and engines can read; the second is the company's word.

## Rules

1. **Never blend lanes in one sentence.** If a point needs two lanes, use two sentences, each labelled.
2. **Third-party tool numbers are never multiplied into a payoff.** A vendor's modeled volume times your measured rate produces a number that looks measured and is not. Use vendor figures for scale and direction only.
3. **Client-reported figures stay at the scope the client gave.** A product-line figure is not a product figure. A correlation the client reports is labelled as a correlation.
4. **Public commentary is illustration, not proof.** It shows what buyers say, never how many say it, unless Brad counted it (which makes the count Custom research).
5. **A fact an agent reported but nobody read does not reach a deliverable.** A person reads the source before the claim is used. This rule exists because a support article once reached a slide on an agent's "reported, not read" tag.
6. **Every client-facing number is recomputed from stored data** by code separate from the collector, or labelled "not yet recomputed." Code that collected the data shares its bugs; separate code catches them.
7. **Retired numbers are listed and never reintroduced.** Each case keeps a retired list with reasons, and every later draft is checked against it.
8. **Outside AI research is never evidence.** Deep-research outputs and model reviews are how something was found. Every claim taken from them is re-sourced and tagged by its real origin.

## Naming conventions

- **Codes and labels are separate.** Codes (`stratemai`, `observed`) are lowercase with underscores and never change once data uses them. Lane labels are for readers and can be reworded here without touching data.
- **One word, one meaning.** Each code has one definition, in the glossary. Retired words: "measured" and "reported" as lane names, and "Observed" as a slide label. Use the fields above instead.
- **Deprecate, don't rename.** A replaced code is marked retired with a pointer to its successor.
- **No compound codes.** `vendor_modeled` packs two answers into one word; it splits into `vendor` + `modeled`.

### Mapping from the Oct 20 registry draft

| Registry lane (retired) | Becomes |
|---|---|
| `measured` | `stratemai` + `observed` (and `client` + `observed` for client pages captured by hand) |
| `vendor_modeled` | `vendor` + `modeled`, or `vendor` + `observed` for a vendor's crawl facts |
| `reported` | `client` + `stated`, or `independent` + `finding`, or `public` + `opinion` |

The registry's claim types map the same way: `observed`, `estimated` (now `modeled`), `company_stated` (now `stated`), `independent_finding` (now `finding`), `user_voice` (now `opinion`).

## How to apply

Before a deliverable goes out:

1. List every number and every quoted claim.
2. Give each its origin, kind, grade and source row in the case's numbers ledger.
3. Look up the lane. Anything without a lane stops here.
4. Check each sentence for more than one lane.
5. Check no Third-party tool number is multiplied by anything.
6. Check every number against the retired list.
7. Mark each number recomputed or not yet recomputed.

## What to record

The numbers ledger for each case lives with the case data, not here. Each row carries: the figure, numerator and denominator, surface, dates, origin, kind, grade, lane, source id, recomputed (yes or not yet, by what, when), and status (live or retired, with reason).
