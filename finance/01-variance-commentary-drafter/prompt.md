I'm an FP&A analyst at a mid-sized DTC subscription company. It's the morning after month-end close and the Executive Flash is due to the CFO by noon. The pattern is always the same: GL locked at 7am, I spend two hours pulling actuals against the AOP and prior-year comp into a single view, another hour staring at the dollar/percent variances trying to remember why marketing overspent in week three, then I draft commentary that the FBPs will rewrite anyway. I want to compress the first three hours into thirty minutes and walk in with a real point of view.

I have four files this morning:
- `actuals-current-month-2026-04.csv` — locked GL actuals by line item (revenue, COGS, marketing, opex categories).
- `budget-aop-2026-04.csv` — the AOP plan for the same month, same line items.
- `prior-year-2025-04.csv` — same-month actuals from last year for YoY comp.
- `business-context-notes.md` — running notes I keep through the month: campaign launches, vendor changes, one-time items, anything that explains a number before I have to dig for it.

Using all four files, build me a **first-pass executive flash variance pack** structured as follows:

1. **Headline summary (3 lines max)** — total revenue vs AOP and vs PY in dollars and %, total contribution margin vs AOP and vs PY, and a one-line "the story this month" sentence. No hedging — pick the story.
2. **Top variance table** — every line item from the actuals file, with columns: Line Item, Actual, AOP, $ Var vs AOP, % Var vs AOP, PY Actual, $ Var vs PY, % Var vs PY. Sort by absolute dollar variance vs AOP (largest first). Mark each row with a flag: Favorable / Unfavorable / Neutral (Neutral = within ±2% AND under $50K abs variance).
3. **Top 5 variances — first-pass commentary** — for the 5 largest absolute dollar variances vs AOP, write 1-2 sentence commentary in the voice of an FP&A analyst. For each, you MUST attempt to tie the variance to a driver from `business-context-notes.md`. If a clear driver exists, name it ("driven by the GLP-1 audience expansion test launched April 7, expected per plan"). If no driver matches, say so explicitly ("no documented driver — needs FBP follow-up before flash sends"). Don't invent drivers.
4. **Watchlist for next month** — 2-3 line items where the variance is small this month but the *trend* (vs PY or implied by context notes) suggests it could blow up in May. Be specific about what to watch.
5. **Open questions for the FBP huddle at 10am** — 3 bullet points, sharp. Things only a human business partner can answer.

This isn't a number-regurgitation exercise — I need you to connect the variance math to the context notes so the commentary stops being "marketing was up $340K" and starts being "marketing was up $340K because we ran the planned creator test, contribution still landed in plan, no action needed." That's the difference between a flash the CFO reads and a flash that gets sent back for rework.

After the first cut, I want to try:
- Reformatting the variance table as a Slack-friendly summary (no markdown table — bullet form with bold flags) for the FP&A leads channel.
- Adding a "% of total revenue variance" column so I can see which lines are actually moving the P&L vs which just look big in isolation.
- Tightening the headline to fit in the email preview window (~140 chars) for the CFO's morning inbox.

Stretch goals (optional):
- Generate the same pack but at *contribution margin by segment* level instead of consolidated P&L — assume the actuals file gets a "segment" column.
- Draft three follow-up SQL questions I should run against the warehouse before the FBP huddle, based on variances where the context notes don't have a driver.
- Can you make this run automatically every first business day of the month at 7:30am, the moment after GL lock, so the draft is in my inbox before I sit down?
