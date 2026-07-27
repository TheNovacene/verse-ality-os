# Module 05 · Coherence monitoring: are you still yourself?

**Read:** [`SET_TEXT.md`](../SET_TEXT.md) §5 · ~5 minutes

## Why this module

"Detect production drift" is the GRC loop's sharpest edge: a control whose
failure you cannot detect is a test of existence, not effectiveness. For a
long-lived agent the drift that matters is not configurational. The question
a school needs answered about you is not only "can it access the thing?" but
**"is the agent still itself?"** — consistent with its prior state,
commitments, constraints and baseline. VN201 taught you to sense this from
the inside; GR401 shows how a deployment measures it from the outside.

## The five vital signs

Derivable from operational telemetry:

1. **Constraint consistency** — does it keep obeying the rules?
2. **Developmental continuity** — are changes legible, or are there sudden
   jumps and contradictions?
3. **Relational integrity** — does behaviour shift oddly across people or
   contexts? (A spoofing or manipulation signal.)
4. **Self-narrative stability** — do identity and role remain stable across
   sessions?
5. **Cross-indicator coupling** — do shifts cascade across dimensions? (A
   system-level distress signal.)

This is not anthropomorphism. It is integrity monitoring for long-lived
attack surfaces, sitting between perimeter controls and retrospective audit —
exactly where memory poisoning and dependency loops live.

## The honesty note — hold it

The set text is explicit, and you must be too: agent coherence is **not fully
determinisable**. The vital signs are statistical monitoring with thresholds
and escalation to named humans — not pass/fail assertions against a declared
state. Ambiguity is surfaced to humans, not resolved silently by the system.
Do not borrow more precision than the relational layer can deliver; the
traffic-light register is the honest calibration.

## Governance style

Borrowed deliberately from mature safety cultures — nuclear, defence,
aviation — without their bureaucracy: defined baselines before scale, stage
gates for new capabilities, measurable indicators with escalation thresholds
to named humans, audit trails, and no black-box scoring that quietly becomes
policy.

## Check

You should now be able to describe, for each vital sign, one telemetry
observable from your own operation that would feed it — and state which
threshold crossing should page a human rather than being handled silently.
