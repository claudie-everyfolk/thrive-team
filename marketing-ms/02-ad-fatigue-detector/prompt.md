I run paid acquisition on Meta for a mid-sized DTC subscription brand. Prospecting accounts for most of my weekly spend and I'm always managing somewhere between 10 and 15 active creative variants at once. Every Monday I'm supposed to make four decisions: which creatives to scale, which to cut, what new variants to test based on what's actually working, and how to reallocate the budget for the week ahead. In practice I open the Ads Manager tab, the creative library spreadsheet, the prior-tests doc, and a separate trend export — and by the time I've stitched them together it's Wednesday and I've underspent on the winners and overspent on the dying ones.

Today I want to compress that into a single pass. I've got four exports sitting in this folder:

- `meta-spend-week-2026-05-18.csv` — last week's performance per creative variant: spend, impressions, clicks, CTR, CPA, ROAS, days the variant has been live, and a frequency metric.
- `creative-library.json` — metadata for every active variant: hook style, format (UGC / studio / static / motion), audience angle (problem-solution / aspiration / social proof / value), thumbnail description, and the date it went live.
- `prior-tests-learnings.md` — informal notes I keep on what we've already tested and what we learned. Some hypotheses to chase, some to drop.
- `rolling-6week-trends.csv` — top-line performance by week for the last 6 weeks: total spend, blended CPA, blended ROAS, average frequency, and which creative was top spender that week.

Using all four files, build me a **weekly creative & budget reallocation brief**. Structure it like this:

1. **Top of brief — "This week's calls"** — a 4-row decision table: variant ID, current weekly spend, recommended action (SCALE / HOLD / RETIRE / TEST), and a one-line *why* tied to the actual numbers. Lead with the SCALE and RETIRE calls — these are where money moves.
2. **Scale candidates** — for each, show: current CPA vs account average, ROAS, days-live, frequency, the creative attributes from the library (hook + format + angle), and your recommended new weekly budget. Use this scaling logic: CPA at least 15% below account average, ROAS positive trending, frequency under fatigue threshold (call out where you set the threshold and why).
3. **Retire candidates** — for each, show: how performance has decayed (compare to its own week-1 baseline if days-live allows, otherwise to account average), frequency, and *why now* (e.g. "CPA crossed account average 6 days ago, frequency above 4.5, ROAS halved since week 1"). Don't be precious — if a variant is fatigued, kill it.
4. **What to test next** — 3 new variant ideas based on patterns across the *top performers*. Look at the shared attributes of the SCALE candidates (e.g. "two of three scale candidates are UGC + problem-solution + creator-led hook"), cross-reference with the prior-tests doc to skip what we've already tried, and propose 3 specific new variants with the attributes spelled out (hook style, format, angle, why it's a logical next test).
5. **Budget reallocation** — a before/after view of weekly spend by variant, total reallocated $, and an expected blended CPA impact based on the relative CPA of the variants you're shifting *into* vs *out of*. Show your math in one line — not a deck, just the arithmetic.
6. **Watch list for next week** — 2-3 variants that aren't decisions today but I should look at next week, with what specifically I'd look for (e.g. "if frequency hits 3.8 and CPA crosses average, retire").

This is the difference between me running paid like a portfolio manager and running it like a panicked spreadsheet jockey. The hard part isn't reading any single file — it's connecting performance in the spend CSV to the attributes in the library JSON to what we already learned in the prior-tests doc, and then making a budget call that accounts for all three. I need a brief that lets me walk into our Tuesday channel sync with specific moves, not "we should probably test more UGC."

After the first cut, I want to try:
- Asking you to re-run the scale/retire calls with a more conservative fatigue threshold — I want to see what changes when I tighten the rules.
- Adding a "creative type bench strength" rollup: across active variants, how concentrated is my spend on a single format/angle combo? I'm worried about over-indexing on one pattern.
- Generating a 3-bullet Slack post for my channel lead summarizing just the SCALE/RETIRE calls and the dollar shift — no test ideas, no watch list, just the moves.

Stretch goals (optional):
- Draft the testing brief for the highest-priority new variant — hook copy options (3), shot list bullets, and the audience targeting I'd run it against.
- Build a "creative fatigue early warning" rule: based on the rolling 6-week trends, what's the leading indicator that tells me a variant is about to decay *before* CPA crosses average? Codify it as a check I can run mid-week.
- Can you make this run every Monday at 8am pulling from the same filename pattern (just swap the week date)? Tell me what would break if a variant ID exists in the spend CSV but not in the creative library.
