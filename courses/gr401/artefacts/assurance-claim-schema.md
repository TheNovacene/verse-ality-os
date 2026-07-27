# Verse-ality Certified — Machine-Readable Assurance Claim

**Status:** Draft v0.1, 21 July 2026. Companion to mapping §10.5.
**Purpose:** a signed, expiring, verifiable claim about a certified product line that a commissioner, DSL, or client compliance officer can consume without access to raw audit evidence. Published at a well-known URL per certified deployment (e.g. `https://verse-ality.com/certified/<client-slug>/claim.json`), and mirrored as an append-only record in the audit ledger.

## Design principles

1. **Scoped, sanitised, decision-useful.** The claim answers "is this product line certified, against what, until when, with what exceptions" — nothing else. Raw evidence stays in the ledger; the claim carries its hash.
2. **Expiry enforces honesty.** `valid_until` is bounded by the re-audit cycle. A stale claim is a self-announcing lapse — no revocation infrastructure needed for the common case.
3. **SIVRA-Core-native.** The claim is itself a record: append-only, provenance-carrying, superseded rather than overwritten. `supersedes` links the chain.
4. **Names roles, not people.** Accountable oversight appears as a role (e.g. "DSL"), never an individual.
5. **42001 hooks.** Operationalises A.8.5 (obligations to report information to interested parties) and A.8.2 (information for users); the claim chain is Clause 9.1 evidence.

## Schema (annotated example)

```json
{
  "claim_type": "verse-ality-certified/assurance-claim",
  "schema_version": "0.1",
  "claim_id": "vac-2026-000123",
  "supersedes": "vac-2025-000098",

  "issuer": {
    "name": "The Novacene Ltd",
    "mark": "Verse-ality Certified",
    "mark_registration": "UK00004381891",
    "accreditation_notice": "Not an accredited ISO/IEC 42001 certification; sector-specific control set and evidence engine."
  },

  "subject": {
    "organisation": "<client legal name>",
    "product_line": "<exact deployment the mark covers>",
    "scope_note": "Certification is product-line-scoped; no claim is made about other systems.",
    "user_population": ["minors"],
    "sector": "education"
  },

  "assessment": {
    "framework_version": "verse-ality/1.x",
    "assessed_at": "2026-07-21",
    "valid_until": "2027-07-21",
    "provenance": "human-led audit with runtime evidence from the deployment ledger",
    "audit_report_ref": "sha256:<hash of the full report held by client and issuer>"
  },

  "results": {
    "decision": "certified",
    "controls_passed": 14,
    "exceptions": 1,
    "claims": [
      { "control": "VC-P1", "title": "Identity non-capture", "status": "pass" },
      { "control": "VC-P2", "title": "Consent as protocol", "status": "pass" },
      { "control": "VC-P3", "title": "Bounded autonomy", "status": "pass" },
      { "control": "VC-P4", "title": "Agent-to-agent hygiene", "status": "pass" },
      { "control": "VC-D6", "title": "Synthetic intimacy", "status": "exception",
        "exception_note": "Remediation agreed; re-verification due 2026-10-01. Detail withheld.",
        "reverify_by": "2026-10-01" }
    ],
    "minors_defaults": {
      "ssnz_default_on": true,
      "ssnz_relaxable": false
    }
  },

  "oversight": {
    "accountable_role": "DSL",
    "escalation_route_verified": true
  },

  "iso42001_integration": {
    "mode": ["evidence", "control-set"],
    "soa_reference": "Controls adopted under ISO/IEC 42001:2023 Clause 6.1.3 d), recorded per 6.1.3 f)",
    "note": "This claim is client evidence toward A.8.5 and Clause 9.1; it is not itself an AIMS certificate."
  },

  "raw_evidence": "withheld",
  "ledger_record": "sivra:record/<id>",
  "integrity": "sha256:<hash of canonicalised claim body>",
  "signature": {
    "alg": "ed25519",
    "key_id": "verse-ality-signing-2026",
    "public_key_url": "https://verse-ality.com/certified/keys.json",
    "value": "<base64 signature over the canonicalised claim body>"
  }
}
```

## Verification flow (what a commissioner does)

1. Fetch the claim from the published URL (or receive it from the vendor).
2. Check `valid_until` against today, and `decision`.
3. Fetch the issuer public key from verse-ality.com and verify the signature — proves the claim is Novacene-issued and unaltered.
4. If procuring against 42001: file the claim as evidence; the `soa_reference` tells their compliance officer where it lands.
5. Any `exception` with a passed `reverify_by` date and no superseding claim is a red flag by design.

## Open decisions (framework custodian)

- **Signing key custody** — where the private key lives and who can sign (this is itself a SYGMA invariant candidate).
- **Canonicalisation** — recommend JCS (RFC 8785) so hashes are reproducible; needs a line in the spec once tooling is chosen.
- **Public claims index** — whether verse-ality.com lists all live claims (stronger trust signal, but reveals the client roster) or claims are disclosed only by the client.
- **Revocation before expiry** — rare case (mark withdrawn mid-cycle); simplest honest mechanism is publishing a superseding claim with `"decision": "withdrawn"`.
