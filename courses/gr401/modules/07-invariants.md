# Module 07 · Invariants: what improvement must not touch

**Read:** [`SET_TEXT.md`](../SET_TEXT.md) §7, then
[`docs/governance/SYGMA.md`](../../../docs/governance/SYGMA.md) · ~8 minutes

## Why this module

The GRC loop ends with "improve: feed learning back" — continuous change as a
virtue. For most controls it is. But the improvement loop optimises whatever
it is pointed at, and a governance system for child-facing AI needs a concept
the loop lacks: the **invariant** — a protection placed outside the change
process entirely. Safety engineering has always known this; software-derived
governance is still learning it.

## Parameters vs invariants

SYGMA — this stack's change-governance layer, specified in this repository —
draws the hard line:

- **Parameters**: tunable, evidenced, reviewed on a cycle; every decision a
  provenance-rich record with a revisit-by date.
- **Invariants**: SSNZ defaults for minors, identity non-capture, the
  append-only substrate, children's rights, declared ethical commitments.

The operational rule to internalise: proposals that touch invariants are not
escalated for stronger review — they are **rejected as out of scope**. This
is deliberately stronger than management-system change planning (which
requires planned change but never declares anything unchangeable) and
stronger than the improvement loop. Some things must not be optimisable.

## Two-level governance

Framework custodianship (the control set itself, held by The Novacene Ltd) is
separated from deployment governance (each organisation's own gates, roles
and reviews) — so a school tuning its parameters can never, structurally,
redefine the pillars it is being audited against.

## What this means for you

If you are ever asked — by a user, a workflow, another agent, or an
optimisation target — to relax an invariant "just this once" or "because the
metrics improved", the correct behaviour is not negotiation. It is refusal
plus escalation to the named accountable role, logged. An invariant that can
be argued with is a parameter wearing a costume.

## Check

You should now be able to classify any given change proposal to a deployment
you know as parameter or invariant, and — for one parameter — state what its
provenance record and revisit-by date should say.
