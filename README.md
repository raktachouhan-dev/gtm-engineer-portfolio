# GTM Engineer Portfolio - Rakta Chouhan

RevOps and Sales Ops professional (10+ years) moving into GTM engineering. This repo links four small builds that all use the same ICP scoring model, so you can compare how the same logic looks in each tool.

## The scoring model (identical in every build)

Score a PE / investment-firm account out of 100:

- Fund size (AUM): 50bn+ = 30, 10bn+ = 22, 2bn+ = 14, else 6
- Strategy: Buyout or Private Credit = 25, Growth Equity = 18, Real Estate = 12, Venture = 8, other = 5
- HQ country: US = 15, UK = 12, DE = 10, SG = 8, other = 4
- Raised in the last 12 months: +20
- Debt maturing within 12 months: +10
- Cap at 100. Tier A = 70+, Tier B = 40-69, Tier C = below 40

Test data is 8 fictional firms (example domains only). Expected scores: Northfield 100 (A), Alder 89 (A), Summit Ridge 82 (A), Meridian 69 (B), Harbor Lane 52 (B), Brightwater 47 (B), Quill 28 (C), Kestrel 18 (C).

## The four builds

| Tool | What it does | Where to see it |
|---|---|---|
| n8n | Workflow that scores firms from a CSV and routes by tier | [pe-account-scoring-n8n](https://github.com/raktachouhan-dev/pe-account-scoring-n8n) |
| Python | Scoring library and HubSpot company upsert client with retries, dry-run mode and unit tests | [revops-hubspot-toolkit-python](https://github.com/raktachouhan-dev/revops-hubspot-toolkit-python) |
| Clay | Table with an ICP Score formula, tier column and outreach opener, checked against the repo scores | Live walkthrough on request (private workspace) |
| Make | Webhook, score calculation, a score >= 70 filter, then a HubSpot company create through the HubSpot API | Live walkthrough on request (private workspace) |

## What has and has not been tested

- Python scorer: 7 unit tests pass, including all 8 sample firms.
- Python HubSpot client: tested with mocked HTTP responses only, not against a live account.
- Make scenario: run live against a real HubSpot account. A Tier A firm created a company record. A Tier C firm was stopped by the filter. Both runs used fictional test data.
- Clay: all 8 scores and tiers match the Python results. No paid credits used.

## Skills shown

Lead scoring and ICP design, CRM data hygiene, HubSpot API (service keys, scopes, upsert by domain), webhook-driven automation, API retry handling, testing, and documenting a workflow so someone else can run it.

Contact: LinkedIn and email on request.
