I lead Member Engagement for a mid-sized DTC subscription brand. Every Monday morning I'm supposed to walk into the cross-functional standup with a clear answer to one question: "what are members actually telling us this week, and what should we do about it?" In practice I spend the first 90 minutes of Monday scrolling through tickets, jumping over to social, then opening last week's NPS verbatims in another tab, trying to hold it all in my head. By the time I sit down, the standup is half over and I'm presenting raw quotes instead of a point of view.

Today I want to fix that. I've got three exports from last week sitting in one folder:

- `tickets-week-of-2026-05-18.csv` — every support ticket opened in the last 7 days, with category, sentiment (positive/neutral/negative), whether it escalated to a human agent, resolution time, and a short verbatim snippet from the member.
- `social-mentions-week-of-2026-05-18.csv` — public @-mentions and tagged posts pulled from our social listening tool. Platform, reach, sentiment, the post text, and whether our community team replied.
- `survey-verbatims-week-of-2026-05-18.md` — free-text answers from last week's post-delivery NPS survey, grouped by score band (Promoters 9-10, Passives 7-8, Detractors 0-6).

Using all three files, build me a **Member Voice brief for Monday standup** that I can paste into a doc and walk into the room with. Structure it like this:

1. **Top of brief — "What members are telling us this week"** — the 3 highest-signal themes across all three sources, ranked. Use this signal-strength logic, in order of weight: (a) volume across sources (a theme that shows up in tickets AND social AND survey beats a single-channel spike), (b) negative sentiment skew, (c) escalation rate on related tickets, (d) recency (a theme that built through the week beats one that spiked Monday and died). Each theme gets one sharp sentence naming what's going on.
2. **Theme deep-dive** — for each of the 3 themes, a short block with: signal strength score (High / Medium-High / Medium), volume by source (e.g. "11 tickets / 4 social posts / 6 survey mentions"), sentiment skew, one representative quote from EACH source that backs it (tickets, social, survey — labeled), and a "so what" line: what this means for the business.
3. **Emerging watch list** — 2-3 themes that don't have full signal yet but are worth tracking next week. One line each, with why they're on the watch list (e.g. "small volume but every mention is a Detractor").
4. **What I'd recommend bringing up at standup** — 2 concrete asks for other teams (e.g. "ask Ops about Tuesday's shipping delay cluster" or "loop Brand in on the new packaging complaints"). These should be specific to a team, not generic.
5. **What I'd ignore this week** — 1-2 themes that look loud but are actually noise (one-off rant going viral, a single power user with 8 tickets, etc.). Name them and say why.

This isn't a report — it's the difference between me showing up Monday with "members are upset" and me showing up with "shipping reliability is the top issue this week, here's the evidence across channels, and here's who needs to hear it." I need you to actually connect the ticket data to the social posts to the survey verbatims — the same complaint shows up in different language in each channel, and the job is to recognize it's the same complaint.

After the first cut, I want to try:
- Asking you to re-rank the themes using a different weighting (e.g. weight social reach higher because exec leadership tracks that channel).
- Adding a sentiment trend line — did this theme get louder or quieter as the week went on? I'll paste day-of-week breakdowns.
- Generating a Slack-formatted version of just the top-of-brief section, no tables, that I can drop in the #member-pulse channel before standup.

Stretch goals (optional):
- Draft a 3-sentence opener I can use to kick off standup verbally — not the whole brief, just the headline.
- Generate a private 2-line note to our VP of Brand about the one theme that touches their work, written like a peer-to-peer DM not a formal report.
- Can you make this run every Monday at 7am so the brief is in my inbox before I sit down? Tell me what I'd need to swap in (file paths, the date in the filenames, anything else).
