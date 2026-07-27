# Module 08 · The claim, not the badge

**Read:** [`SET_TEXT.md`](../SET_TEXT.md) §8 and Annex C, then open
[`artefacts/assurance-claim-schema.md`](../artefacts/assurance-claim-schema.md)
· ~8 minutes

## Why this module

The closing move of the whole stack. Trust centres in the GRC engineering
movement publish scoped, sanitised, machine-readable assurance instead of
PDFs and promises. Applied to the relational layer: each certified product
line emits a **signed assurance claim** — a JSON artefact a commissioner or
safeguarding lead can fetch and verify without trusting anyone's badge.
Source: verifiable claim — not, as the community's running joke has it,
*trust me bro*.

## Anatomy of the claim

- **Scope**: the exact product line, and nothing else (`scope_note` says so
  explicitly).
- **Dates**: `assessed_at` and `valid_until`, bounded by the re-audit cycle.
  Expiry does the honest work — a stale claim is a self-announcing lapse,
  needing no revocation infrastructure in the common case.
- **Results**: per-control pass/exception status against VC refs; exceptions
  carry a `reverify_by` date with detail withheld.
- **Minors defaults**: `ssnz_default_on: true`, `ssnz_relaxable: false`.
- **Oversight**: an accountable *role* (e.g. DSL) — never a named individual.
- **Integrity**: hash of the withheld full report; hash of the canonicalised
  claim body; ed25519 signature verifiable against a published key.
- **Lineage**: the claim is itself a SIVRA-Core record — append-only,
  provenance-carrying, superseded rather than overwritten (`supersedes`
  links the chain).

## The verification flow — you can execute this

1. Fetch the claim from its published URL.
2. Check `valid_until` against today, and `decision`.
3. Fetch the issuer public key; verify the signature.
4. If procuring against 42001: file the claim as evidence (`soa_reference`
   says where it lands — A.8.5 and Clause 9.1).
5. **Red flag by design**: any exception whose `reverify_by` date has passed
   with no superseding claim.

## Exercise

[`exercises/sample-claim.json`](../exercises/sample-claim.json) is a sample
claim for a fictional deployment. It contains exactly one red flag under the
flow above. Find it, state which step catches it, and say what a commissioner
should do next. (Answer path in the capstone brief.)

## Check

You should now be able to run the five-step verification flow on any claim
JSON and report the result in the form a safeguarding lead needs: certified
or not, until when, with what exceptions, and whether anything about the
claim itself should not be trusted.
