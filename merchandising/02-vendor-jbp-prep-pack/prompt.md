# Vendor JBP Prep Pack

I'm a Category Manager prepping for a Joint Business Plan meeting with one of our pantry vendors next week. They're going to walk in with a deck of their own and a request: 4% cost increase across all SKUs, two new SKUs to be reviewed, and a soft ask about expanding their share of our pantry set. I need to walk in with the receipts.

Right now, building this prep takes me the better part of a day. I pull 12 months of sales out of our BI tool, paste in-stock and fill data from a separate report, dig through the quality-issues log, and try to remember which promos they participated in. Then I write a one-pager myself. By the time I'm done I've spent 6 hours on Excel surgery and 30 minutes thinking about the actual negotiation. I want that ratio flipped.

I've attached four files for this vendor (Northpine Provisions, vendor ID V-44182):
- `vendor-profile-northpine.md` — relationship history, current SLAs, commercial terms, known issues going into the JBP
- `vendor-sales-trend-northpine.csv` — 12 months of unit and dollar sales by SKU, with prior-year comparison
- `in-stock-and-fill-history.csv` — weekly in-stock %, fill rate, and lead time by SKU vs SLA
- `quality-issues-northpine.json` — every quality complaint or FC incident in the last 9 months

## What I need you to build

Using all four files, give me a single-page negotiation prep pack with the following structure:

1. **Top-of-page snapshot.** Vendor name, total net sales last 12 months, YoY growth %, current overall SLA status (Green/Yellow/Red with one-line justification), number of open quality issues, and a one-line "headline" I can lead the meeting with.

2. **Where they're winning.** Three bullets. Each tied to a specific SKU or metric — growth rate, in-stock above target, low complaint rate, strong promo participation. No vague flattery; cite the numbers.

3. **Where they're failing us.** Three to five bullets. Rank by negotiating leverage, not by severity to FSQA. Each bullet pairs the issue with the SLA or commitment it's violating. Open quality issues count more than closed ones. NP-1031 should jump out — cross-reference the supply problems in the in-stock file against the quality issues against the sales trajectory.

4. **What to ask for.** Three to five concrete asks I can put on the table. Each ask should be defensible from a specific data point in the files. Examples of the shape I'm looking for: "Hold the line on the proposed cost increase for NP-1031 until the open allergen-labeling issue is closed and 90 days of in-stock data exceeds 95%." Don't give me vague asks like "improve service" — give me asks tied to numbers and dates.

5. **What I should NOT bring up.** One or two short bullets — things that look bad on paper but where we don't have leverage, or where pushing now would hurt the relationship vs. a different meeting. Helps me hold my fire.

6. **Open questions for the vendor.** Three short questions whose answers would change my asks. These go at the end so I remember to actually ask them.

Output as clean markdown that fits on a single screen. No tables wider than 4 columns. Sections clearly labeled. If a number rounds awkwardly, round it; don't make me read 37853.

## Why this matters

This is the meeting where I either anchor the conversation or I react to theirs. I don't need you to summarize the data — I have the data. I need you to *connect* the supply issues to the quality issues to the sales trajectory to the cost-increase request, so I walk in with a thesis: which SKUs are pulling weight, which are dragging, what we're willing to trade, and where we hold the line. The output is a tool for a negotiation, not a report.

## After the first cut, I want to try

- A "vendor view" version — same data, framed as how Northpine will probably present it (i.e., what story can THEY tell with the wins, so I'm not surprised).
- Re-running with stricter cutoffs: any SKU below 95% in-stock for 4+ consecutive weeks is treated as at-risk for delisting.
- Adding a "scenario" section: if we approve the 4% cost increase, what's the implied retail price change and the margin impact at current volumes.

## Stretch goals (optional)

- Calculate the dollar impact of the open quality issues (units affected × list cost) and propose a credit ask.
- Score each SKU on a 1-10 "keep / negotiate / cut" framework using growth + service + quality together.
- Draft the email I send Northpine the day after the JBP recapping commitments.
- Set this up as a template so I can drop in any vendor's four files and get the prep pack on demand — eventually triggered automatically the week before any scheduled JBP.
