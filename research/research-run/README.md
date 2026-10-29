# research-run

Governance pointer. The research-run skill itself stays in `research-corpus` until consolidation. This folder holds the rules every run follows, so they live with the method rather than with the data.

| File | Holds |
|---|---|
| `../study-design/` | Study designs; the first is AI answer naming, from the Sep 2026 calibration runs |
| `../evidence-lanes/SKILL.md` | Lane labels, recomputation and the retired-numbers rule |
| `../schemas/evidence-file.schema.json` | The evidence file shared by `research-corpus` and `answer-engine-check` |

Instruments a run calls on are under `instruments/`: the Human Audit before any rate is reported, citation classes, reference denominators, the rendering check, and the Closed Book Live API Model before any causal language.

Collectors are not here. Phase 1 collectors wait on two decisions: whether the harness replaces `model_probe.py`, and which probe set to use.
