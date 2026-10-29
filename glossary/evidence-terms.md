# Evidence terms

Codes used on every number (see `research/evidence-lanes/`). Codes never change once data uses them.

## origin

| Code | Definition | Example | Not this |
|---|---|---|---|
| `stratemai` | Brad's own collection or analysis | Naming rate from a frozen prompt set | A vendor dashboard figure, even if Brad pulled it |
| `client` | The client company, through its pages or its statements | A support article; an earnings figure | A press article about the client |
| `vendor` | A commercial tool's output | Profound prompt volume | A vendor's published study (that is `independent`) |
| `independent` | Researchers, analysts, test labs, regulators, courts | A study's finding; an NAD ruling | A vendor quoting an analyst (find the analyst's own page) |
| `public` | Customers and communities | A Reddit thread; a retailer review | A count of Reddit citations (that is `stratemai`) |

## kind

| Code | Definition | Example | Not this |
|---|---|---|---|
| `observed` | Seen directly and stored as it was | An AI answer captured verbatim; a page as served on a date | A modeled traffic estimate |
| `modeled` | An estimate from a model | Modeled prompt volume; CPC estimate | A count from stored answers |
| `stated` | A claim someone makes about themselves | "Customers up 256%" from earnings | What the client's page shows a buyer (that is `observed`) |
| `finding` | A conclusion from a test, study or ruling | A lab's test result | A press summary of the finding (go to the source) |
| `opinion` | A view or experience someone shares | "Setup took five minutes" in a review | How many reviews say it (count it: `stratemai` + `observed`) |

## grade

| Code | Definition |
|---|---|
| `A` | Fit to carry a claim on its own, for this use |
| `B` | Fit only with a second B from a different owner |
| `C` | Context or a lead; never carries a claim |

## lane (looked up from origin + kind)

| Code | Label | origin + kind |
|---|---|---|
| `custom_research` | Custom research | `stratemai` + `observed` |
| `client_public_sources` | Client public sources | `client` + `observed` |
| `client_reported` | Client-reported | `client` + `stated` |
| `third_party_tool` | Third-party tool | `vendor` + `modeled` or `observed` |
| `published_research` | Published research | `independent` + `finding` |
| `public_commentary` | Public commentary | `public` + `opinion` |

## Retired

| Retired | Use instead |
|---|---|
| `measured` (registry lane) | `stratemai` + `observed` |
| `vendor_modeled` (registry lane) | `vendor` + `modeled` |
| `reported` (registry lane) | `client` + `stated`, `independent` + `finding`, or `public` + `opinion` |
| `estimated`, `company_stated`, `independent_finding`, `user_voice` (registry claim types) | `modeled`, `stated`, `finding`, `opinion` |
| "Measured", "Observed", "Reported", "Vendor" (old slide labels) | The lane labels above |
