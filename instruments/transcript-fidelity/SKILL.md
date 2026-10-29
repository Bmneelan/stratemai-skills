---
name: transcript-fidelity
description: Compare two AI transcriptions of the same session by scoring claims and named entities rather than word error rate, to show whether names, numbers, negations and product terms survive. Use when a client's keynote, webinar, earnings call or other spoken content is processed by third-party AI (note-takers, captioning, summarisers), when checking which transcript to treat as the source of record, or when testing how a brand's vocabulary degrades in someone else's AI.
---

# Transcript fidelity

## What it measures

Whether the meaning of spoken content survives AI transcription and summarisation. It scores the things a reader acts on: who was named, which products and partners, what the numbers were, and whether a negation survived. Word error rate misses the errors that matter most here. A transcript can get 95% of words right and still flip "fewer than half" to "more than half."

## When to use it

- To decide which of two transcripts is the source of record before quoting a session.
- To show a client how their newer product names, partner names and claims degrade when their content passes through someone else's AI. It is the same mechanism as answer engines repeating old names, seen in a different tool.

## Protocol

1. **Align a comparison window.** Use only the stretch both transcripts cover. Record start and end times and what the window contains.
2. **Build the reference list.** From the most reliable source available (official transcript, published slides, the client's own pages), list every person, product, partner, number and polar claim (anything with "not," "fewer," "never," "without") in the window. Check spellings against primary sources.
3. **Score each transcript against the reference on four dimensions:**

   | Dimension | Question | Score |
   |---|---|---|
   | Entity accuracy | Is each person, product and partner name recognisable as the right entity? | Correct / recognisable but misspelled / lost or wrong |
   | Number accuracy | Does each number survive with its unit and scope? | Correct / wrong / lost |
   | Polarity accuracy | Did each negation or comparative survive? | Preserved / inverted / lost |
   | Summary faithfulness | Does the tool's summary assert anything absent from both transcripts? | Count of unsupported assertions, each listed |

4. **List material differences.** For each moment where the transcripts disagree on something a reader would act on, quote both and state the effect (meaning inverted, claim lost, name lost).
5. **Note structural differences:** speaker labels, coverage, whether a summary exists.

An inverted polarity or an unsupported summary assertion counts more than any number of misspellings, because it changes what the reader believes. Report those first.

## Pass bar

No single threshold yet; the pilot sets the rubric, not the bar. Until a benchmark exists, report scores per dimension and lead with inversions and unsupported assertions. A transcript with any inverted claim in the window is not used as a source of record for that window.

## Reference result

Pilot, Oct 2026, one keynote, two tools, about 40 minutes of overlap. One tool inverted a statistic ("fewer than half" became "more than half"), lost a multi-part analyst claim, and garbled most product and partner names. Its summarizer named an older product name that appeared in neither transcript. Both tools misspelled some people's names. The more accurate tool also had the shorter coverage: a reliable capture and an accurate one were not the same tool that day.

## What it does not claim

This is a pilot, not a benchmark: one session, one listener setup. Capture conditions (speaker audio, room noise, network interruptions) affect results. It says nothing about either tool's accuracy in general.

## What to record

Store with the case, not in this repo: the session, the tools and their settings, the capture setup, the comparison window, the reference list with sources, scores per dimension per tool, the material differences table, unsupported summary assertions, and which transcript was made source of record. Quotes taken from the less reliable transcript where the other has no coverage are marked "unverified."
