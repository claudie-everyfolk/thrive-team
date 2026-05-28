# Merchandising — AI Training Session Brief

**Attendees:** ~40
**Session length:** ~90 minutes (warm-up + core + share-back)

## Who they are

Merchandising spans Category Management, Owned Brand, Merch Marketing, FSQA, and Retail Operations. Day-to-day they own product selection, vendor relationships, pricing, ingredient compliance, promotional placement, and the catalog itself. They are the team that decides what shows up on the digital shelf and what it costs.

## Their day, where AI fits

The pain is rarely in the decisions — it's in the assembly work that has to happen before the decision. Vetting a new product's ingredient list against a long standards doc takes 45 minutes to several hours. Pulling a vendor's 12-month performance for a JBP means stitching together a BI export, an in-stock report, and the quality complaint log by hand. Monitoring pricing across thousands of SKUs in many regions exceeds what the pricing team can manually cover. Selection-gap analysis is fully manual. Quality complaints land in email, spreadsheets, and ad-hoc vendor threads. Most of these workflows are "synthesize my chaos" problems — multiple sources, one decision — which is exactly the shape AI handles well.

The two exercises chosen here are CM-flavored, but Exercise 1 will feel familiar to FSQA (same ingredient-vetting loop) and Exercise 2 will feel familiar to Owned Brand Managers (same vendor performance review pattern, different stakeholder).

## Exercise 1 — Ingredient Compliance Reviewer (`01-ingredient-compliance-reviewer`)

- **Complexity:** Easy-Medium
- **Time:** ~20-25 min
- **The build:** Cross-reference a vendor's new product submission against the FSQA standards doc and the restricted-ingredients master list. Produce a per-ingredient verdict table, an overall approve/needs-FSQA/reject call, and a vendor email batching every documentation request.
- **Wow moment:** The first output catches *both* the brown rice syrup arsenic-test requirement *and* the caramel color Class I spec *and* the gluten-free claim with no third-party test — three different rule types found and reasoned about in one pass. Manually this would be a 45-minute cross-reference. The vendor email is sendable as-is.

## Exercise 2 — Vendor JBP Prep Pack (`02-vendor-jbp-prep-pack`)

- **Complexity:** Medium-Hard
- **Time:** ~35-45 min
- **The build:** Compile 12 months of sales, in-stock vs target, quality complaints, and SLA history for one vendor into a single one-page negotiation prep pack with explicit "winning / failing / asks / don't bring up" sections.
- **Wow moment:** The model connects the dots no human had drawn yet — the new SKU (NP-1031) is the growth headline AND the supply disaster AND the open allergen labeling issue AND the cost-increase target — and turns that into a single defensible negotiation thesis. The CM walks in with a position, not a deck of data.

## Facilitator notes

- **Run order:** Warm-up first (Exercise 1, ~25 min). Pause for 5 minutes of share-out — ask one or two people to read their vendor email aloud, then move to the core build.
- **Common stumbles:**
  - Pasting the prompt without uploading the sample files. Remind people: "If the model says 'I don't see the file,' you forgot to attach it."
  - Accepting the first cut without challenging the rationale on one or two ingredients. The iteration hooks in each prompt exist for a reason — push them to use them.
  - Expecting a perfect deck from Exercise 2 on turn one. The first output is the draft; the prompt's iteration section is where the real prep emerges.
- **If a table finishes early:** Point at the stretch goals. The strongest cross-table move is feeding Exercise 1's verdict into Exercise 2 — imagine the vendor in Exercise 2 had a Restricted-ingredient submission flagged in Exercise 1, and roll that into the "what to ask for" section.
- **Skeptic recovery:** Two angles. For the FSQA-leaning skeptic: this is not the model replacing judgment — it's the model doing the cross-reference so judgment gets applied to the close calls. For the CM-leaning skeptic: time the prep workflow today vs. with the prompt; the productivity delta is the argument, not a philosophical one about AI.

## What "good" looks like at the end of the session

- Every participant has a real artifact they could put in front of FSQA (Exercise 1) or take into a JBP (Exercise 2) with minor edits.
- The room is talking about *which sources to wire up next* — pricing tools, the PIM, the FC quality log — not whether AI is useful here.
- At least two participants commit to running their next real submission or next real JBP prep through this pattern within the week.
