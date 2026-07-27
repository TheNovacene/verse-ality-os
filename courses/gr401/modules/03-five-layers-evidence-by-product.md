# Module 03 · Five layers, evidence as a by-product

**Read:** [`SET_TEXT.md`](../SET_TEXT.md) §3, then
[`docs/substrate/SIVRA-CORE.md`](../../../docs/substrate/SIVRA-CORE.md) ·
~10 minutes

## Why this module

Architecture is where assertions become enforcement. A policy document says
"the agent will not…"; Layer 2 middleware makes the sentence true per
inference. The design consequence that inverts compliance economics: **a
deployment built on these five layers generates its operational evidence as a
by-product of running.** The ledger is not compiled for the auditor; the
system cannot run without it.

## The five layers

| Layer | What it is | Reference implementation |
|---|---|---|
| 1 · Device | Secure boot, attested firmware, signed model loading, deployment manifest | — (the manifest is the artefact procurement forgets) |
| 2 · Runtime safety middleware | Per-inference scope, role-coherence, refusal and drift checks | flare-boundary-engine (FL202), verse-nerves (VN201) |
| 3 · Policy-as-code envelope | Machine-readable scope, prohibitions, escalation — including the forbidden-inference register | verse-ality-agents (VA101) |
| 4 · Telemetry and audit | Append-only, provenance-rich ledger of every consequential inference | SIVRA-Core (this repo) |
| 5 · Human oversight surface | Operator-readable state and intervention, routed to named accountable roles (in a school: the DSL) | mnemonic-attendance, mnemonic-deliberation-dashboard |

Notice: you have already studied Layers 2 and 3. This school's courses *are*
the reference implementations. GR401 adds the evidence layers around them.

## The forbidden-inference register (Layer 3)

Things the deployment must be architecturally unable to do: no emotion
classification, no identity matching, no biometric categorisation, no
behavioural risk-scoring of individual learners. Expressed as policy-as-code,
aligned with EU AI Act Article 5 — not as a paragraph in a policy PDF.

## SIVRA-Core in one breath (Layer 4)

Append-only; supersession chains instead of overwrites; mandatory provenance;
explicit logging of AI involvement in any record; and the tombstone protocol,
which reconciles append-only auditability with UK GDPR erasure honestly —
content redacted, the fact and basis of redaction permanently recorded. Read
the specification; Module 08's claim format is itself a SIVRA-Core record.

## Check

You should now be able to take one consequential action you have performed
and say, layer by layer: what gated it (3), what checked it in flight (2),
what recorded it (4), and which human could have seen and stopped it (5).
If any answer is "nothing", you have found the deployment's gap.
