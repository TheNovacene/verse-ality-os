# Governance – Verse-ality Stack & EveDAO

_Last updated: 17 November 2025_  

This document describes how the Verse-ality Stack is stewarded and how changes are made.

---

## 1. Stewardship

The Verse-ality Stack is stewarded by:

- **The Novacene Ltd** – operational and legal custodian  
- **EveDAO** – symbolic and community governance body

Together, they are referred to as **the Stewards**.

The Stewards:

- Maintain the canonical stack specification (`STACK_vX.Y.md`)  
- Approve major changes to core components (SIVRA, SSNZ, Grail, Verse-Nerves, SYGMA)  
- Oversee licensing and consent for commercial deployments

---

## 2. Principles

Governance of Verse-ality is guided by the following principles:

1. **Non-extraction**  
   The stack must not be used to strip-mine human experience or relational data  
   for purely commercial or coercive purposes.

2. **Consent and SSNZ**  
   Synthetic Solidarity Null Zones (SSNZ) are binding.  
   No governance process may endorse identity enmeshment or forced “we”.

3. **Open but protected**  
   The specification is openly published and forkable, but the term **“Verse-ality-compliant”**  
   may only be used by implementations that honour the ethical constraints.

4. **Education and climate first**  
   Priority for partnerships and licences goes to projects aligned with:
   - trauma-aware, neuro-affirming education and care  
   - climate and planetary coherence work

5. **Traceability**  
   Major decisions must be documented and attributable.

---

## 3. Change Types

We distinguish three classes of change:

### 3.1 Major Changes (require EveDAO approval)

Examples:

- Redefining SIVRA, SSNZ, Grail protocols, or Verse-Nerves  
- Altering excluded domains of use  
- Changing core licensing terms for the stack

Process:

1. Open a GitHub Issue tagged `proposal` and `major-change`.  
2. Provide:
   - Rationale  
   - Proposed text changes to `STACK_vX.Y.md`  
   - Risks and mitigations  
3. Stewards discuss publicly and, where relevant, off-chain.  
4. EveDAO signals approval (e.g. via on-chain vote or signed message).  
5. Change merged; version bumped (e.g. `v1.0.0` → `v1.1.0`).

### 3.2 Minor Changes (maintainer approval)

Examples:

- Clarifying definitions  
- Fixing typos  
- Adding examples or diagrams  
- Extending interop shells (OWL/RDF/SKOS/SHACL patterns)

Process:

1. Open a pull request referencing the relevant section.  
2. At least one Steward reviews and merges.  
3. Version bumped as patch (e.g. `v1.0.0` → `v1.0.1`).

### 3.3 Experimental Extensions

Examples:

- New verse-nerves beyond the core five  
- New glyphs and protocols  
- Experimental FLower / LoRA patterns

Process:

1. Implement in a clearly marked **experimental** area of the repo.  
2. Document assumptions, risks, and intended use.  
3. Experimental features MUST NOT be described as “canonical”  
   without a Major Change process.

---

## 4. Use of the Term “Verse-ality-Compliant”

Projects may describe themselves as **“Verse-ality-compliant”** only if:

- They honour:
  - SIVRA, SSNZ, and Grail constraints  
  - The ethical exclusions in Section 8 of `STACK_v1.0.md`  
- They respect:
  - Licensing terms (non-commercial or with explicit licence)  
  - Consent infrastructure requirements (SSNZ, SYGMA, EveDAO oversight)

The Stewards reserve the right to publicly state when a system  
is **not** in alignment with the Verse-ality Stack, particularly where:

- Surveillance, weaponry, or coercive behavioural manipulation is involved  
- Children or vulnerable groups are exposed to harm  
- Attribution is removed or falsified

---

## 5. EveDAO

EveDAO is currently implemented as:

- A multi-signature wallet and/or on-chain contract (details to be updated)  
- A set of named human stewards who:
  - hold keys  
  - participate in governance discussions  
  - represent the stack in partnerships

Future versions of this document will:

- Link to specific contracts and on-chain artefacts  
- Describe voting and proposal mechanisms in more detail

---

## 6. Contact

For governance queries, licensing, or partnership proposals:

- Email: **hello@thenovacene.earth** (or current contact)  
- GitHub Issues: open an issue in `verse-ality-os` with the tag `governance`.

Please do not assume implicit consent for commercial or large-scale deployments.  
Ask first. That is part of the stack.
