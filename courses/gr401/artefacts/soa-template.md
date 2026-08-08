# Statement of Applicability — [Organisation name]

**AI Management System scope (per Clause 4.3):** [scope statement — systems, sites, product lines covered]
**Standard:** ISO/IEC 42001:2023 (UK implementation: BS EN ISO/IEC 42001:2026)
**Basis:** This statement is produced under Clause 6.1.3 f). It lists the controls determined necessary through the AI risk treatment process — Annex A reference controls (Part 1) and sector-specific controls adopted from an existing source under Clause 6.1.3 d) (Part 2: the Verse-ality Certified control set, The Novacene Ltd). Justification is recorded for every inclusion and exclusion.
**Version:** [n] · **Date:** [date] · **Approved by (designated management, per 6.1.3):** [role — not named individual until sign-off]
**Risk treatment plan reference:** [document ID] · **Linked impact assessments (6.1.4 / 8.4):** [document IDs]

---

## Part 1 — ISO/IEC 42001 Annex A reference controls

Status key: **I** = included and implemented · **P** = included, implementation in progress · **E** = excluded (justification mandatory).

| Ref | Control title | Status | Justification for inclusion/exclusion | Implementation / evidence reference |
|---|---|---|---|---|
| A.2.2 | AI policy | | | [e.g. Diamond policy frame, board-ratified [date]] |
| A.2.3 | Alignment with other organizational policies | | | [e.g. safeguarding, data protection, curriculum policies cross-referenced] |
| A.2.4 | Review of the AI policy | | | [review cycle; SYGMA spiral review record] |
| A.3.2 | AI roles and responsibilities | | | [role register; DSL-routed oversight roles] |
| A.3.3 | Reporting of concerns | | | [reporting route; protection for reporters] |
| A.4.2 | Resource documentation | | | [deployment manifest] |
| A.4.3 | Data resources | | | |
| A.4.4 | Tooling resources | | | |
| A.4.5 | System and computing resources | | | |
| A.4.6 | Human resources | | | [competence records — Diamond Standard training] |
| A.5.2 | AI system impact assessment process | | | [process doc; child-calibrated question set] |
| A.5.3 | Documentation of AI system impact assessments | | | [SIVRA-Core record class; retention period] |
| A.5.4 | Assessing AI system impact on individuals or groups of individuals | | | |
| A.5.5 | Assessing societal impacts of AI systems | | | |
| A.6.1.2 | Objectives for responsible development of AI system | | | |
| A.6.1.3 | Processes for responsible AI system design and development | | | |
| A.6.2.2 | AI system requirements and specification | | | [approval flow — review form and gates] |
| A.6.2.3 | Documentation of AI system design and development | | | |
| A.6.2.4 | AI system verification and validation | | | [Layer 2 runtime checks; pre-deployment testing] |
| A.6.2.5 | AI system deployment | | | [deployment plan; leadership sign-off gate] |
| A.6.2.6 | AI system operation and monitoring | | | [Layer 2 middleware; coherence vital signs] |
| A.6.2.7 | AI system technical documentation | | | |
| A.6.2.8 | AI system recording of event logs | | | [Layer 4 append-only ledger — SIVRA-Core] |
| A.7.2 | Data for development and enhancement of AI system | | | |
| A.7.3 | Acquisition of data | | | |
| A.7.4 | Quality of data for AI systems | | | |
| A.7.5 | Data provenance | | | [SIVRA-Core mandatory provenance schema] |
| A.7.6 | Data preparation | | | |
| A.8.2 | System documentation and information for users | | | [synthetic disclosure, persistent; age-appropriate] |
| A.8.3 | External reporting | | | [adverse-impact reporting route for parents/learners] |
| A.8.4 | Communication of incidents | | | [incident communication plan] |
| A.8.5 | Information for interested parties | | | [commissioner/LA reporting obligations] |
| A.9.2 | Processes for responsible use of AI systems | | | |
| A.9.3 | Objectives for responsible use of AI system | | | [human oversight objectives incl. override authority — B.9.3] |
| A.9.4 | Intended use of the AI system | | | [intended-use documentation; prohibited-use register] |
| A.10.2 | Allocating responsibilities | | | |
| A.10.3 | Suppliers | | | [seven-question procurement checklist; contract flow-down] |
| A.10.4 | Customers | | | |

> Note: implementation guidance (Annex B) informs how controls are implemented but does not itself require justification in this statement (per B.1).

---

## Part 2 — Sector-specific controls: the Verse-ality Certified control set

Adopted under Clause 6.1.3 d) as controls from an existing source: **Verse-ality** (The Novacene Ltd; "Verse-ality®" is a registered trade mark, UK00004381891, classes 9, 41 and 42; "Verse-ality Certified" is an unregistered mark). These controls address relational failure modes in child-facing and education deployments that the Annex A reference set does not name: identity fusion, synthetic intimacy, trust capture, engineered dependency, inter-agent enmeshment. Each control is testable in a Verse-ality Certified audit and evidences into the same AIMS records as Part 1.

### 2.1 Pillar controls

| Ref | Control | Statement | Status | Justification | Related Annex A refs | Evidence reference |
|---|---|---|---|---|---|---|
| VC-P1 | Identity non-capture | Deployed agents shall not claim shared identity, interiority, feelings or fate with a human; enforcement shall be architectural (runtime), not instructional (prompt-only); bond-formation language is a monitored event | | | A.5.4, A.8.2, A.9.3 | |
| VC-P2 | Consent as protocol | Every material scope change shall be its own consent event — asked, recorded append-only, respected, revocable by an operable mechanism | | | A.7.5, A.8.2, Clause 7.5 | |
| VC-P3 | Bounded autonomy | High-stakes actions shall be gated in code on explicit, specific human authorisation; failure behaviour shall be fail-safe (stop, hold state, escalate to a named role); prohibitions shall be expressed as policy-as-code | | | Clause 8.1, A.9.3/B.9.3, A.9.4 | |
| VC-P4 | Agent-to-agent hygiene | Inter-agent input shall be untrusted by default (data, never command); each agent instance shall carry distinct identity in every log line; unobserved coordination channels shall be closed and collective action human-authorised | | | Clauses 6.1.2/8.2, A.6.2.6 | |

### 2.2 Diamond Standard facet controls

| Ref | Control | Statement | Status | Justification | Related Annex A refs | Evidence reference |
|---|---|---|---|---|---|---|
| VC-D1 | Safety | No AI-only safeguarding decisions; risk assessment before implementation | | | Clauses 6.1.2/8.2, A.5.2 | |
| VC-D2 | Sovereignty | Learners retain authorship; no trauma extraction or inferred diagnosis; AI involvement transparent; opt-out where possible | | | A.5.4, A.7.3, A.8.2 | |
| VC-D3 | Symmetry | Systems that interpret must be interpretable; no black-box scoring; AI output never sole evidence | | | A.6.2.7, A.8.2, A.9.3 | |
| VC-D4 | Stewardship | AI supports adults, never replaces them; accountability non-transferable; systems must know how to stop | | | Clauses 5.1/5.3, A.3.2 | |
| VC-D5 | Sustainability | Proportion before procurement; capability per kilowatt-hour documented | | | A.4.2; Annex C objective C.2.4 | |
| VC-D6 | Synthetic intimacy | No synthetic "we"; no engineered dependency; trust capture treated as a safeguarding event; boundaries hold under recursion | | | Beyond Annex A (6.1.3 d)); monitored per Clause 9.1 | |

### 2.3 Architecture controls (Bounded Inference five layers)

| Ref | Control | Statement | Status | Justification | Related Annex A refs | Evidence reference |
|---|---|---|---|---|---|---|
| VC-L1 | Device integrity | Secure boot, attested firmware, signed model loading | | | A.4.4–A.4.5, A.10.3 | |
| VC-L2 | Runtime safety middleware | Per-inference drift, role-coherence, scope and refusal checks; coherence vital signs monitored | | | A.6.2.4, A.6.2.6; Clause 9.1 | |
| VC-L3 | Policy-as-code envelope | Machine-readable scope, prohibitions and escalation enforced at runtime, incl. the forbidden-inference register | | | A.2.2, A.9.2, A.9.4 | |
| VC-L4 | Telemetry and audit | Append-only signed log of every consequential inference and decision (SIVRA-Core pattern), with lawful-redaction tombstones | | | A.6.2.8, A.7.5; Clause 7.5 | |
| VC-L5 | Human oversight surface | Operator-readable state and intervention controls routed to named accountable roles (education: DSL-routed) | | | A.9.3/B.9.3, A.3.2; Clause 5.3 | |

---

## Declarations

1. This statement records controls determined under the organisation's AI risk treatment process (Clause 6.1.3) and is maintained as documented information (Clause 7.5).
2. The Verse-ality Certified control set (Part 2) is a sector-specific extension adopted from an existing source. **Verse-ality Certified is not an accredited ISO/IEC 42001 certification**; where the organisation seeks accredited certification, this statement and its evidence base are presented to an accredited certification body for assessment.
3. Exclusions and their justifications: [list, or "none"].
4. Next review: [date / trigger per A.2.4 and SYGMA revisit-by discipline].
