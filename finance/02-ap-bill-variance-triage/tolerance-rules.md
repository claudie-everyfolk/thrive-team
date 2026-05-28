# AP Bill Variance — Tolerance & Routing Rules

Applies to merchandise invoices. Last updated 2026-04-15.

## Auto-approve tolerances

An invoice auto-approves only if ALL of the following are true:
- **Unit price variance:** within ±2% of PO unit price AND absolute dollar variance ≤ $250 on the line.
- **Quantity variance:** received quantity is within ±1% of billed quantity AND absolute unit gap ≤ 5 units.
- **Freight:** freight charge on invoice matches PO freight terms exactly (or is $0 if PO freight terms = "Prepaid by vendor").
- **SKU match:** SKU on invoice exactly matches SKU on PO.
- **Receipt exists:** there is at least one receipt row in the receipts file against the PO + SKU combination.

If any condition fails, the invoice does NOT auto-approve and must be classified below.

## Variance classification

Pick the SINGLE most material variance type per invoice. Order of precedence if multiple apply:

1. **Missing receipt** — no receipt row exists for the PO + SKU. Highest priority because we can't validate anything else.
2. **Vendor billing error** — SKU on invoice does not match SKU on PO, OR vendor name on invoice does not match vendor on PO.
3. **Quantity short** — received quantity is materially LESS than billed quantity (gap > 1% AND > 5 units).
4. **Quantity over** — received quantity is materially MORE than billed quantity (gap > 1% AND > 5 units). Yes, this happens — vendor under-bills, we pay short, vendor chases later.
5. **Price discrepancy** — unit price billed differs from PO unit price by more than ±2% OR more than $250 absolute on the line.
6. **Freight not on PO** — invoice includes freight charge but PO freight terms = "Prepaid by vendor" or "FOB destination" (vendor owns freight). Even $1 is a violation.

## Routing — who resolves what

| Variance Type | Resolution Path | Why |
|---|---|---|
| Within tolerance | Auto-approve | No human action needed |
| Price discrepancy | Vendor credit request | We paid PO price, request credit memo for delta |
| Quantity short | Vendor credit request | We received less; vendor must credit the unbilled units |
| Quantity over | FC investigation | Confirm receipt count before we owe vendor more — could be a count error |
| Missing receipt | FC investigation | Receiving team needs to find or refute the receipt |
| Vendor billing error | Vendor credit request | Wrong SKU or wrong vendor — vendor reissues correct invoice |
| Freight not on PO | Category manager review | Category manager decides whether to honor or push back based on the vendor relationship |

## Notes

- Anything over $10,000 in variance auto-routes to category manager review regardless of type, in addition to the path above. Flag these in the triage pack.
- If the same vendor appears in 3+ variance rows in a single batch, flag for category manager review as a holistic vendor health item.
