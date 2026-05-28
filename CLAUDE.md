# thrive-team

Hands-on Claude Code exercises for a company-wide AI training day during Thrive Week, June 2026 (Los Angeles, in-person). ~180 employees across 5 functional groups, 2 exercises per group.

## Repo layout

```
thrive-team/
├── README.md                       # participant-facing intro (per-team section)
├── CLAUDE.md                       # this file — for re-running or extending
├── COURSE_GENERATOR_PROMPT.md      # the system prompt that produced every exercise
├── teams.csv                       # one row per team — the source of truth
├── ralph-wiggum-loop.sh            # batch-generation loop (overkill for 5 teams, kept for reuse)
├── operations/
│   ├── README.md                   # facilitator brief for both exercises
│   ├── 01-{warm-up-slug}/
│   │   ├── prompt.md
│   │   └── *.csv / *.json / *.md   # synthetic sample data
│   └── 02-{core-build-slug}/
│       ├── prompt.md
│       └── *.csv / *.json / *.md
├── marketing-ms/
├── merchandising/
├── finance/
└── people-legal/
```

## Design rules

**Generic framing.** No exercise mentions the client by name, quotes from strategy docs, or names real internal systems/vendors/SKUs. The exercises read as "for a mid-sized e-commerce / CPG / DTC company." This is deliberate — the repo is public.

**"Synthesize my chaos."** Every exercise pulls 2-4 scattered sources (CSV + JSON + markdown) into a single actionable view. Not "draft an email," not "summarize a doc."

**Two exercises per team.**
- `01-` = warm-up, ~20-25 min, Easy / Easy-Medium
- `02-` = core build, ~35-45 min, Medium / Medium-Hard

**Paste-ready.** `prompt.md` is purely the prompt — no facilitation notes, no meta. Participants paste into Claude Code, upload sample files, run.

## Regenerating or adding a team

1. Edit `teams.csv` (add a row or change theme slugs).
2. Re-run the generator against just that team:

```bash
cd /Users/claudie/work/thrive-team
claude --print --dangerously-skip-permissions --max-turns 20 \
  "Read COURSE_GENERATOR_PROMPT.md and teams.csv. Generate the package for team '{slug}'. Spawn one subagent per exercise (2 in parallel)."
```

Or for a full re-run / large batch, use the loop:

```bash
BATCH_SIZE=5 MAX_TURNS=20 \
EVENT_CONTEXT="Thrive Week AI training, June 2026, LA" \
CSV_FILE=teams.csv \
GENERATION_PROMPT=COURSE_GENERATOR_PROMPT.md \
./ralph-wiggum-loop.sh
```

Progress lives in `.batch-progress`, logs in `batch-loop.log`.

## Updating an existing exercise

`prompt.md` and sample data live in the same folder. Edit in place, commit. The README for that team should be re-checked if you change the exercise theme materially.

## Quality gates (every shipped exercise passes ALL FIVE)

1. Feasible in 30-45 min with no live integrations
2. Works on the synthetic data alone — value is in the pattern, not the numbers
3. Right level for the function and seniority mix
4. Output is validatable from participants' domain expertise
5. Maps to a real pain point named in `teams.csv`
