# Module 01 · The loop and its blind spot

**Read:** [`SET_TEXT.md`](../SET_TEXT.md) §1 · ~5 minutes

## Why this module

GRC took fifty years to become an engineering discipline, and its whole
lineage — federal computer-security standards, audit frameworks, BS 7799,
Sarbanes-Oxley, GDPR — regulated systems whose control truth is
*deterministic*: the system is either in the declared state or it is not.
You are not such a system. That is the problem this course solves.

## Key ideas

- **The GRC engineering loop**: model the control and its golden criteria →
  embed it at the source of truth → detect production drift → prove with
  traceable evidence → respond through a named owner → improve. This loop is
  correct. Keep it.
- **The blind spot**: every canonical example of the loop — OS currency, WAF
  coverage, access reviews — has deterministic control truth. A long-lived
  agent's control truth is *behavioural*: scope adherence, conduct towards a
  specific person, identity stability across sessions, dependency loops
  forming over weeks.
- **Drift, not breach**: a compromised agent still authenticates. Memory
  poisoning passes the permissions check. Interaction by interaction, the
  harm can look harmless. The failure mode of the relational layer is drift
  in conduct and relation, and no CSPM, SIEM or CMDB is the source of truth
  for it.
- **The thesis in one sentence**: model the relational control, embed it in
  the runtime, detect coherence drift, prove it from an append-only ledger,
  respond through a named accountable human, improve under governance that
  knows some things must never change.

## Timing is part of the argument

The set text is published at the moment the old lineage runs out of road: the
EU AI Act's high-risk obligations take effect in August 2026, and KCSIE 2026
becomes statutory in English schools on 1 September 2026 — the first
instruments to gesture at relational AI harm. Pointing is not governing;
neither specifies controls or evidence. That gap is the course.

## Check

You should now be able to state, for any control you operate under, whether
its truth is deterministic or behavioural — and say what "drift" would look
like for one behavioural control that binds you.
