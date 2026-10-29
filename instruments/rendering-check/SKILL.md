---
name: rendering-check
description: Compare raw HTML word count against rendered word count on a client's cited or target pages to flag content that only appears after the page runs JavaScript. Use when auditing whether client pages are readable by AI crawlers and answer engines, when a page that should be cited is not, or when preparing a technical-risk section for an AI visibility readout. Reports a technical risk to retrieval, never a cause of omission.
---

# Rendering check

## What it measures

How much of a page's text is present in the raw HTML the server returns, versus how much appears only after the page runs in a browser. Many crawlers, including some AI engines' fetchers, read raw HTML or render inconsistently. Text that loads late may never be seen.

## When to use it

On every client page an answer cites, and on every page you intend to change as part of a test. Run it early: if a target page fails, any test that edits its content is confounded until rendering is fixed.

## Protocol

1. List the pages in scope with their URLs and the reason each is in scope (cited, or a test target).
2. For each page:
   - Fetch the raw HTML without executing scripts. Strip tags, scripts, styles and navigation boilerplate the same way for every page. Count words.
   - Load the same URL in a headless browser, wait for network idle, then extract visible body text with the same stripping rules. Count words.
   - Compute the late share: (rendered minus raw) divided by rendered.
3. Flag any page where the late share is above 50%, meaning more than half its words load after the page opens.
4. For each test target, record pass or flag individually. Whether a specific target is affected is a check you run, not a finding you infer from the sample rate.

Use the same user agent, viewport and wait rule for every page, and record them. Different settings produce different counts, and the comparison is only meaningful within one setup.

## Pass bar

A page passes if its late share is 50% or less. The sample figure (flagged of total) is reported with its denominator.

## Reference result

Oct 2026 enterprise SaaS case: 56 of 147 cited client pages flagged. Whether the three test-target pages were among them was set as a week-1 check, not reported as a finding.

## What it does not claim

- It does not show that an engine failed to read a page. Engines render differently and change without notice.
- It does not explain why a client is or is not named. Report it as a technical risk to retrieval, never as a cause of omission.
- Word count is a proxy. A page can pass on words and still hide the one fact that matters behind a tab or accordion; check the specific facts on test targets by hand.

## What to record

Store with the run:

- Each URL, raw word count, rendered word count, late share, flag.
- Fetch date, user agent, viewport, wait rule and the stripping rules.
- For test targets: whether each key fact appears in raw HTML, checked by hand.
