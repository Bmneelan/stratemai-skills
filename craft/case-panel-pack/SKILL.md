---
name: case-panel-pack
description: Build a numbered handoff pack (files 00 to 10) that lets a reviewer or a fresh chat pick up a case cold, with the brief, deck text, numbers ledger, rules, decisions, QA status, open questions, sources, parked ideas and data approaches. Use when handing a case to an outside reviewer, starting a new chat on an existing case, preparing for a panel or readout, or whenever a case has grown past what one conversation can hold.
---

# Case panel pack

## Why

A case that lives in one long chat can't be reviewed independently. Splitting it into numbered files with fixed jobs lets a fresh reader find the rules before touching a slide, the ledger before touching a number, and the decisions log before reopening a settled question. It also lets a reviewer who has not seen the work built test it without inheriting its assumptions.

## The files

Copy `template/` into the case's own location (never into this repo) and fill each file.

| File | Holds | Read it when |
|---|---|---|
| `00-readme.md` | What the pack is, the case in one paragraph, standing constraints, files not in the pack | First, always |
| `01-brief-and-audience.md` | The brief, the audience, what they care about, how the deliverable maps to both | Before producing anything |
| `02-deck-text.md` | Every slide's text and speaker notes, in order, with version | Reviewing or rewriting a slide |
| `03-numbers-ledger.md` | Every number with numerator, denominator, surface, dates, lane, source and recompute status; the retired list | Before touching any number |
| `04-rules-and-style.md` | Standing rules for slides, wording, lanes and process | Before producing anything |
| `05-decisions-log.md` | What was decided, when, why, and what was rejected | When a question feels already answered |
| `06-qa-status.md` | Each outside review, item by item, with status | Checking what has been fixed |
| `07-open-questions.md` | What is unresolved, what a fresh analysis should test, the strongest case against | Running a new analysis |
| `08-sources-and-context.md` | Facts used with sources, outside research used, what is private and must not appear | Citing anything |
| `09-parked-ideas.md` | Ideas set aside, with why and what would bring them back | Before proposing something new |
| `10-data-approaches-and-confidence.md` | How the evidence was built, how confident to be, soft spots, retired numbers, rules for touching numbers | Defending or challenging the method |

## How to fill it

1. Start with 03 and 10. The ledger and the method are what every other file depends on.
2. Write 00 last, once the rest exists.
3. Keep the pack versioned with the deck. When the deck version changes, update 02 and the ledger in the same pass.
4. Anything private (internal data shared to pressure-test, personal notes) is named in 08 as excluded, and never appears in any file.
5. Ask the reviewer to read 00, 04 and 07 before anything else.
