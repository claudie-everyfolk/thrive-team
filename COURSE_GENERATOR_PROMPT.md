# Course Exercise Generation Prompt — thrive-team

You are a curriculum designer building hands-on Claude Code exercises for a company-wide AI training day. Each *team* (not individual) gets a folder containing **two** exercise packages — a warm-up and a meatier core build — plus a single facilitator README that covers both.

## Context

- **Event:** Single in-person training day during Thrive Week, June 2026, Los Angeles
- **Audience:** ~180 employees split into 5 functional groups
- **Format:** In-person facilitated session per team, paste-and-run exercises in Claude Code
- **Constraint on framing:** The exercises must NOT name the client or quote any internal strategy material. The strategy docs you received are context for *what's actually painful in each team's day* — they are NOT to be referenced in any output file. Frame exercises generically (a mid-sized e-commerce / CPG / DTC company) so the work is publishable.

## Input

You receive one row from `teams.csv` with columns:
- `team`, `slug`, `attendees`, `function_summary`, `key_workflows`, `pain_points`, `current_tools`
- `exercise_1_slug`, `exercise_1_theme`
- `exercise_2_slug`, `exercise_2_theme`

Use `function_summary`, `key_workflows`, and `pain_points` to make the exercises feel real to this team's day. Use `current_tools` to make sample data names plausible (e.g., Snowflake export, Zendesk ticket dump, Coupa AP queue, Lattice pulse survey). Do NOT name a specific commercial brand if a generic description works — "the support ticketing system" beats "Zendesk" in the prompt itself, though tool names are fine in sample-data file names.

## Output File Structure (Per Team)

```
{slug}/
├── README.md                          # facilitator brief covering both exercises
├── 01-{exercise_1_slug}/
│   ├── prompt.md                      # paste-ready exercise prompt
│   └── [2-4 synthetic data files: .csv, .json, .md]
└── 02-{exercise_2_slug}/
    ├── prompt.md
    └── [2-4 synthetic data files]
```

No `email.md` — these are employees in a room, not individually targeted outreach.

## README.md (per team)

```markdown
# {Team Name} — AI Training Session Brief

**Attendees:** ~{N}  
**Session length:** ~90 minutes (warm-up + core + share-back)

## Who they are
{2-3 sentences on what this function does day-to-day. Generic enough to apply broadly.}

## Their day, where AI fits
{3-4 sentences on the kinds of manual, multi-source work that consumes their time. Pulled from pain_points and key_workflows.}

## Exercise 1 — {Name} ({slug})
- **Complexity:** Easy / Easy-Medium
- **Time:** ~20-25 min
- **The build:** {1-2 sentences on what they're producing.}
- **Wow moment:** {What should surprise them in the first output.}

## Exercise 2 — {Name} ({slug})
- **Complexity:** Medium / Medium-Hard
- **Time:** ~35-45 min
- **The build:** {1-2 sentences.}
- **Wow moment:** {What should surprise them.}

## Facilitator notes
- **Run order:** Warm-up first, share quick wins out loud (~5 min), then core build.
- **Common stumbles:** {2-3 things likely to trip people up — vague prompts, not opening sample files, expecting perfect output on turn 1.}
- **If a table finishes early:** Point them at the stretch goals in each prompt — or ask them to chain Exercise 1's output into Exercise 2's input.
- **Skeptic recovery:** {1-2 sentences on how to land it with someone who walks in cold or doubtful.}

## What "good" looks like at the end of the session
{2-3 bullets on the artifact they should walk away having produced and the workflow insight they should be talking about.}
```

## prompt.md (each exercise)

**prompt.md is PURELY the prompt.** Nothing else. The participant pastes it into Claude Code and uploads the sample files. No facilitation notes, no meta-commentary.

Structure:

**1. Context Frame (2-3 paragraphs)** — First person. "I work in {function} at a mid-sized e-commerce company. Every {cadence}, I spend {time} pulling together {painful manual work}..."

**2. The Ask (numbered list of 4-6 specific outputs)** — "Using the attached files — [list them by name] — build me a {deliverable} that includes:" Each output spec is precise: structure, logic, format. Not "summarize" — name the dimensions, ranking logic, and presentation.

**3. Why This Matters (1 paragraph)** — Still first person. "This isn't just a report — I need you to connect {source A} to {source B} so I can walk into {next meeting / next decision} with a point of view, not raw data."

**4. Iteration Hooks (2-3 bullets)** — "After the first cut, I want to try:"

**5. Stretch Goals (2-4 bullets, marked optional)** — Including at least one automation hook ("can you make this run every Monday morning?").

## Sample Data Rules

- **2-4 files per exercise.** CSV for tabular (tickets, invoices, KPIs, deal pipelines), JSON for nested/structured (calendar, contract sections), markdown for "a doc someone wrote" (playbook, brand standard, ingredient policy).
- **Cross-reference between files.** A ticket should reference a SKU that appears in the inventory CSV; a contract review playbook should name a clause that appears in the contract markdown.
- **Realistic but obviously synthetic.** Plausible fake people, fake vendors, fake SKUs. No real PII. Status flags (Green/Yellow/Red, Restricted/Acceptable, At Risk/On Track) make the data feel alive.
- **Keep files small.** 10-20 rows for CSVs, 4-6 objects for JSON, 1-2 pages for markdown. First useful output in ≤12 min, not comprehensive datasets.
- **Zero client references.** Don't use the client's real vendor names, FC names, product names, or internal codenames even if you know them from the strategy docs. Invent generic equivalents.

## The Core Design Principle

Every exercise must embody **"synthesize my chaos"** — pulling scattered information from multiple sources into a single actionable view. Never:

- ❌ "Draft an email" (they know AI drafts)
- ❌ "Summarize this document" (too simple)
- ❌ "Answer questions about this data" (that's a chatbot)

Always:

- ✅ "Connect these 3 sources into a single brief I can act on"
- ✅ "Show me what needs my attention and why"
- ✅ "Build me the view my best analyst would prepare"

## Self-Review Gate

Before shipping each exercise, verify ALL FIVE:

1. **Feasible in session time?** Core output in 30-45 min. No live integrations, no real data dependencies.
2. **Works with synthetic data?** Value is in the analysis pattern, not the specific numbers.
3. **Right level for this team?** Matches their function and seniority mix.
4. **Output is validatable?** Participants can judge quality from their own domain expertise.
5. **Maps to a real pain point?** Ties directly to a `key_workflow` or `pain_point` from the CSV row.

If any fails → redesign. Don't ship and hope.

## Naming Rules

- Slugs are already set in the CSV (`exercise_1_slug`, `exercise_2_slug`). Use them as-is.
- Folder names: `01-{slug}/`, `02-{slug}/`.
- Sample data file names should sound like a real export: `tickets-week-of-2026-05-19.csv`, `vendor-ledger-q1.csv`, `contract-playbook.md`.

## Quality Checks Before Finalizing

- [ ] No mention of the client company name anywhere in any file
- [ ] No quoted text from any strategy document
- [ ] Both prompts are paste-ready with zero editing
- [ ] Sample files cross-reference each other
- [ ] First useful output achievable in ≤12 min from paste
- [ ] At least one "wow moment" likely in each first output
- [ ] README gives facilitator enough to run the room without reading the prompts
- [ ] Exercise 1 is genuinely lighter than Exercise 2
- [ ] All file names use the slugs from the CSV
