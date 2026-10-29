---
name: citation-classes
description: Classify the URLs an AI answer cites into source classes (competitor-owned, review or listicle, Reddit, client-owned, other) and report whose pages carry the answers. Use when analysing citations from ChatGPT, Gemini, Perplexity, Google AI Overviews or similar, when someone asks which sources an engine relies on for a category, when sizing how much of an answer set rests on competitors' own pages, or before putting any citation share into a deliverable.
---

# Citation classes

## What it measures

Who owns the pages an AI answer cites. The question behind it is whose voice the engine is repeating when it answers a buyer's question: the client's, a competitor's, a reviewer's, or the crowd's.

## When to use it

On any run that stores citations with URLs. It is most useful on answers that name competitors and not the client, because those are the answers where the source mix explains the gap.

## Classes

| Class | What belongs in it |
|---|---|
| Competitor-owned | Pages on a domain owned by a company competing in the category |
| Review or listicle | Review sites, comparison pages, "best X" lists, analyst roundups not owned by a competitor |
| Reddit | reddit.com threads |
| Client-owned | Any domain the client owns, including help centres, docs, blogs and community sites |
| Other | Everything that does not fit above: news, encyclopaedias, government, unrelated vendors |

Open item: a sixth class for pages cited as a source about other companies (a vendor's page used by the engine to describe a different company). It is defined here as a candidate and reserved in the evidence file schema (`source_about_others`), but no collector assigns it yet. Until it is, these pages fall into whichever owner class their domain matches, and that limitation is stated when it could matter.

## Protocol

1. Extract every cited URL from every answer in scope. Keep the answer identifier with each citation.
2. **Pass 1, known domains.** Classify by a domain list maintained per category: client domains, named competitors' domains, known review and listicle sites, Reddit. Everything else is "unknown."
3. **Pass 2, unknown domains.** Classify the unknowns as a separate, recorded pass. A person (or code a person has checked) looks at each unknown domain and assigns a class. Record who did it, the date and the decision per domain. When the before and after figures differ by more than a few points, have a second person classify a sample of the Pass 2 domains independently and record their agreement, since the after figure rests on those calls. This pass exists because unknown domains in a category are often small competitors, and leaving them unclassified understates the competitor share.
4. Always report both figures, before and after Pass 2. The before figure uses only domains listed up front, so it is a floor nobody can dispute. The after figure depends on a person's calls about unknown domains. Showing both lets the reader see how much of the result rests on that judgment, and the gap itself shows how much of the source base sits on companies nobody listed up front.
5. Count at two levels, and never mix them under one definition:
   - **Share of answers citing a class:** of N answers, how many cite at least one page in the class.
   - **Share of citations in a class:** of M citations, how many are in the class.

   These answer different questions. Answer share says how often a buyer sees the class at all; citation share says how much of the source base the class holds. Putting an answer-level number under a citation-level definition is a real build error that has happened before; label every figure with its level.

## Pass bar

There is no agreement threshold for the classes themselves, because class assignment is a lookup plus a recorded judgment rather than a reading of meaning. The bar is completeness: every citation in scope is classified, the unknown-domain pass is recorded, and each reported figure names its level.

## Reference result

Zoom case, Oct 2026 (enterprise SaaS): 145 unbranded AI Receptionist answers that named competitors and not Zoom, holding 810 citations. Share of citations that were competitor-owned: 53% before the unknown-domain pass, 71% after. Reviews and listicles 5%, Reddit 1%, Zoom-owned 0% (all share of citations). Most cited: Smith.ai's receptionist pricing page, RingCentral's receptionist pricing page and Goodcall's home page. The Pass 2 calls were one person's and were not checked by a second.

## What it does not claim

- It does not show what the engine read. Citations are what the answer shows, not everything retrieved. Say "cite," never "retrieve."
- It does not show that a cited page caused an answer's content.
- Class shares are properties of the prompt set and the dates. They do not generalise to the category at large.

## What to record

Store with the run:

- The domain list used in Pass 1, with its date.
- The Pass 2 log: each unknown domain, the class assigned, who assigned it, the date.
- Counts per class at both levels, before and after Pass 2.
- The most-cited URLs per class, with counts.
- Whether the "cited as a source about others" class was applied.
