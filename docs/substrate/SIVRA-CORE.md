# SIVRA-Core

**Status:** Draft v0.1 · Plain register
**Companion document:** [`SIVRA.md`](./SIVRA.md) (symbolic register — philosophical source)
**Maintainer:** The Novacene Ltd
**Licence:** CC BY-NC-SA 4.0

---

## 1. Purpose

SIVRA-Core specifies a **record substrate** for AI-augmented organisations: an append-only, provenance-rich memory layer in which change is recorded as transformation rather than erasure.

This document is the auditor- and commissioner-facing expression of the SIVRA substrate. It contains no symbolic notation. The glyphic vocabulary in the companion document is a compression layer over the commitments defined here; it is notation, not mechanism. Nothing in this specification depends on it.

SIVRA-Core is written to serve two compliance surfaces simultaneously:

1. **ISO/IEC 42001:2023** — as an implementation pattern for documented information, event logging, and data provenance requirements within an AI management system (AIMS).
2. **UK education safeguarding practice** — as a formalisation of the record-keeping discipline already required of schools and alternative provision (KCSIE, statutory chronologies, retention duties).

The claim of this specification is deliberately narrow: organisations deploying AI systems in high-trust contexts need a memory substrate with these properties. It does not claim more.

---

## 2. Definitions

| Term | Meaning |
|---|---|
| **Record** | A structured, typed unit of information committed to the substrate (an event, decision, assessment, observation, or state change). |
| **Substrate** | The append-only store holding all records and their provenance metadata. |
| **Transformation** | Any change to organisational state. Transformations are *recorded*; prior states are never overwritten. |
| **Provenance metadata** | The mandatory who / what / when / why / prior-state attached to every record. |
| **Tombstone** | A record marking that another record's *content* has been lawfully redacted, while preserving the fact, time, and reason of redaction. |
| **Derived narrative** | Any human-readable account (report, summary, chronology view) generated *from* records. Narratives are outputs of the substrate, never inputs to it. |

Requirement keywords (**MUST**, **SHOULD**, **MAY**) follow RFC 2119 usage.

---

## 3. Core commitments

The substrate rests on three commitments. Each has a plain engineering expression and an operational rationale drawn from safeguarding practice, where this discipline has been load-tested for decades.

### 3.1 Non-destructive record-keeping

> *Nothing meaningful is lost.*

- The substrate **MUST** be append-only. Records, once committed, are immutable.
- Correction is performed by appending a superseding record that references the record it corrects. Both remain retrievable.
- Deletion of content, where legally required (see §6), is performed by tombstoning — never by silent removal.

**Rationale.** In safeguarding, a record is never deleted because its significance may only become apparent years later, in a pattern no single author could see. The same logic applies to AI system decisions: an output that seemed unremarkable at the time may be the critical evidence in a later incident review or impact assessment.

### 3.2 Provenance of transformation

> *Change is vector, not noise.*

Every record **MUST** carry provenance metadata:

- **Actor** — the human, system, or agent that committed the record (agents identified per-instance, never as a pooled identity).
- **Timestamp** — committed time, from a trusted clock.
- **Trigger** — what occasioned the record (user action, scheduled process, escalation, upstream record).
- **Prior state reference** — for any record that supersedes, corrects, or evolves another, an explicit link to its predecessor(s).
- **Basis** — for decisions: the policy, assessment, or authority under which the action was taken.

The substrate therefore forms a **directed graph of transformations**, not a flat log. The trajectory of a record — how a concern, assessment, or system behaviour *evolved* — is a first-class queryable object.

**Rationale.** A safeguarding chronology is valuable precisely because it captures direction and velocity of change, not just current state. Likewise, ISO/IEC 42001 impact assessment and continual improvement processes require knowing not only *what* an AI system did but *how its behaviour changed over time* and *what changed it*.

### 3.3 Structure before story

> *Records are structured; narrative is derived.*

- Records **MUST** be typed and structured at the point of capture (event type, subjects, facts, actions, outcomes as discrete fields).
- Free-text narrative **MAY** be attached to a record but **MUST NOT** be the record's only content.
- Reports, summaries, and chronology views are *derived* from records and **MUST** cite the record identifiers they draw on. A derived narrative is itself committed as a record, with provenance.

**Rationale.** Narratives get rewritten; the people who wrote them move on; memory drifts. Structured facts with dates, actors, and actions survive their authors. This is standard safeguarding instruction ("record facts and actions, not opinions and stories") elevated to an architectural rule. It also directly mitigates a known AI failure mode: a model summarising its own history will confabulate unless the summary is anchored to citable structured records.

---

## 4. Architectural requirements

An implementation of SIVRA-Core:

1. **MUST** provide an append-only event store with immutable records and monotonic ordering.
2. **MUST** enforce the provenance schema (§3.2) at write time — a record lacking mandatory provenance fields is rejected, not accepted-and-flagged.
3. **MUST** support supersession links, so that the current state of any entity is computed as the head of its transformation chain, with the full chain retrievable.
4. **MUST** distinguish record classes with differing retention and access rules (e.g. safeguarding, operational, AI-system event logs) at the schema level.
5. **MUST** log AI system involvement explicitly: where a record was generated, drafted, or influenced by an AI system, the system, version, and prompt/policy context **MUST** be captured in provenance. Human review or approval, where it occurred, is itself a record.
6. **SHOULD** make emergence visible: queries over the transformation graph (frequency, clustering, cross-record patterns) are a supported operation, because patterns across records are where meaning that "no single author could see" becomes detectable.
7. **SHOULD** support cryptographic integrity (hash-chaining or equivalent) so that the absence of tampering is demonstrable to an auditor, not merely asserted.
8. **MAY** implement the substrate on any storage technology (relational, document, ledger); the commitments are architectural, not vendor-specific.

---

## 5. Mapping to ISO/IEC 42001:2023

SIVRA-Core is designed as an implementation pattern for the following AIMS requirements. *(Clause and control titles paraphrased; verify numbering against the purchased standard text before formal submission.)*

| ISO/IEC 42001 area | Requirement (paraphrased) | SIVRA-Core mechanism |
|---|---|---|
| Clause 7.5 — Documented information | Creation, updating, and control of documented information; protection against loss of integrity | Append-only substrate; supersession chains; write-time schema enforcement (§3.1, §4.2) |
| Clause 8 — Operational planning and control | Control of planned changes; review of unintended changes | Transformation graph makes both planned and unintended change queryable with full provenance (§3.2) |
| Clause 9 — Performance evaluation | Monitoring, measurement, analysis; retention of evidence | Derived narratives with record citation (§3.3); emergence queries (§4.6) |
| Clause 10 — Improvement | Nonconformity and corrective action records | Corrections as superseding records — the nonconformity and its remediation are permanently linked (§3.1) |
| Annex A — AI system event logging | AI systems record event logs of operation | §4.5: AI involvement captured in provenance per record |
| Annex A — Data provenance | Provenance of data used by AI systems is documented | Provenance schema is mandatory, not optional metadata (§3.2) |
| Annex A — AI system impact assessment | Impact assessments documented and maintained | Assessments are records in the substrate; their evolution is a transformation chain, giving auditors the assessment *history*, not just its latest version |
| Annex A — Technical documentation | Documentation across the AI system life cycle | Life-cycle documents live in the substrate under §3.1 rules — no silent version replacement |

**Sector-specific note (education).** For an education deployment, the substrate's record classes (§4.4) align the AIMS with existing statutory duties: the safeguarding record class inherits KCSIE-consistent retention and access rules, so the organisation runs *one* memory discipline satisfying both the AI management system and safeguarding inspection, rather than two parallel regimes.

---

## 6. Lawful redaction: the tombstone protocol

Append-only storage must coexist with data protection law. SIVRA-Core resolves the apparent conflict as follows:

- Where a UK GDPR erasure request (or equivalent obligation) applies and no exemption holds, the record's **content** is redacted and replaced by a **tombstone** carrying: the record identifier, the fact of redaction, the lawful basis for redaction, the actor authorising it, and the timestamp. The transformation graph remains intact; the content does not.
- Where an exemption applies — notably safeguarding records, which are retained under statutory and local-authority guidance irrespective of erasure requests — the exemption relied upon **MUST** be recorded as the basis field of a retention decision record.
- Tombstoning is itself a transformation with full provenance. An auditor can always see *that* something was removed, *when*, *by whom*, and *on what basis* — without seeing what it was.

This preserves the first commitment honestly: what is protected from loss is *meaning and accountability*, not raw data in defiance of law.

---

## 7. Existing implementations and framework relations

- **Reference implementation:** the Nudge Education risk assessment system (NOOMA) operates versioned risk assessments with a standing layer, dependency graph, and certification states that change without erasing their history — a working instance of §3.1–3.3 in a live education context.
- **Diamond Standard:** SIVRA-Core is the record-keeping expression of the **Stewardship** pillar, and supplies the evidence base on which the Safety, Sovereignty, and Symmetry pillars are auditable.
- **Verse-ality agent infrastructure:** consent gates and policy contracts (SSNZ, VerseLang patterns) generate events; SIVRA-Core is where those events are durably held. The two are complementary: one governs action, the other governs memory.

## 8. Out of scope

SIVRA-Core does not specify: the symbolic notation layer (see companion document), user interface, storage vendor, or cryptographic algorithm choices. It does not claim that this substrate produces intelligence, coherence, or emergence — only that it makes organisational memory non-destructive, attributable, and auditable, which is the precondition for detecting those things if they occur.

---

*Changes to this specification are themselves recorded as superseding versions. Practise what you specify.*
