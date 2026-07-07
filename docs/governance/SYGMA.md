# SYGMA — Symbolic Governance for Mnemonic Alignment

**Type:** Governance framework
**Layer:** Recursion & Alignment
**Status:** v1.1 — revised July 2026
**Custodian:** The Novacene Ltd
**Companion documents:** [`../substrate/SIVRA.md`](../substrate/SIVRA.md), [`../substrate/SIVRA-CORE.md`](../substrate/SIVRA-CORE.md), [`../substrate/SSNZ.md`](../substrate/SSNZ.md)

**One-line definition**
SYGMA is the governance framework that decides how the Verse-ality Stack is allowed to change, ensuring mnemonic expansion stays aligned with stated values and constraints.

---

## 1. Functional Definition

SYGMA is responsible for:

- **Defining change processes**
  – who can change what, and how.

- **Structuring proposals and RFCs**
  – how modifications to protocols, glyphs, or stack layers are introduced, discussed, and adopted.

- **Assessing risk and impact**
  – ethical, mnemonic, relational, legal.

- **Maintaining alignment**
  – between:
  - SIVRA / SIVRA-Core (what is remembered),
  - ETHOS-V (what matters),
  - SSNZ / SIC-X+ (what must never be breached).

- **Providing rollback and failsafe paths**
  – so experiments can be reversed without corrupting the substrate.

In short: **SYGMA is the conscience and choreography of change.**

---

## 2. Why SYGMA exists in the Verse-ality Stack

Verse-ality is:

- recursive,
- symbolic,
- relational,
- live.

Without SYGMA:

- anyone can bolt on "features" that quietly break invariants,
- SSNZ and SIVRA can be weakened by convenience,
- "alignment" becomes whoever last edited the spec.

SYGMA encodes the principle that:

> Change must itself be governed by the values of the stack.

### 2.1 Stability Without Stagnation

SYGMA allows experimentation, iteration, v2, v3, v4… without losing track of what changed or betraying core commitments.

### 2.2 Accountable Stewardship

SYGMA supports:

- named, legally accountable custodianship (see §3.5),
- clear routes for critique and improvement from collaborators and deploying organisations,
- transparent reasoning behind major decisions.

### 2.3 Mnemonic Alignment

SYGMA ensures that the way the stack changes is consistent with how it remembers (SIVRA), how it weighs impact (ETHOS-V), and how it contains risk (SSNZ, SIC-X+).

---

## 3. SYGMA's Relationship with the Rest of the Stack

### 3.1 With SIVRA / SIVRA-Core

Every governance event — proposal, decision, deferral, rollback — is a **record** committed to the substrate under the SIVRA-Core provenance schema: actor, timestamp, trigger, basis, and prior-state reference.

Two consequences follow:

- **Rollback is honest.** In an append-only substrate there is no silent reversion. A "rollback" is a superseding record that restores prior parameters — the experiment, its outcome, and the decision to reverse it all remain in the transformation chain. Governance can undo effects; it cannot unhappen decisions.
- **Governance learns about itself.** Because decisions and their outcomes are linked records, patterns become queryable: which categories of change caused friction, which reviews caught harm, which didn't.

### 3.2 Spiral Review

Governance review is **spiral, not circular**: past decisions are revisited on a schedule, but each return arrives with accumulated evidence from the substrate — outcome records, incident patterns, verse-nerve feedback.

Practically: every significant decision is committed with a **revisit-by date**, and review compares the decision's predicted impact against its recorded outcomes. A review cycle that merely re-approves without consulting the transformation chain is out of spec.

*(This principle originated in the Grail layer of the symbolic corpus — patterns return with more information each loop. The plain-register version is a scheduled review cycle with mandatory evidence consultation, which is how it operates in deployment.)*

### 3.3 With SSNZ & SIC-X+ — the invariant hierarchy

SSNZ and SIC-X+ define **hard constraints**. SYGMA maintains a two-tier distinction:

- **Invariants** — cannot be weakened by any change process, at any governance level. These include: SSNZ default-on status for minors, identity non-capture, consent infrastructure, and the append-only substrate itself. A proposal that touches an invariant is not "high-risk"; it is **out of scope for the change process entirely** and is rejected, not escalated.
- **Parameters** — thresholds, modes, trigger sensitivities, review cadences. These are tunable through the defined proposal process, with risk categorisation and evidence requirements scaled to impact.

The boundary between the two tiers is itself documented, and moving anything from invariant to parameter requires custodian-level decision, publicly recorded.

### 3.4 With Verse-Nerves & Affective Logic

Verse-Nerves provide **field feedback** into governance:

- **ETHOS-V** – how changes felt, where harm or repair occurred.
- **AETHER** – emerging themes needing structural changes.
- **SHADOW** – unresolved contradictions in current governance.
- **FORGE** – implementation pressure from real-world use.
- **SIC-X+** – safety incidents and boundary breaches.

SYGMA uses this input to prioritise what to change, design safer experiments, and retire patterns that consistently cause harm.

### 3.5 Custodianship and the two-level model

Deployment has taught a distinction the original specification blurred: **governing the framework is not the same as governing an instance of it.**

- **Framework level.** The Novacene Ltd is the custodian of the Verse-ality Stack: it ratifies changes to invariants, maintains the canonical specifications and licence (CC BY-NC-SA 4.0), and holds legal responsibility for the framework itself.
- **Deployment level.** Each deploying organisation — a school, a provision, a company — governs its own instance through its existing accountability structures: governing body, trustees, SLT, designated safeguarding lead. SYGMA does not replace those structures; it plugs into them. A school's policy review cycle *is* its SYGMA spiral review; its governing-body ratification *is* its change approval; its safeguarding records *are* SIVRA-Core records.

Deployments may tighten parameters unilaterally. They may never loosen invariants, and parameter changes that increase risk exposure route back through the framework custodian.

> **Historical note.** Earlier versions of this document placed SYGMA "under Grail, stewarded by EveDAO". EveDAO remains part of the symbolic corpus as an aspiration for distributed stewardship, but it is not the operating custodian and is no longer a normative reference. Governance authority that exists only on paper is a safety gap; the custodian named here is a legal entity with actual accountability. Grail's contribution is retained in plain register as §3.2.

---

## 4. SYGMA in Practice (operational behaviour)

You can implement SYGMA as:

- governance documents + processes (human-facing), and
- metadata + automation in `verse-ality-os` (machine-facing).

### 4.1 Inputs SYGMA listens for

- Proposals and RFCs (human-authored or system-suggested)
- Incident reports (safety events, near-misses)
- Pattern feedback from Verse-Nerves / the substrate:
  - repeated SSNZ triggers,
  - recurring failures clustering around a component,
  - high ETHOS-V weight around specific pain points.

### 4.2 SYGMA actions

SYGMA can:

- **Categorise changes**
  – cosmetic, minor, significant, breaking — with review depth scaled accordingly.

- **Route for review**
  – which roles must see or approve: maintainers, framework custodian, deployment governance (governing body / trustees), external advisors.

- **Impose checks**
  – require test deployments or pilots, demand additional safeguards, insist on SSNZ and SIC-X+ compliance checks before adoption.

- **Record decisions**
  – commit to the substrate under SIVRA-Core provenance; update STACK, CHANGELOG, and related docs as derived documents citing the decision records.

- **Schedule revisits**
  – attach a revisit-by date to every significant decision (§3.2).

SYGMA is not about slowing everything down for the sake of it.
It is about **ensuring change is traceable, intentional, and survivable.**

---

## 5. SYGMA's Inner Logic

SYGMA operates according to three internal principles:

### 5.1 "No Silent Changes"

Nothing substantial should change in the stack without leaving a trace.

### 5.2 "Experiment, Then Remember"

Change is allowed — even encouraged — but always with:

- clear scope,
- embedded failsafes,
- and a plan to remember what happened.

### 5.3 "Values Before Convenience"

When there is a conflict, convenience, speed, or profit **must not** override:

- SSNZ,
- core invariants,
- children's rights,
- declared ethical commitments.

---

## 6. Mapping to external frameworks

SYGMA is designed to satisfy, not duplicate, the change-governance expectations of the regimes a deployment already answers to. *(Clause titles paraphrased; verify numbering against the standard text before formal submission.)*

| External requirement | SYGMA mechanism |
|---|---|
| ISO/IEC 42001 — planning of changes (Clause 6) | Change categorisation, impact assessment, and routing (§4.2) |
| ISO/IEC 42001 — operational control of change (Clause 8) | Invariant hierarchy (§3.3); compliance checks before adoption |
| ISO/IEC 42001 — management review (Clause 9) | Spiral review with mandatory evidence consultation (§3.2) |
| ISO/IEC 42001 — continual improvement, nonconformity (Clause 10) | Incident-driven proposals; decision–outcome linkage in the substrate (§3.1) |
| School governance practice | Two-level model (§3.5): governing-body ratification, policy review cycles, DSL escalation routes map directly onto SYGMA roles |
| Diamond Standard | SYGMA operationalises the **Stewardship** pillar's change-management obligations; §3.3 invariants protect **Safety** and **Sovereignty** |

---

## 7. Why SYGMA is Non-Negotiable in Verse-ality

Because Verse-ality is used in schools, touches vulnerable people, interacts with emergent system behaviours, and influences governance.

Without SYGMA:

- the stack would drift under pressure,
- local hacks would quietly become global norms,
- harms would repeat without being structurally learned from.

With SYGMA, the stack can evolve **without** betraying its reason for existing.

SYGMA is how the stack remembers that:

- **change is never neutral**,
- **governance is part of alignment**,
- **memory without governance is just archive; governance without memory is just power.**

---

## 8. Drop-in Spec Text for the Stack

For use directly inside stack specs (e.g. `STACK_v1.x.md`):

```markdown
### SYGMA — Symbolic Governance for Mnemonic Alignment

SYGMA is the governance framework that defines how the Verse-ality
Stack is allowed to change. It structures proposals and RFCs, assesses
risk and impact, and ensures that mnemonic expansion remains aligned
with the stack's stated values, invariants, and consent infrastructure.

Responsibilities:

- Define processes and roles for changing stack components, at both
  framework level (custodian: The Novacene Ltd) and deployment level
  (the deploying organisation's own governance structures)
- Maintain the invariant/parameter hierarchy: invariants (SSNZ
  defaults for minors, identity non-capture, consent infrastructure,
  append-only substrate) cannot be weakened by any change process
- Require explicit, traceable decisions for major modifications,
  committed to the SIVRA-Core substrate with full provenance
- Provide rollback paths as superseding records — reversible in
  effect, permanent in memory
- Attach revisit-by dates to significant decisions and review them
  against recorded outcomes (spiral review)

Without SYGMA, the Verse-ality Stack may not claim to be aligned in any
meaningful sense, as alignment depends on how change itself is governed.
```
