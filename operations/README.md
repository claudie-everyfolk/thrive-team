# Operations & Fulfillment — AI Training Session Brief

**Attendees:** ~20
**Session length:** ~90 minutes (warm-up + core + share-back)

## Who they are

Demand planners, supply planners, procurement leads, FC operations managers, transportation analysts, and ops integration folks. They run a multi-fulfillment-center physical operation — flow of goods from vendor to dock to bin to box to doorstep. Their day is dense with numbers from systems that don't talk to each other.

## Their day, where AI fits

A typical day involves stitching together exports from the warehouse management system, the carrier portal, the procurement queue, vendor scorecards, and a half-dozen Snowflake queries — usually into a single spreadsheet that gets emailed, then immediately becomes stale. Shift handoffs are reconstructed from six tabs. Carrier scorecards are quarterly archeology projects. SKU outlier reviews are done by eye because nobody has time to write a query for the tail. These are exactly the workflows where "synthesize my chaos" pays off — the bottleneck isn't decision-making, it's getting to a clean enough view to decide on.

## Exercise 1 — Shift Handoff Synthesizer (`01-shift-handoff-synthesizer`)
- **Complexity:** Easy-Medium
- **Time:** ~20-25 min
- **The build:** A paste-ready prompt that fuses a shift-metrics CSV, an open-items JSON (safety / audits / feedback), and a markdown "news of the day" doc into a single ranked handoff brief for the incoming shift lead.
- **Wow moment:** The "If you read nothing else" section. Watching Claude correctly rank a safety incident above a 31%-below-goal line above a pending 8-hr audit — using priority logic *they specified* — is the moment people stop seeing this as autocomplete.

## Exercise 2 — Carrier Scorecard Builder (`02-carrier-scorecard-builder`)
- **Complexity:** Medium-Hard
- **Time:** ~35-45 min
- **The build:** A QBR-ready scorecard for ~7 carriers across on-time %, exception rate, cost, claim rate, and tracking freshness — flagged Red/Yellow/Green using contract SLAs from a rate-card markdown doc — plus a per-carrier "what to bring up in the QBR" section with negotiation talking points tied to specific contract clauses.
- **Wow moment:** Claude correctly *discounts* the carriers that had legitimate disclosed service incidents (from the JSON) when grading their exception trend — and cites the contract clause that justifies the renegotiation ask. That's a thing only their best analyst would do, surfaced in one prompt.

## Facilitator notes

- **Run order:** Warm-up first. After ~20 min, ask 2-3 people to read their handoff brief output aloud — focus on the "If you read nothing else" section since it's where prioritization quality is most visible. Then transition to the core build.
- **Common stumbles:**
  - People paste the prompt but forget to upload all three / four sample files. Output will be vague — first remedy is "did you attach all the files?"
  - On Exercise 2: some will skip the contract markdown because it "looks like documentation." That doc is what makes the scorecard sharper than the data alone — call this out before they start.
  - First-output perfectionism. Encourage one iteration round before they declare it broken. The iteration hooks in the prompts are there on purpose.
- **If a table finishes early:** Stretch goals are listed in each prompt. The highest-value one is chaining: take Exercise 1's handoff brief output and feed it into a "what does my morning standup deck look like" prompt. Or in Exercise 2, ask them to generate the per-carrier one-pagers.
- **Skeptic recovery:** If someone walks in saying "I already have a dashboard for this" — agree with them. The pitch isn't replacing the dashboard. It's that the *interpretation layer* on top of the dashboard (what to do about it, what to bring up in the meeting, what the incoming shift needs to know first) is the part that still eats their afternoon. Show them how the prompt cites the contract clause in Exercise 2 — that's analyst work, not dashboard work.

## What "good" looks like at the end of the session

- Every participant walks out with two working prompt templates saved somewhere they'll find them again (encourage saving to a shared team folder during the share-back).
- At least one person on the transportation side has identified a real carrier in their book they want to re-grade using this approach next week.
- The room is talking about *which of their current workflows* fits the "synthesize my chaos" pattern — not whether AI can do their job, but which 30-minute task they're going to compress to 5 by next Friday.
