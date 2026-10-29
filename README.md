# stratemai-skills

The Wayfinder workbench. Every method, instrument, research rule and craft skill Brad Neelan uses for marketing and business research lives here, in one repo.

## Scope

Consult and Crew engagements draw on this repo. Forge ventures (DefendFam and similar) use its instruments the way a client would. Octomai, the operating harness, is a separate project and is out of scope.

## Sorting rule

**Method lives here; data lives with whoever owns it.**

Raw runs, ledgers and case data stay in `research-corpus`. Evidence files are client data and are gitignored here. A skill may cite a reference result (a count and what it taught) so the reader knows what the instrument has already shown. It never carries the underlying answers, citations or client material.

## Forge boundary

Forge ventures are clients of this workbench, not contributors to it. Their data, research frames and decisions never enter this repo. If a Forge project produces a better method, the method comes here, stripped of the venture's data, the same way it would from any engagement.

## Layout

| Folder | Holds | Status |
|---|---|---|
| `methods/` | The analytical frameworks: Intent Modeling, Right to Win, Entity and Semantic Mapping | Stubs |
| `instruments/` | Measurement protocols, each with a pass bar and a list of what it does not claim | Drafts |
| `research/` | Governance for research runs: evidence lanes, study design, the evidence file schema | Drafts |
| `craft/` | How findings become deliverables: deck rules, the case panel pack | Drafts; voice is a stub |
| `glossary/` | Shared vocabulary | Placeholder |
| `agents/` | Anything that runs a loop with tools toward a goal | Stub |

`INVENTORY.md` is the running list of what exists anywhere in the workbench, built or not, and where it lives.

## How to add a skill

1. Pick the folder by what the skill is: a way of thinking (`methods/`), a way of measuring (`instruments/`), a rule for evidence (`research/`), or a way of presenting (`craft/`).
2. Create `<folder>/<skill-name>/SKILL.md` with YAML frontmatter holding `name` and `description`. The description carries all the when-to-use logic, because it is what decides whether the skill is picked up.
3. Keep the body under 500 lines. Write instructions in the imperative, and say why a rule matters instead of stacking hard requirements.
4. Instruments state, in this order: what it measures, when to use it, the protocol, the pass bar, what it does not claim, what to record.
5. Add or update the row in `INVENTORY.md` in the same commit.
6. No client data, no keys, no AI authorship lines.
