I'm a transportation analyst. I have a Quarterly Business Review with our seven main parcel carriers in nine days, and right now my "scorecard" is a Google Sheet I rebuild from scratch every quarter by stitching together four sources. By the time I have a clean view I'm out of time to actually *think* about what to negotiate. I want to flip that ratio.

I've pulled the four sources I always end up using:

- `carrier-performance-2026-q2.csv` — per-carrier monthly KPIs: on-time %, exception rate, cost per shipment, claim rate, tracking-event freshness (avg hours between scan events). Three months of data.
- `exceptions-log-2026-q2.csv` — every shipment exception this quarter with carrier, lane, exception type, dwell hours, and resolution status. ~15 rows.
- `rate-card-contract-notes.md` — our negotiated rate cards by carrier and lane, plus the renegotiation triggers and SLA thresholds buried in the contract amendments. Some of this is what we *signed*, not what we're getting.
- `service-incidents-2026-q2.json` — major service incidents (weather diversions, hub fires, scanning system outages) that the carriers reported to us. Useful for not unfairly penalizing carriers for stuff outside their control.

Using all four, build me a **carrier QBR scorecard package** with two sections:

### Section 1 — Carrier Scorecard Table

One row per carrier. Columns: Carrier, On-Time % (Q2 avg), Exception Rate (Q2 avg), Cost per Shipment (Q2 avg), Claim Rate (Q2 avg), Tracking Freshness (hrs), Trend vs Q1 (↑↓→ per metric — pick the most directionally important one). Plus a **Status column** using this logic:

- **Red** if any of: on-time < contracted SLA in `rate-card-contract-notes.md`, claim rate > 1.5%, OR ≥3 unresolved exceptions in the exceptions log.
- **Yellow** if any of: on-time within 2 pts of SLA but above, exception rate trending up >20% vs Q1, OR cost per shipment >5% above contracted rate card.
- **Green** otherwise.

When you assign a flag, **show your work in a one-line "why" cell** — cite the specific number and source ("On-time 94.1% vs 96% SLA per contract §3.2").

**Discount any incident that appears in the service-incidents JSON** when calculating exception trends — make a note at the bottom of which carrier-months you adjusted and by how much.

### Section 2 — "What to Bring Up in the QBR"

Organized by carrier (in scorecard status order — Red first, then Yellow, then Green). For each carrier, 2-4 bullets covering:

1. **The one metric to confront them on** — the most contractually concrete underperformance, with the contract clause / rate cited.
2. **The lane-level pattern** — pull from the exceptions log: is the underperformance concentrated on a specific lane or service level? Don't say "performance dropped" — say "performance dropped on the LAX→DEN lane specifically, 4 of 5 late shipments originated there."
3. **The leverage point** — what we can credibly threaten or ask for. Reference the rate-card doc's renegotiation triggers if any have been hit.
4. **What to NOT bring up** — if a carrier had a legitimate service incident, flag it so I don't waste credibility complaining about something they already disclosed.

For Green carriers, replace the confrontation bullet with "lock in renewal terms — they're performing; what do we want to ask for?"

This isn't a status report. I need to walk into seven meetings with a position per carrier — what I'm pushing on, what I'm willing to trade, and what the data backs me up on. The current scorecard tells me what happened. I need this one to tell me what to *do* about it.

After the first cut, I want to try:
- Recomputing the Status flags if I change the SLA thresholds (we may be renegotiating the on-time threshold from 96% to 95% with one carrier — what changes?).
- Adding a "savings opportunity" column estimating $ at stake per carrier if they hit SLA vs current (you'll have to make a reasonable assumption about shipment volume — call it out).
- Re-ranking the QBR talking points by which ones have the highest $ impact, not by Red/Yellow/Green.

Stretch goals (optional):
- A short executive cover memo (≤150 words) summarizing the quarter for my VP — three sentences on the state of the carrier book, one paragraph on the negotiation themes, one closing line on what I need from her.
- A lane-level heat map (text/markdown is fine — no images) showing exception concentration: rows = carriers, columns = top lanes, cell = exception count.
- A version of the prompt I can re-run quarterly by just swapping the four input files — what assumptions did you bake in that I'd need to revisit?
- Can you turn the "what to bring up" section into individual one-pagers per carrier, so I can hand each meeting its own briefing?
