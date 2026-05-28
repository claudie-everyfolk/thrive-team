I'm in-house counsel at a mid-sized e-commerce company. My intake queue is full of vendor SaaS agreements — every team wants to buy something, and every vendor sends their own paper. The bottleneck is me reading 10-12 pages of legalese, comparing it to our playbook in another tab, and remembering what we got the last vendor in this category to concede. By the time I send the redline, the requesting team has been waiting two weeks and is annoyed.

A request just landed in my queue: a marketing analytics SaaS, 220 seats, ~$100K ACV, vendor sent their standard MSA. The requesting team wants to sign by end of next week. I want to do the full first-pass triage in the next 20 minutes so I can either hand it straight to negotiation or escalate to my VP with the specific issues already flagged.

I've got three files attached:
- `vendor-msa-northbeam-analytics-v1.md` — the vendor's standard paper. 10 numbered sections.
- `contract-playbook-v4.md` — our internal playbook. Tells you what's in-policy, what's a soft deviation (negotiate), and what's a hard deviation (escalate to VP Legal) per clause type.
- `prior-redlines-similar-deals.json` — recent redlines on three similar SaaS deals. Useful for tone and specific language we've actually gotten vendors to accept.

Using all three files, build me a **contract triage brief**. Structure it like this:

1. **Section-by-section flag table.** One row per vendor contract section (1-10). Columns: Section #, Section name, Status (`In policy` / `Soft deviation - negotiate` / `Hard deviation - escalate`), one-line summary of the issue. Where a section has multiple issues at different severities, take the most severe and note the others briefly in the same cell.

2. **Suggested redline language for every deviation.** For each soft or hard deviation, give me: (a) the exact vendor language that's a problem, (b) the proposed replacement language we'd send back, (c) a one-line rationale tied to the playbook section. Where the prior-redlines JSON has language we've already gotten a similar vendor to accept, use that as the starting point and cite the deal ID.

3. **Risk summary (one paragraph, ~4-6 sentences).** Plain English. Written for the requesting business team — not for legal. The point: what are the top 2-3 things they should know about this contract before signing, in language they'll actually read. No legalese.

4. **Draft response email to the vendor.** Subject line + body. Professional, not adversarial. Lead with the top 3 redlines (rank by severity, not order of appearance in the contract). For each: name the section, state our position, propose specific language. Close by asking for a turnaround date.

5. **Escalation flag.** One line at the top: `ESCALATE TO VP LEGAL: YES / NO`. Yes if any hard deviation exists. If yes, give me a 2-bullet "what the VP needs to know before approving the email" that I can paste into a Slack DM.

This isn't a summary exercise. The whole point is that the playbook, the contract, and our prior precedent are three separate sources right now — and the time-waste is me holding all three in my head while drafting. I need you to do that synthesis so I can spend my brain on the judgment calls, not the lookup.

After the first cut, I want to try:
- Rerunning with a tighter risk summary — three sentences, executive-friendly, no clause numbers.
- Generating the same outputs in two flavors: one for a "fast-track" deal (just the email + escalation flag) and one for a "full review" deal (everything).
- Adding a "ballpark fallback positions" column to the redline table — what I'd accept if the vendor pushes back hard on each one.

Stretch goals (optional):
- Generate a 1-paragraph internal Slack message I can send to the requesting team to set expectations on the negotiation timeline based on what's in this contract.
- Build a reusable version of this prompt I can re-run on any new vendor contract by swapping the contract filename — what would the prompt template look like?
- If we close this deal, summarize the negotiated outcomes in a JSON record I can append to `prior-redlines-similar-deals.json` so the next reviewer has the precedent.
