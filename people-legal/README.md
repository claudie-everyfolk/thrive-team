# People Ops & Legal — AI Training Session Brief

**Attendees:** ~60
**Session length:** ~90 minutes (warm-up + core + share-back)

## Who they are

Combined function spanning the full employee lifecycle plus the legal coverage that wraps around the business. Talent Acquisition (HQ recruiting + FC / Last Mile high-volume hiring), HQ People Ops and HRBPs, FC People Ops, and Legal / Compliance (contracts, regulatory, marketing review, trademark). One room, very different days — but they share the same underlying problem: a lot of high-judgment work bottlenecked by manual screening, drafting, and synthesis before any of the actual judgment can happen.

## Their day, where AI fits

Recruiters and coordinators lose hours to inbound resume review and interview scheduling before they get to do the relationship work that actually wins candidates. HRBPs prep for business reviews by manually combing pulse verbatims, exit themes, and HR ticket trends from three different systems and then have an hour left to form a point of view. In-house counsel triages incoming contracts page by page, holding the company playbook and prior negotiation history in their head while drafting redlines. Marketing and UX content gets reviewed at a fraction of what's produced because compliance review is the slowest seat in the chain. Every one of these is multi-source synthesis work — exactly where Claude Code shifts the cycle time from days to minutes.

## Exercise 1 — Contract Redline Triage (`01-contract-redline-triage`)

- **Complexity:** Easy-Medium
- **Time:** ~20-25 min
- **The build:** Paste a vendor SaaS agreement, the company contract playbook, and a JSON of prior redlines from similar deals. Get back a section-by-section policy flag (`In policy` / `Soft deviation - negotiate` / `Hard deviation - escalate`), suggested redline language for each deviation grounded in actual prior precedent, a plain-English risk summary for the requesting team, and a draft response email to the vendor leading with the top 3 issues.
- **Wow moment:** When the model pulls a specific redline from a 6-month-old precedent deal in the JSON and uses *that* exact language in the email — instead of inventing new language. The point lands: the playbook + the precedent + the contract is exactly the synthesis humans do badly, and the model does it in 90 seconds.

## Exercise 2 — Engagement Pulse Synthesizer (`02-engagement-pulse-synthesizer`)

- **Complexity:** Medium-Hard
- **Time:** ~35-45 min
- **The build:** Three messy sources — pulse-survey free-text verbatims (CSV), exit interview themes (markdown), and HR ticket trends (CSV with MoM deltas) — collapsed into one walk-in-ready brief per department. Each brief surfaces friction themes ranked by *cross-source signal strength* (not raw frequency), a manager-effectiveness read, a retention-risk indicator, and three concrete items to raise with the department head — each with supporting evidence.
- **Wow moment:** When participants see the same theme show up in verbatims, exits, and tickets and the model correctly weights it higher than a louder single-source signal. That's the HRBP move that takes years to develop, performed instantly on data the participants brought.

## Facilitator notes

**Run order — and the big-room split.** This is the biggest group of the day. Don't try to march all 60 people through both exercises in lockstep — it'll bog down. Instead:

- **Seat by function before the session starts.** Legal and senior People Ops (Sr. HRBPs, Talent leads, People Ops leadership) at one cluster of tables. HRBPs, recruiters, and FC People Ops at another cluster.
- **First 25 min — split focus.** Legal / senior People Ops tables go straight into Exercise 1 (the contract triage). HRBP / recruiter tables go straight into Exercise 2 (the pulse synthesizer). Each group starts on the exercise that lands hardest in their day-to-day.
- **5 min share-back at the 25-min mark.** Two volunteers (one from each side of the room) share their best output. This is the moment that crosses the room.
- **Next 35-40 min — swap.** Each cluster now tackles the *other* exercise. Faster the second time because they've seen the pattern.
- **Final 15 min — full-room share-back.** Three or four examples of "what surprised me." Make sure at least one Legal voice and one HRBP voice speaks.

**Common stumbles.**
- Exercise 1 — pasting just the contract and not the playbook + JSON. Without all three sources the model invents a generic review, not a precedent-grounded one. The whole point evaporates. Walk the room early to catch this.
- Exercise 2 — asking for "one big summary" instead of one brief per department. The cross-department aggregation is the easy answer and the wrong one. The value is the per-department texture.
- Either exercise — accepting the first cut. The iteration hooks in the prompts are where the real "oh" happens. Push tables to run at least one follow-up.

**If a table finishes early.** Stretch goals in each prompt are real, not filler. The "make it run every Monday morning" stretch on Exercise 2 is the gateway drug to scheduled-job thinking — start there. For Exercise 1, the "fast-track vs full-review flavors" stretch teaches output customization, which transfers to almost every other contract type.

**Skeptic recovery.** Two angles depending on who walks in cold. For a Legal skeptic ("the model will get the redline wrong and we'll send a bad email") — agree, then point out the model isn't sending anything; it's producing a draft *with cited precedent* that they review in 5 minutes instead of drafting from scratch in 45. The judgment stays with them; the typing doesn't. For an HRBP skeptic ("this is just summarization") — pull up the output and walk them through one ranked theme. The model didn't summarize — it cross-referenced three sources and weighted by signal redundancy. That's the analyst move, not the summarizer move.

## What "good" looks like at the end of the session

- Every Legal participant leaves with a contract triage workflow they could plausibly use on the next inbound vendor MSA — including draft redline language pulled from their own precedent.
- Every HRBP / People Ops participant leaves with one finished per-department brief and an answer to the question "what could I prep for in 5 minutes instead of 50 next quarter?"
- The room is talking about a shared insight: their highest-judgment work is mostly bottlenecked by lower-judgment lookup and synthesis, and that's exactly the part the model handles best.
