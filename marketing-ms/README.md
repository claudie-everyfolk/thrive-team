# Marketing & Member Services — AI Training Session Brief

**Attendees:** ~40
**Session length:** ~90 minutes (warm-up + core + share-back)

## Who they are

A combined function spanning brand and creative, member engagement (CRM, lifecycle, analytics), member growth (paid acquisition, BD/influencer, paid creative), and the member services floor (chat/voice agents, QA, WFM). It's the entire arc from "someone sees the brand" through "someone calls in with an issue at 9pm on a Saturday" — under one roof for the day.

## Their day, where AI fits

Creative variant testing is capped by manual review bandwidth. Ad fatigue gets caught only after performance has already decayed. Community management eats 40+ hours a week across the team. Voice-of-Member insight extraction means combing through tickets by hand. QA can only sample a tiny slice of agent conversations. Every one of these is a "multiple scattered sources, one decision needed" problem — exactly what Claude is for.

## Exercise 1 — Member Voice Synthesizer (`01-member-voice-synthesizer/`)
- **Complexity:** Easy-Medium
- **Time:** ~20-25 min
- **The build:** Synthesize a week of support tickets, public social mentions, and survey verbatims into a "what members are telling us this week" brief — themes ranked by signal strength (volume across sources + sentiment + escalation + recency), each backed by representative quotes from each channel.
- **Wow moment:** Members complain about the same things in three different vocabularies — "shipping" in tickets, "out for delivery lol" on social, "tracking lies" in survey. The first output collapses all three into one named theme with evidence, and surfaces the one viral influencer rant as noise to ignore. That recognition pattern is what they'd have spent 90 minutes doing by hand.

## Exercise 2 — Ad Fatigue Detector (`02-ad-fatigue-detector/`)
- **Complexity:** Medium-Hard
- **Time:** ~35-45 min
- **The build:** Read weekly Meta performance across 12 creative variants, flag scale / hold / retire / test calls with reasoning tied to numbers, cross-reference top performers' attributes against the prior-tests doc to propose 3 new variants, and produce a budget reallocation with expected CPA impact.
- **Wow moment:** The model spots that all three scale candidates share the same hook + format + angle (creator-led question + UGC + problem-solution), then proposes test variants that vary *creator vertical* while holding the winning attributes constant — exactly the open hypothesis sitting in the prior-tests doc. That's not a summary; that's reasoning across files.

## Facilitator notes

- **Mixed seating.** This is the only combined group of the day — Member Services floor agents next to paid acquisition managers next to brand creatives. Seat them at mixed tables on purpose. The MS person at table 3 knows the actual member complaints; the paid acq person knows what hooks are running; pairing them is where the real insight comes from. Don't let them cluster by sub-team.
- **Run order:** Warm-up first (Member Voice), share quick wins out loud (~5 min — ask 2 tables to read their top theme), then core build (Ad Fatigue Detector).
- **Common stumbles:**
  - Pasting the prompt without uploading the sample files. The output will be hallucinated. Tell them upfront: paste, attach, then run.
  - Accepting the first output as final. Both exercises have iteration hooks built in — push them to use at least one.
  - Treating Exercise 2 as a spreadsheet exercise. The whole point is connecting the JSON metadata to the spend CSV to the prior-tests doc. If someone says "I just used the spend CSV," redirect them.
- **If a table finishes early:** Point them at the stretch goals — especially the "make this run automatically every Monday" hook in both prompts. Or chain Exercise 1's output into Exercise 2: a top theme from Member Voice (e.g. "packaging complaints") becomes the brief for a new creative variant in Ad Fatigue.
- **Skeptic recovery:** For the brand/creative skeptic who walks in saying "AI can't write a hook" — they're right, but that's not the exercise. The exercise is the *analyst layer* — the work that decides which hooks should exist in the first place. For the MS floor agent who says "I don't read paid acquisition data" — Exercise 1 is theirs; the brief they produce is what their VP of Engagement actually walks into Monday standup with.

## What "good" looks like at the end of the session

- Every table walks out with two artifacts: a Member Voice brief and a creative reallocation brief, each in a format that could be shared with leadership Monday morning with minimal editing.
- They can articulate the pattern that links both exercises: scattered multi-source data → one ranked, evidenced, opinionated view. That's the workflow shape they should be looking for everywhere in their own week.
- At least one table proposes a real next step from their own job — "I'm going to run this on my actual ticket queue Monday" or "I'm rebuilding our weekly creative review around this format" — and says it out loud in share-back.
