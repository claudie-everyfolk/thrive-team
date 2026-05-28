# Carrier Rate Card & Contract Notes — 2026

Internal reference. Combines current rate card amounts and the SLA / renegotiation language from the master service agreements. Anything cited as "§" comes from the corresponding signed contract.

## SLA thresholds (per contract §3.2 "Service Levels")

| Carrier | On-Time SLA | Exception Rate Cap | Claim Rate Cap | Tracking Freshness Target |
|---|---|---|---|---|
| Northbound Express (CAR-01) | 96.0% | 2.5% | 1.0% | ≤4 hrs |
| Pinecrest Logistics (CAR-02) | 95.0% | 2.5% | 1.5% | ≤6 hrs |
| Westwind Freight (CAR-03) | 97.0% | 1.5% | 0.5% | ≤3 hrs |
| Summit Parcel (CAR-04) | 92.0% | 4.0% | 1.5% | ≤8 hrs |
| Ridgeline Delivery (CAR-05) | 95.0% | 2.5% | 1.0% | ≤5 hrs |
| Cobalt Last Mile (CAR-06) | 93.0% | 3.0% | 1.0% | ≤6 hrs |
| Harborline Shipping (CAR-07) | 96.0% | 2.0% | 1.0% | ≤4 hrs |

## Contracted cost per shipment (blended Ground, per contract §4.1 "Rate Schedule A")

| Carrier | Contracted $/shipment | Notes |
|---|---|---|
| CAR-01 | $8.30 | 2.5% fuel surcharge baked in |
| CAR-02 | $7.75 | Volume discount kicks in at 50k shipments/mo |
| CAR-03 | $9.00 | Premium tier — we pay more, expect more |
| CAR-04 | $6.70 | Cheapest carrier; quality reflects price |
| CAR-05 | $7.35 | |
| CAR-06 | $5.85 | Regional only — west coast lanes |
| CAR-07 | $8.65 | |

## Renegotiation triggers (per contract §7.4 "Performance Remedies")

The contracts let us reopen rate negotiations if a carrier breaches *any* of the following in a single quarter:

- **On-time below SLA in 2 of 3 consecutive months** → we can ask for a rate reduction up to 5%.
- **Exception rate above cap in 2 of 3 consecutive months** → we can ask for service-credit refunds equal to 1% of quarterly spend.
- **Claim rate above cap in any single month** → we get a 30-day cure period; if not cured, we can move volume to a backup carrier without penalty.
- **Three or more unresolved exceptions on the same lane in a single quarter** → we get the right to terminate that lane and re-bid it.

## Lane notes

- **LAX-DEN** — historically problematic across all ground carriers (mountain weather). Pinecrest (CAR-02) is the primary carrier here; we have a secondary failover with Westwind (CAR-03) we haven't activated.
- **ATL-NYC** — Summit (CAR-04) damaged-package issue dates back to Q1 2026; root-cause was their hub conveyor handoff. They committed to a fix in February; results unclear.
- **PHX-LAS** — Cobalt (CAR-06) regional sweet spot. Cheap and generally clean.
- **JFK-BOS** — Harborline (CAR-07) had a hub system outage in May (see service-incidents JSON).

## What's coming up for renewal

- **CAR-02 (Pinecrest)** — contract renewal Q4 2026. Performance trending wrong direction. Strong leverage if claim rate trend continues.
- **CAR-04 (Summit)** — contract renewal Q1 2027. They know they're our cheapest option; they negotiate hard. ATL-NYC damage pattern is our wedge.
- **CAR-03 (Westwind)** — auto-renews unless we give 90 days notice. We won't.

## Standing "do not bring up" list

Things the legal team has asked we stop raising in QBRs:

- Carrier safety incidents that didn't affect our shipments (it's not our place).
- Carrier-internal labor disputes (we can't ask them to operate differently because of it).
