# Ingredient Compliance Review

I'm a Category Manager on the natural-foods grocery team. A brand partner just submitted a new product for our owned & partner brand program, and before I can move it forward I need to do an ingredient-by-ingredient compliance check against our standards.

Today this takes me anywhere from 45 minutes to several hours per SKU. I scroll the ingredient list, jump into the restricted-ingredients sheet, cross-check the standards document, decide what's a hard reject vs what's recoverable with documentation, then write the vendor email asking for the missing pieces. Most of the time goes into the cross-referencing, not the judgment. I want that flipped.

I've attached three files: the vendor's product submission (`product-submission-2026-05-18.md`), the FSQA quality standards document (`quality-standards-v4.md`), and the master restricted-ingredients list (`restricted-ingredients-master.csv`).

## What I need you to build

Using those three files, give me a single review packet with the following sections:

1. **Per-ingredient table.** One row per ingredient in the submission, in label order. Columns: `Ingredient`, `Status` (Acceptable / Restricted / Unacceptable), `Rationale` (one short sentence citing the rule), `Documentation needed` (specific document name from the standards, or "—"). Match each ingredient against both the CSV and the standards doc — they reinforce each other; flag any disagreement.

2. **Marketing-claim cross-check.** The submission lists claims like "gluten-free" and "non-GMO." For each claim, tell me whether the documentation on file (or NOT on file) supports keeping that claim on pack. Treat any claim without supporting documentation as a label-risk flag.

3. **Overall verdict.** One of: `Approve as submitted` / `Approve pending docs (needs-FSQA)` / `Reject — reformulation required`. Pick exactly one and justify it in two sentences referencing the most decisive ingredients.

4. **Doc-request list.** A clean bulleted list of every document I need to ask the vendor for, grouped by ingredient. If the same document covers two ingredients, say so.

5. **Draft vendor email.** Single email to the buyer contact in the submission. Friendly, professional, batches every doc request in one ask, references the specific ingredient triggering each request, and sets a 10-business-day clock per our vendor norms. Open with the verdict in plain language. No marketing speak.

## Why this matters

I'm not looking for a summary of the standards — I have those. I need the cross-reference *done*, with a recommendation I can defend in front of FSQA and a vendor email I can send today. The leverage is connecting the ingredient list to the restricted CSV to the standards doc to the marketing claims so I walk into my next vendor call already aligned, instead of spending the morning building the packet.

## After the first cut, I want to try

- Re-running this with a stricter posture: assume any Restricted ingredient missing docs is a soft reject unless the vendor is in our top 10.
- Asking you to draft a second version of the vendor email in a firmer tone, for vendors who have missed prior documentation deadlines.
- Generating an internal FSQA handoff note (separate from the vendor email) summarizing only the Restricted items and the specific risk language.

## Stretch goals (optional)

- Output the per-ingredient table as a CSV I can paste back into our submission tracker.
- Flag any allergen on the label that's NOT declared in the "Contains" statement, and vice-versa.
- Suggest a reformulation path for any Unacceptable ingredient (what's the closest Acceptable substitute the vendor is likely to have access to).
- Wire this up so I can drop any future submission markdown into a folder and get the review packet emailed to me automatically.
