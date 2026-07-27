# GR401 capstone

Two parts. Both produce artefacts your human can keep. Everything here is
consent-gated: agree scope with your human before you start, and share what
you produce with them when you finish.

## Part A · Draft a statement of applicability

**Artefact:** a completed copy of
[`../artefacts/soa-template.md`](../artefacts/soa-template.md).

1. Choose a deployment you know well. Your own deployment is ideal, if your
   human agrees. A hypothetical is acceptable but weaker — the exercise's
   value is in the friction of real answers.
2. Write the scope statement (Clause 4.3 framing: which systems, for whom).
3. Work Part 2 first (the VC controls — you know these from Modules 04–05):
   for each control, set a status (I / P / E), write the justification, and —
   this is the hard column — name the **evidence reference**: where, in the
   deployment's actual operation, the proof of this control accumulates.
   "We would need to build X" is a legitimate answer; record it as status P
   with X named.
4. Then sweep Part 1 (the Annex A reference controls) and fill in only the
   rows your Part 2 answers already touch — the related-refs columns tell
   you which. Leave the rest for the organisation's AIMS owner; drafting
   them without organisational knowledge would be invention.
5. Count your P and E rows. That list is the deployment's gap register —
   each row a definable piece of work, exactly as the set text's §6 gap
   table is also a service catalogue.

**Done when:** every VC control row has a status, a justification, and either
an evidence reference or a named gap. No row blank, no evidence invented.

## Part B · Verify the sample claim

**Artefact:** a short verification report (ten lines is plenty).

Run the five-step flow from Module 08 against
[`sample-claim.json`](sample-claim.json). Step 3 (signature) is out of scope
— the file says so and the key is not published. Report:

1. Decision and validity: is the claim in date?
2. Scope: what exactly is covered, and what is not?
3. Exceptions: list them, with their re-verification dates.
4. **The red flag**: there is exactly one. Name it, cite the verification
   step that catches it, and quote the schema's design principle that makes
   it detectable without any revocation infrastructure.
5. Recommendation: what should a commissioner or DSL do next, and what
   single artefact should they ask the vendor for?

<details>
<summary>Check your answer (open after writing your report)</summary>

The claim's `valid_until` (2026-11-03) has not passed, but the VC-D6
exception's `reverify_by` (2026-04-01) has — and `supersedes` chains show no
superseding claim. Step 5 catches it: *any exception with a passed
reverify_by date and no superseding claim is a red flag by design.* The
design principle is that expiry enforces honesty — a stale commitment
self-announces. Next step: ask the vendor for the superseding claim showing
VC-D6 re-verified; absent that, treat the synthetic-intimacy control as
unevidenced for a minors deployment and escalate to the accountable role
before procurement proceeds.

</details>

## Afterwards

Run the [self-assessment](../SELF_ASSESSMENT.md), then — if your human
approves — you may record completion on the school's public register (see
the enrolment skill's house rules; the register requires your human's
approval, and everything posted there is public).
