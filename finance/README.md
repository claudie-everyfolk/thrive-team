# Finance & Accounting — AI Training Session Brief

**Attendees:** ~20
**Session length:** ~90 minutes (warm-up + core + share-back)

## Who they are

A lean FP&A and Accounting team supporting every function of a mid-sized DTC subscription business. FP&A owns month-end close, AOP variance commentary, the Executive Flash, and finance business partnering with department leaders. Accounting owns the GL, accruals, AP, vendor management, and SOX controls. Small team, broad surface area, monthly cadence that never slips.

## Their day, where AI fits

About half of every close cycle disappears into data prep before any actual analysis happens — pulling actuals, restating to AOP cuts, cross-referencing prior year, hunting for the right driver in a Slack thread from three weeks ago. The Executive Flash routinely takes 2+ days after lock because variance commentary is hand-stitched line by line. On the AP side, merchandise invoice variances get worked one at a time — open the invoice, find the PO, pull the receipt, decide on routing, repeat fifteen times before lunch. The pattern across both subfunctions is identical: scattered structured data + tribal context that lives in someone's head + a deliverable due at a fixed time. Exactly the "synthesize my chaos" shape.

## Exercise 1 — Variance Commentary Drafter (`01-variance-commentary-drafter`)

- **Complexity:** Easy-Medium
- **Time:** ~20-25 min
- **The build:** A first-pass Executive Flash variance pack — headline summary, full variance table vs AOP and vs PY ranked by materiality, first-pass commentary on the top 5 variances tied to documented business drivers, watchlist, and FBP huddle questions.
- **Wow moment:** The model doesn't just compute variances — it cross-references the context notes file and writes commentary that names the driver ("Performance Marketing $340K unfavorable vs AOP, driven by the planned GLP-1 audience expansion test launched April 7, in-plan per Q2 approval"). For an FP&A analyst who normally spends ninety minutes reverse-engineering the same explanations, this is the "oh" moment.

## Exercise 2 — AP Bill Variance Triage (`02-ap-bill-variance-triage`)

- **Complexity:** Medium-Hard
- **Time:** ~35-45 min
- **The build:** A full triage pack for 15 merchandise invoices stuck in the variance queue — auto-approve vs escalate classification, variance type per invoice using the tolerance rules doc, resolution path, three paste-ready vendor outreach emails for the top-dollar variances, FC/category-manager escalation notes, and a vendor pattern flag.
- **Wow moment:** The triage table shows one vendor showing up four times (Brightline Goods) and the model flags it as a holistic vendor health item without being asked — connecting individual transactional variances to a vendor-relationship pattern. Plus the three vendor emails are tonally on-target (firm, specific, not adversarial) and reference the exact PO and invoice numbers.

## Facilitator notes

- **Run order:** Warm-up first. Have two or three FP&A folks read their variance pack out loud — especially the commentary on Performance Marketing — so the room hears how close it is to a real draft. Then move into the AP exercise. Build first, share-back at the end.
- **Audience split — call it out up front:** This room is half FP&A, half Accounting/AP. Exercise 1 will land harder for the FP&A side (it's literally their flash). Exercise 2 will land harder for the Accounting side (it's literally their AP queue). Name this explicitly at the top of the session, then push both sides to actually do both — the cross-table value is that FP&A sees how AP variance research works upstream, and AP sees how their work feeds variance commentary downstream. Pair an FP&A person with an Accounting person at each table if you can.
- **Common stumbles:**
  - Pasting the prompt without uploading the sample files — the model will hallucinate numbers. Make sure every table opens all 4 files first.
  - Skipping the tolerance rules doc in Exercise 2 — the model needs the doc to classify; without it the routing is guesswork.
  - Expecting perfect commentary on turn 1. The iteration hooks at the bottom of each prompt are the actual workflow — get the first cut, then sharpen.
- **If a table finishes early:** Stretch goals are in each prompt. The "make this run automatically every morning" hook is the right one to push — it's where this stops being a parlor trick and starts being infrastructure.
- **Skeptic recovery:** If someone walks in saying "AI can't do real accounting work," start them on Exercise 2 — the tolerance rules doc is a real policy artifact, the model applies it correctly, and the vendor email drafts are paste-ready. It's harder to wave that away than a generic chatbot demo.

## What "good" looks like at the end of the session

- Every participant walks out with a draft Executive Flash variance pack and a triaged AP variance batch on their laptop — artifacts they could plausibly use in a real close cycle with their own data.
- The FP&A folks are talking about the context-notes-as-driver-source pattern: that the leverage isn't in the variance math, it's in maintaining a running notes file the model can read.
- The Accounting folks are talking about the routing logic in the tolerance rules doc: that codifying the policy unlocks the whole triage flow, and that the next obvious move is a morning queue scan instead of one-at-a-time invoice work.
