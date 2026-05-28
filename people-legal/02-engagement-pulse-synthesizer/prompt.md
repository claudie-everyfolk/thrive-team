I'm an HRBP at a mid-sized e-commerce company. Every quarter I sit down with each department head for a business review. The expectation is that I walk in with a clear point of view on what's actually going on with their people — not the headline engagement score (everyone has that already), but the texture underneath: what's bubbling up, what's getting worse, who's flight-risk, what they should actually do.

The problem is the data lives in three completely different places and three completely different shapes. Pulse survey verbatims are a CSV of free-text comments tagged by department and sentiment. Exit interview themes live in a quarterly markdown summary. HR ticket trends are a structured CSV with month-over-month deltas by category. By the time I've read all three and held them in my head, I have an hour left to actually write the brief. So I usually don't — I write a thin version and rely on my own pattern recognition in the meeting.

I want to fix that. I've got three files attached:
- `pulse-survey-verbatims-q2-2026.csv` — 35 free-text comments across three departments (Customer Operations, Engineering, Merchandising) with role level, tenure, and sentiment tags.
- `exit-interview-themes-q1-2026.md` — last quarter's exit themes, organized by department, with ranked themes and notable destinations.
- `hr-ticket-trends-q2-2026.csv` — ticket categories by department with current month volume, prior month, MoM trend %, and a note column.

Using all three files, build me **one brief per department** (Customer Operations, Engineering, Merchandising) — three briefs total, each one self-contained and walk-in-ready. Each brief follows this structure:

1. **Headline (2 sentences max).** What's the one-line story for this department this quarter? Plus a "vs last quarter" directional read (worsening / stable / improving), grounded in the ticket trends and exit themes.

2. **Top friction themes, ranked by signal strength (3-5 themes).** For each theme: a short name, the strength rating (Strong / Moderate / Emerging), and 2-3 supporting data points pulled across the three sources. Crucially: the ranking is by *signal across sources*, not by frequency in any single source. A theme that shows up in verbatims AND exit interviews AND ticket trends is Strong even if it's only the 3rd most frequent in any one of them. A theme that shows up loudly in only one source is Emerging at best.

3. **Manager-effectiveness read (2-3 bullets).** What do the three sources collectively say about how managers in this department are doing? Look across verbatims that mention managers (positive and negative), ticket categories tied to manager / coaching, and exit themes about manager bandwidth. Don't average to "fine" — name the pattern.

4. **Retention risk indicators (one short paragraph).** Synthesize: who's most at risk of leaving in this department, based on (a) sentiment patterns by tenure band in the verbatims, (b) cited destinations in exits, (c) ticket categories that historically precede attrition (compensation, career, workload). Be specific — "newer ICs in this role band" beats "some people."

5. **What I'd bring up with the department head — 3 concrete items.** Each item is: (a) one sentence stating what you'd raise, (b) the supporting quote or data point from the sources, (c) the specific ask of the department head. Not "improve engagement" — something they could actually act on in the next 30 days. Rank by urgency.

This isn't a report — it's a meeting prep document. I need to walk in able to say "here's what's going on, here's the evidence, here's what I think we should do." The synthesis is the whole point: a department head will dismiss "11 of 14 exits cited workload" if I lead with it, but they'll engage if I say "the workload story shows up in three different signals — let me show you what I'm seeing." Connect the sources for me so I can connect the conversation.

After the first cut, I want to try:
- Adding a "what would change my read" section per brief — what data would tell me I'm wrong about the headline?
- Generating a fourth, cross-department brief: what themes are showing up in multiple departments vs. department-specific? Useful for my conversation with the CHRO.
- Tightening each brief to a single-page version I could screenshot and send before the meeting.

Stretch goals (optional):
- Build a manager-effectiveness scorecard with three dimensions (coaching presence, workload defense, career conversations) and rate each department Strong / Mixed / Weak with evidence.
- Generate three different versions of the same brief — one for an analytical department head who wants the numbers, one for a relational one who wants the human story, one for a skeptical one who'll push back on the methodology. Same underlying analysis, different framing.
- Can you make this re-run automatically the first Monday of every month when the new pulse + ticket data lands? What would the prompt template look like, and what would I need to change in the filenames each time?
