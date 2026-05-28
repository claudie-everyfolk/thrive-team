# thrive-team

Hands-on Claude Code exercises for a company-wide AI training day. ~180 employees across five functional groups, two exercises per group, all built around the same core idea:

> **Synthesize my chaos.** Pull 2-4 scattered sources into a single view I can actually act on.

## The five groups

| Group | Folder | Warm-up | Core build |
|---|---|---|---|
| Operations & Fulfillment | [`operations/`](operations/) | Shift handoff synthesizer | Carrier scorecard builder |
| Marketing & Member Services | [`marketing-ms/`](marketing-ms/) | Member voice synthesizer | Ad fatigue detector |
| Merchandising | [`merchandising/`](merchandising/) | Ingredient compliance reviewer | Vendor JBP prep pack |
| Finance & Accounting | [`finance/`](finance/) | Variance commentary drafter | AP bill-variance triage |
| People Ops & Legal | [`people-legal/`](people-legal/) | Contract redline triage | Engagement pulse synthesizer |

Each folder has:
- `README.md` — facilitator brief covering both exercises
- `01-{slug}/prompt.md` + sample data — warm-up (~20-25 min)
- `02-{slug}/prompt.md` + sample data — core build (~35-45 min)

## How to run one in the room

1. Open `prompt.md` for the exercise.
2. Paste the entire prompt into Claude Code.
3. Upload the sample data files from the same folder.
4. Run. Iterate using the hooks at the bottom of the prompt.

## About the synthetic data

Every file in this repo is synthetic. Names, vendors, SKUs, metrics, ticket bodies — all invented. The data feels real because the *shape* of the workflow is real; the numbers are not.

---

For extending or regenerating, see [`CLAUDE.md`](CLAUDE.md).
