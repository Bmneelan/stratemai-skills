# CLAUDE.md

The Wayfinder workbench. Read `README.md` for scope and the sorting rule, and `INVENTORY.md` for what exists.

## Standing rules

- Never open, print or log `.env` or any key value. Do not make billed API calls unless Brad asks for a specific run.
- No AI authorship attribution anywhere: no `Co-Authored-By` trailers, no "generated with" lines in commits, files or READMEs. Commit as `brad.neelan@stratemai.com`.
- Right to Win is an industry-standard framework. Skills encode Brad's application of it, never a claim of authorship.
- Do not call anything an agent unless it runs a loop with tools toward a goal. A script, a protocol or a prompt is not an agent.
- Stop and report before deleting or moving any existing file.

## Sorting rule

Method lives here; data lives with whoever owns it. Raw runs, ledgers and case data stay in `research-corpus`. Evidence files are client data and stay gitignored. Forge ventures use the instruments like any client; their data, frames and decisions never enter this repo.

## Skill authoring

- Each skill is a folder with a `SKILL.md`. YAML frontmatter holds `name` (matching the folder) and `description`.
- The description carries all the when-to-use logic. The body is for how.
- Body under 500 lines. Imperative instructions. Explain why a rule matters rather than stacking MUSTs.
- Instruments follow a fixed order: what it measures, when to use it, protocol, pass bar, what it does not claim, what to record.
- Reference results name the client and the month ("Zoom case, Oct 2026"), since that helps navigation. They carry counts and what was learned, never the underlying answers, citations or client material.

## Language rules that apply to every skill

- "Cite," never "retrieve," unless the Closed Book Live API Model has run.
- "Working explanation" or "leading hypothesis," never "cause."
- Every number carries surface, sample and dates, and one evidence lane.
- No em dashes in deliverable text.

## Repo conventions

- Update `INVENTORY.md` in the same commit as any skill change.
- Stubs say they are stubs in the first line of the body.
- Schemas live under `research/schemas/` and are versioned by `$id`.
