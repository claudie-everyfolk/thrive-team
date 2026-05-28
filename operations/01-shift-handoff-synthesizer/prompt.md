I'm a shift lead at one of our fulfillment centers (FC "BV"). I just finished the day shift and I'm handing off to the night lead in about 15 minutes. Right now my handoff process is: open six tabs, copy-paste numbers into a Slack DM, forget two things, get pinged about them at 11pm. Today I want to do it properly.

I've got three messy sources I always end up pulling from:
- `shift-metrics-bv-2026-05-26.csv` — pack and pick UPH by line, vs the shift goal, and rolling 7-day average. Includes a "behind_schedule" flag.
- `open-items-bv-2026-05-26.json` — open safety incidents, pending audits, and associate feedback items from the floor (some opened today, some carried over).
- `news-of-the-day-bv-2026-05-26.md` — a short doc I jotted during the shift with context the next lead won't know unless I tell them (vendor changes, equipment quirks, VIP orders, weather).

Using all three files, build me a single **shift handoff brief** for the incoming night lead. It needs to be skimmable in 60 seconds and detailed enough that they don't have to ping me. Structure it like this:

1. **Top of brief — "If you read nothing else"** — the 3 highest-priority items across all sources, ranked. Use this priority logic, in order: (a) any open safety incident not yet closed, (b) any line >15% below goal that's still running into the next shift, (c) any pending audit with a due time inside the next 8 hours, (d) any VIP / escalation context from the news doc. Pull at most 3 items total — be ruthless.
2. **Production status** — a tight table: line, function (pack/pick), shift UPH, goal, % to goal, 7-day avg, status flag (Green / Yellow / Red using ≥100% / 85-99% / <85% to goal). Sort worst-to-best by % to goal.
3. **Open items requiring action this shift** — grouped under three headers: Safety, Audits, Associate Feedback. For each item show: ID, what it is in one line, who owns it, and when it's due. Carry-over items (not opened today) get a "(carried)" tag.
4. **Heads-up context** — a short bulleted version of the news-of-the-day doc, but only the items that affect the next 12 hours. Skip anything purely historical.
5. **One question the night lead should be ready to answer at standup tomorrow** — your pick, based on patterns across the three files. Just one. Make it sharp.

This isn't busywork — if I miss a pending audit or a behind-schedule line, that becomes someone else's 6am fire. I need you to connect what's in the metrics CSV (what's broken right now) to what's in the open-items JSON (who's already on it) so the incoming lead walks in with a plan, not a triage list.

After the first cut, I want to try:
- Reformatting the whole brief as a Slack message (no tables — use bullets and bold headers, because Slack tables look like garbage).
- Adding a "trend vs yesterday" column to the production table — I'll paste yesterday's CSV next.
- Tightening the "If you read nothing else" section to fit in a single Slack notification preview (~180 chars).

Stretch goals (optional):
- Generate a 1-line text message I can send to the FC manager summarizing the shift in plain English.
- Build a version of this prompt that I can re-run every day by just swapping the date in the filenames — what would I have to change?
- Can you make this run automatically at 14:45 every weekday so the brief is ready by handoff at 15:00?
