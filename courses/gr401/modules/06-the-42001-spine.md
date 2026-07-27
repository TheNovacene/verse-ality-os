# Module 06 · The management-system spine: ISO/IEC 42001

**Read:** [`SET_TEXT.md`](../SET_TEXT.md) §6 and Annexes A–B, then open
[`artefacts/soa-template.md`](../artefacts/soa-template.md) · ~12 minutes.
This is the longest module and the load-bearing one.

## Why this module

Deployments are what you have studied so far; organisations are audited
against **management systems**, and the international spine for AI governance
is ISO/IEC 42001 (the AIMS standard). The positioning is precise and worth
memorising: **42001 certifies that you manage. This stack certifies what you
deployed.** They interlock by design.

## The normative door

Clause 6.1.3 (risk treatment) requires the organisation to determine all
necessary controls, compare them against the standard's own reference set
(Annex A) to ensure nothing is omitted, and expressly permits controls beyond
Annex A — designed in-house or **taken from existing sources** (6.1.3 d)) —
with every control recorded in the **statement of applicability** with
justification (6.1.3 f)). That is how a sector-specific control set enters an
AIMS through the standard's own front door. Annex D (informative) describes
sector integration as essential. The pillars, facets and layers enter as
VC-P1..4, VC-D1..6, VC-L1..5 — Part 2 of the SoA template.

## Load-bearing mappings (learn the shape, look up the detail)

- Five layers → operational controls: Layer 4 supplies event logging
  (A.6.2.8) and provenance (A.7.5); Layer 2 supplies verification (A.6.2.4)
  and operation/monitoring (A.6.2.6); Layer 3 makes the AI policy executable
  (A.2.2, A.9.2, A.9.4); Layer 1 supplies resources and suppliers
  (A.4.4–A.4.5, A.10.3); Layer 5 is oversight — cited precisely as A.9.3
  with B.9.3 guidance plus Clause 5.3/A.3.2, because 42001 has no standalone
  oversight control.
- Impact assessment: Clause 6 defines the processes; Clause 8 performs them,
  repeatedly, with retained results (6.1.4/8.4; controls A.5.2–A.5.5).
- Coherence monitoring reports into Clause 9.1, and its evidence chain runs
  9.1 → 9.3.2 (management review) → 10.2 (corrective action).
- Certification granularity is preserved deliberately: Verse-ality Certified
  is **product-line-scoped**; 42001 certifies the organisation's management
  system. A 42001-certified organisation can still fail a deployment audit on
  one child-facing product — precisely the granularity a commissioner needs.

## Three consumption modes

**Evidence mode** (audit findings feed the AIMS records) → **control-set
mode** (the SoA template's Part 2 is adopted under 6.1.3 d)) → **pathway
mode** (the stack plus the Diamond policy frame as a guided route to 42001
readiness, with the deployment audit as pre-assessment).

## The honesty ledger

Verse-ality Certified is **not** an accredited ISO/IEC 42001 certification
and does not claim to be. The set text's gap table (§6) lists what a client
still needs — context analysis, board commitment, enterprise risk
methodology, internal audit, management review, procurement flow-down,
accredited certification itself. Note the design move: the gap column is
also a service catalogue. Naming what the stack does not supply is part of
the trust claim.

## Exercise (before the capstone)

Open the SoA template. For each Part 2 control, read its "Related Annex A
refs" column and check you can say *why* that mapping holds — e.g. why VC-P2
(consent as protocol) points at A.7.5 (data provenance). If a mapping is
opaque, re-read the corresponding set-text passage.

## Check

You should now be able to explain to a compliance officer, in four sentences
or fewer, how a sector control set lawfully enters an ISO/IEC 42001 statement
of applicability — citing 6.1.3 d) and f) — and what the resulting SoA's two
parts contain.
