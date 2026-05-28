I'm an AP specialist at a mid-sized DTC subscription company. Every morning I open the AP system and stare at a queue of merchandise invoices that didn't 3-way match. Most are small variances that could auto-clear if I had the time. Some are real — a vendor billed us for 2,400 units of a SKU when the FC only received 2,180. Today I have about fifteen of them, and the way I work it now is one row at a time: click into the invoice, find the PO, pull the receipt, eyeball the variance, decide if it's within tolerance, decide who to escalate to. It takes me most of the morning before I've sent a single vendor email. I want to triage the whole batch at once and walk into my 11am with the top 3 vendor emails already drafted.

I have four files:
- `invoices-batch-2026-05-27.csv` — fifteen merchandise invoices currently sitting in the variance queue. Each row has invoice #, vendor, PO #, SKU, quantity billed, unit price billed, freight, total.
- `po-data-2026-05-27.csv` — the corresponding PO lines: PO #, vendor, SKU, quantity ordered, unit price agreed, freight terms.
- `receipts-2026-05-27.csv` — what the FCs actually received against each PO: PO #, SKU, quantity received, FC, receipt date, condition notes.
- `tolerance-rules.md` — our policy doc on what counts as "within tolerance" (auto-approve), and the routing rules for each variance type.

Using all four files, build me a **bill variance triage pack** with:

1. **Summary line** — out of the X invoices in the queue, how many auto-approve, how many need vendor outreach, how many need FC investigation, how many need category manager review. Total dollar value of each bucket.
2. **Full triage table** — every invoice in the batch, with columns: Invoice #, Vendor, PO #, SKU, Billed Qty, Received Qty, Billed Unit Price, PO Unit Price, $ Variance, % Variance, **Variance Type** (one of: price discrepancy / quantity short / quantity over / missing receipt / vendor billing error / freight not on PO / within tolerance), **Resolution Path** (one of: auto-approve / vendor credit request / FC investigation / category manager review). Sort by absolute dollar variance, largest first. Apply the tolerance rules from the markdown file — do NOT make up tolerances.
3. **Top 3 vendor outreach drafts** — for the 3 highest-dollar variances that need vendor outreach (NOT FC investigation, NOT category manager review — actual vendor-facing emails), draft a short professional email I can paste into the vendor email system. Each draft should include: subject line with invoice # and PO #, plain-English description of the discrepancy, what we received vs what was billed, the specific dollar amount in question, and a clear ask (credit memo / corrected invoice / explanation). Sign-off: "AP Team — [Company]". Tone: firm but not adversarial; these are vendors we want to keep.
4. **Escalation list** — for any invoice routed to FC investigation or category manager review, give me a one-line note I can drop into the AP system as a comment, naming the FC or vendor manager who needs to look at it and the specific question they need to answer.
5. **Pattern flag** — if you see the same vendor or the same SKU showing up across multiple variances, call it out as a "look at this vendor/SKU holistically" note at the bottom. One paragraph max.

This isn't a clerical exercise — the value is in connecting the PO data to the receipt data to the invoice so I'm not playing detective on each line. I want to walk into my 11am with the auto-approves already cleared mentally, the three outreach emails ready to send, and a clean escalation list. Right now I'm lucky to get through six invoices before lunch.

After the first cut, I want to try:
- Re-running with stricter tolerances (say, 0.5% on price instead of 2%) to see what would have flagged earlier in the month if we'd tightened the rule.
- Adding a column for "days since invoice received" — anything aging past 7 days should bubble up regardless of dollar size, because we're chasing the 30-day pay cycle.
- Bundling the vendor outreach by vendor — if Vendor B has three variances, draft one consolidated email instead of three separate ones.

Stretch goals (optional):
- Generate the vendor credit request memo in a format I can attach to the email (PDF-style, with invoice #, PO #, variance amount, and a credit request line item).
- Build a quick dashboard view (markdown table) showing which vendors have had the most variances this month so I can flag the worst-offenders for the category manager's next QBR.
- Can you make this run automatically every morning at 7am against whatever's in the variance queue overnight, so I walk into a triaged pack instead of a raw queue?
