# Inventory

Running list of everything in the Wayfinder workbench, built or not, and where it lives. Seeded Oct 29, 2026 from the workbench sections of `claude/workbench-inventory.md` (Oct 28). Add a row when something is made; move a row when its home changes. Update this file in the same commit as any skill change.

Sorting rule: method lives here; data lives with whoever owns it. Forge, Octomai and site items are tracked outside this repo.

Status: **built**, **draft** (written here, not yet used on a case), **partial**, **spec** (written, not built), **protocol** (method defined, not encoded as a skill), **stub**, **idea**.

Location: a path means this repo. `repo <name>` means a separate GitHub repo under Bmneelan. Anything else is where the item lives today, outside any repo.

---

## Methods

| Item | Status | Location | Note |
|---|---|---|---|
| Intent Modeling (Learn / Discern / Compare / Transact / Return) | stub | `methods/intent-modeling/` | Defined on stratemai.com; full build Phase 2 |
| Right to Win (Defend & Dominate / Compete & Challenge / Evaluate & Test) | stub | `methods/right-to-win/` | Industry framework; the staging is Brad's; full build Phase 3 |
| Entity and Semantic Mapping | stub | `methods/entity-semantic-mapping/` | Also a product line; full build Phase 2 and 3 |
| Stratemai Stack visual | built, not deployed | artifact | Six layers |
| Wayfinder Radar (signal harmonization across third-party tools) | named system | site copy | Origin: RADAR at Intuit |
| Wayfinder Retrieval (applied AI/ML) | named system | site copy | Origin: QBSI |
| Shadow Map / AI Query Inference | idea | memory | Name not locked |
| Conversational Spend Gap (answer-to-auction gap) | idea | memory | Name not locked |
| Discovery Displacement Engine | idea | memory | Name not locked |
| Causality tool ("What actually moved it") | parked | chat, Sep 22 | Scripts first, validated in Developer Mode |

## Instruments

| Item | Status | Location | Note |
|---|---|---|---|
| Answer Engine Check | partial (Group 1) | repo `answer-engine-check` | Parked; Group 2 prompt written. Stays in its own repo |
| Rubric-stability harness | built | repo `rubric-stability` | To fold into research-corpus |
| Warm Path Overlay | built | repo `warm-path` | LinkedIn export against prospect lists |
| Answer reliability hand-check (30 answers, per-label agreement, 80% bar) | draft | `instruments/answer-reliability-handcheck/` | Ported from the Oct 2026 panel pack |
| Reference denominators by surface | draft | `instruments/reference-denominators/` | |
| Rendering check (raw vs rendered word count) | draft | `instruments/rendering-check/` | Reference: 56 of 147 |
| Citation classes | draft (skill); partial (code) | `instruments/citation-classes/`; code in `analyze.mjs` | "Cited as a source about others" class not yet in code |
| Offline sensitivity test | spec | `instruments/offline-sensitivity-test/` | Not yet run |
| Transcript fidelity | draft (from a pilot) | `instruments/transcript-fidelity/` | Pilot write-up: `claude/transcript-fidelity-pilot-zoomtopia-keynote.md` |
| Dual note-taker entity check | idea, first tried | Zoomtopia | Candidate to fold into transcript fidelity |
| Zoommate probe | run once | `claude/zoommate-probe-2026-10-20.md` | |

## Research engine and governance

| Item | Status | Location | Note |
|---|---|---|---|
| research-corpus (collectors, frames, ledger, raw data) | built | repo `research-corpus` | Stays the engine; rules move here |
| research-run skill | built | repo `research-corpus` | Pointer in `research/research-run/`; skill moves at consolidation |
| Evidence lanes, recomputation, retired numbers | draft | `research/evidence-lanes/` | |
| Study design rules (Sep 2026 calibration) | draft | `research/research-run/study-design.md` | |
| Evidence file schema v0.1 | draft | `research/schemas/evidence-file.schema.json` | Shared by research-corpus and answer-engine-check; neither emits it yet |
| Tier system 0 to 3 with `decision` flag and `--trend` | built | repo `research-corpus`, commit edf58b9 | |
| Source registry with lane field (measured / vendor_modeled / reported) | queued | `claude/machinery-registry-draft.md` | Machinery item 1; lane names should match `research/evidence-lanes/` |
| Governance update (evidence rules, hand-check, DECISIONS.md, lessons.md, no-AI-attribution) | queued | `claude/machinery-queue.md` | Machinery item 2; partly covered by this repo, to redraft |
| Research agent charter | spec | `claude/research-agent-charter.md` | |
| Research OS | idea | memory | Repeated deep research as a system |
| `credit-check.mjs`, `serp.mjs`, `serp-report.mjs` | built | repo `research-corpus` | |
| `shadow-gemini.mjs` | built | location unknown | Find it |
| Verification step and skeptic pass | unconfirmed | repo `research-corpus` | Status check |
| Backlog of machinery ideas | list | `claude/machinery-backlog.md` | |

## Findings (evidence that the method works)

Write-ups stay where they are; the data behind them stays in research-corpus.

| Item | Location |
|---|---|
| Rubric stability | `claude/rubric-stability-finding.md` |
| Consideration set | `claude/consideration-set-finding.md` |
| Retrieval surface | `claude/retrieval-surface-finding.md`; artifact "Selection, Not Retrieval" |
| Instrument validation | `claude/instrument-validation-finding.md` |
| Read but not chosen | artifact "Read But Not Chosen" |
| Reddit as third-party source | `claude/reddit-third-party-finding.md` |
| Method vs Profound | artifact "Research Method vs Profound"; `claude/profound-trial-read-2026-10-19.md` |
| Search Atlas site audit | `claude/search-atlas-site-audit-2026-10-18.md` |
| AI content and watermarks (desk research) | `claude/ai-content-watermark-research-2026-10-27.md` |

## Craft

| Item | Status | Location | Note |
|---|---|---|---|
| Deck rules | draft | `craft/deck-rules/` | Generalised from `claude/zoom-deck-rules-2026-10-22.md` |
| Case panel pack (00 to 10) | draft | `craft/case-panel-pack/` | Template headings in `template/` |
| Stratemai voice | stub | `craft/stratemai-voice/` | Drafted after real output exists |
| Presenting (pacing, slide count) | notes | memory | |
| Executive teach-back on answer engines | built | Zoom chat | Template candidate |
| Interview dossier and crib sheet format | built | artifacts (Kim Storin, Will Nye) | Template candidate |
| Visual system for a final round | built | artifact "Zoom Final Round · Visual System" | |
| Paid search account build (structure, manager account for API) | partial | DefendFam work | Method belongs here; account stays in Forge |

## Glossary

| Item | Status | Location |
|---|---|---|
| `glossary.json` (47 entries) and `glossary.md` | built | Wayfinder engineering chat; lands in `glossary/` in a later commit |

## Agents and plans

| Item | Status | Location | Note |
|---|---|---|---|
| Wayfinder diagnostic | stub | `agents/wayfinder-diagnostic/` | Phase 4 |
| Wayfinder Agent Plan v2 | spec | `Wayfinder Agent Plan.md` | v3 pending |
| Wayfinder component board | built | artifact | |
| Research agent | charter only | see Research engine above | |
| MCP server for Wayfinder | deferred | decision | Phase 5 |
