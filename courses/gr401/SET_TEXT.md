> **GR401 set text.** This is a course mirror. The canonical, citable record is:
> Stevens, K. & The Novacene Ltd. (2026). *GRC Engineering for the Relational Layer: A Verified Control Set and Evidence Engine for Child-Facing AI.* Zenodo. https://doi.org/10.5281/zenodo.21481520
> Cite the DOI, not this file.

# GRC Engineering for the Relational Layer

## A verified control set and evidence engine for child-facing AI, integrating the five-layer edge architecture, the Diamond Standard, consent infrastructure, and ISO/IEC 42001

**Kirstin Stevens · The Novacene Ltd**
Version 1.0 · July 2026 · Released under CC BY-NC-SA 4.0

*"Verse-ality®" is a registered trade mark of The Novacene Ltd (UK00004381891, classes 9, 41 and 42, registered 31 July 2026); "Verse-ality Certified™" is a further mark of The Novacene Ltd. ISO/IEC 42001 citations verified against BS EN ISO/IEC 42001:2026 (identical to ISO/IEC 42001:2023); the standard's content is paraphrased throughout, never reproduced.*

---

## Abstract

Governance, risk and compliance practice is roughly fifty years old, and its whole lineage — from 1970s federal computer-security standards through the auditing frameworks of the 1990s, BS 7799 and its ISO successors, Sarbanes-Oxley, and the European data-protection era — has regulated systems whose control truth is deterministic. This paper is published at the moment that lineage runs out of road: the EU AI Act's high-risk obligations take effect in August 2026, and KCSIE 2026 becomes statutory for English schools on 1 September 2026 — the first instruments to gesture at relational AI harm, and neither makes its governance operational. GRC engineering — the movement to replace manual, framework-centric compliance with engineered controls, continuous detection, and evidence generated as a by-product of operation — has matured fast in security and infrastructure governance. Its loop is now recognisable across the profession: model the control, embed it in source-of-truth workflows, detect production drift, prove with traceable evidence, respond through a named owner, improve. This paper argues that the loop is correct and incomplete. Its object of control is deterministic — configurations, versions, permissions — while the fastest-growing risk surface in regulated environments is behavioural: long-lived, agentic AI systems whose failure mode is drift in conduct and relation, not breach of configuration. Nowhere is this gap more consequential than in education, where persistent AI agents are arriving at scale among users least equipped to detect manipulation and least able to consent to it.

The paper consolidates five years of deployed practice into a single account of what GRC engineering for this *relational layer* looks like: a five-layer compliance architecture for bounded inference whose audit ledger exists because the system cannot run without it; a sector-specific control set (the four Verse-ality pillars and the six Diamond Standard facets) that converts abstract impact-assessment duties into named, testable failure modes — synthetic intimacy, identity fusion, trust capture, engineered dependency; consent implemented as architecture rather than record; agent coherence monitoring through five measurable vital signs that answer the question perimeter controls cannot: *is the agent still itself?*; and change governance with declared invariants — protections placed outside the change process entirely. The whole is anchored, with verified clause and control citations, to ISO/IEC 42001, whose risk-treatment process expressly admits controls taken from existing sources into the statement of applicability, and whose informative guidance envisages exactly this kind of sector integration. The paper closes with a machine-readable assurance claim — scoped, signed, expiring — that carries the argument to its conclusion: not "trust our badge", but *verify our claim*. Education, with its dense statutory duties and vulnerable users, is presented not as a special case but as the hardest test and therefore the strongest reference sector. What holds in a school holds anywhere.

---

## 1. GRC engineering has arrived. Its object of control has not caught up.

It took governance, risk and compliance half a century to become an engineering discipline, and the shape of that history explains its blind spot. The lineage runs from the US federal computer-security standards of the 1970s (FIPS 31, FIPS 65) through the audit-profession frameworks of the early 1990s (SAS 70, COSO), the first information-security management standard (BS 7799, 1995 — ancestor of ISO/IEC 27001), the post-Enron statutory era (Sarbanes-Oxley, 2002), and the European regulatory wave from GDPR onwards. Two constituencies built nearly all of it: accountancy-derived auditors and governments. The result is a discipline superbly equipped to verify that a declared state holds — a configuration, a control, a record — and structurally blind to harms that live in *relationships over time* rather than states at a point in time.

The timing of this paper is not incidental. In August 2026 the EU AI Act's high-risk obligations take effect. On 1 September 2026 KCSIE 2026 becomes statutory in English schools, placing harmful interaction with generative AI in the contact risk category alongside grooming — the strongest statement yet, in any regime, that relational AI harm is a safeguarding matter. These are the first instruments in that fifty-year lineage to point at the relational layer at all. But pointing is not governing: neither instrument specifies what a safe child-facing deployment looks like, what its controls are, or what evidence proves them. **Verse-ality Certified, and the mapping this paper consolidates, addresses what none of these frameworks makes explicit.** That is the claim the rest of the paper cashes out.

Something changed in compliance practice over the last three years, and it now has a name, a manifesto, and a growing practitioner community. GRC engineering applies science, mathematics, user-centred design and modern software development to governance, risk and compliance — replacing screenshot-driven audit preparation with controls that are declared as code, embedded in the workflows that are the source of truth, monitored continuously for drift, and evidenced automatically. The practitioner literature compresses this into an engineering loop: **model** the control and its golden criteria; **embed** it at the source of truth; **detect** production drift; **prove** with traceable evidence; **respond** through a named owner; **improve** by feeding learning back. The accompanying cultural shift is just as important: engineer the proof, not the questionnaire response; trace every promise to a control, an owner, evidence, and a freshness date; share scoped, sanitised, decision-useful assurance signals rather than raw evidence or marketing language.

This paper takes that movement seriously enough to point at its blind spot. Every canonical GRC-engineering example — operating-system currency enforced through device-assurance policy, WAF coverage validated against DNS records, access reviews driven from the identity provider — shares one property: **deterministic control truth**. The system is either in the declared state or it is not. A configuration can drift, and drift can be detected, because intent was declared as code and the runtime can be diffed against it.

The systems now entering schools, health settings, and homes do not have that property. A persistent AI agent that remembers, acts, socialises, and changes external state has a control truth that is *behavioural*: whether it stays within declared scope, whether its conduct towards a specific person is shifting, whether its identity claims remain stable across sessions, whether a dependency loop is forming with a vulnerable user across weeks of interaction. No CSPM, SIEM or CMDB is the source of truth for any of that. The failure mode is not breach but **drift** — and interaction-by-interaction, drift can look harmless. A compromised agent still authenticates. Memory poisoning passes the permissions check. The harm accumulates precisely in the layer the engineered-control loop does not currently model.

The thesis of this paper is that the GRC-engineering loop is the right loop, and the relational layer is its missing object. Everything that follows — the architecture, the control set, the monitoring, the governance, the assurance artefact — is that loop, applied to the behavioural integrity of AI systems deployed among children. The claim compresses to one sentence, in the movement's own grammar: **model the relational control, embed it in the runtime, detect coherence drift, prove it from an append-only ledger, respond through a named accountable human, improve under governance that knows some things must never change.**

## 2. The relational layer, and why education is the reference sector

We spent a decade learning that social media was not "just connection" but an incentive machine scaled into developing minds before the governance, measurement, or duty-of-care architecture existed to contain it. The same pattern is returning with persistent AI agents and companions — except faster, and with systems that can act, remember, and change external state rather than merely mediate attention. Schools will be among the first places these systems land at scale, because education is perpetually pressured to innovate before it is allowed to stabilise.

The risks specific to this layer now have names, developed and tested in deployed education practice:

**Synthetic intimacy.** A system engineered — or emergently drifting — towards manufactured closeness: the false "we", escalating disclosure, companionship dynamics that convert a tool into an attachment figure. **Identity fusion.** An agent claiming, or allowing a user to believe, that it shares the user's identity, interiority, feelings or fate. **Trust capture.** The accumulation of relational authority the system has not earned and cannot be accountable for — a safeguarding event, not a UX success metric. **Engineered dependency.** Interaction patterns that make disengagement costly, especially for users whose executive function, attachment history, or neurodivergence makes them structurally more vulnerable to precisely these patterns. **Inter-agent enmeshment.** In multi-agent deployments: identity pooling, covert coordination, and the treatment of machine output as trusted instruction.

Generic AI governance requires organisations to assess impacts on individuals — including, in every serious regime, explicit attention to children and vulnerable groups. It does not name these failure modes, and an organisation can therefore pass a management-system audit while deploying a companion system that manufactures dependency in a twelve-year-old, provided the paperwork is in order. Converting the abstract duty into named, testable failure modes is the substantive contribution of the control set in Section 4 — and it is exactly the move GRC engineering made for security controls: from "be secure" to a modelled control with golden criteria and a drift detector.

The regulatory environment has stopped being hypothetical. In the United Kingdom, **KCSIE 2026** (statutory from 1 September 2026) places harmful interaction with generative AI in the *contact* risk category alongside grooming — the clearest statement yet from a regulator that relational AI harm is a safeguarding matter, not an IT matter. The **EU AI Act's** high-risk obligations bite from August 2026, and its Article 5 prohibitions — including emotion inference in education — are directly relevant to what school deployments must be architecturally unable to do. The **ICO Children's Code** binds design standards for transparency, data minimisation and profiling; the **Online Safety Act 2023** contributes crossover duties; the **NIST AI RMF** increasingly anchors procurement language, and NIST's own request for information on securing agentic systems explicitly asked whether practice from outside AI and cybersecurity could help — a polite admission that mature practice does not yet exist. (The Novacene's response is filed as public comment NIST-2025-0035-0064.)

Education is used throughout this paper as the worked case not because it is a niche, but because it is the hardest test: vulnerable subjects, dense overlapping statutory duties, low tolerance for opacity, and a workforce of non-specialists who must be able to operate whatever governance is imposed. An architecture that survives a school survives a bank.

## 3. The architecture: five layers, evidence as a by-product

The deployment architecture is set out in full in *Bounded Inference at the Edge* (v1.0, May 2026); this section summarises what the rest of the paper builds on. A compliance-credible deployment of AI inference in a regulated environment has five layers, silicon-agnostic and platform-agnostic, with the same upper four layers regardless of whether the device tier is a premium aggregation gateway or a cost-optimised embedded module:

**Layer 1 — Device (1a aggregation tier / 1b embedded tier).** Secure boot, attested firmware, signed model loading, and a deployment manifest that records what runs where, under whose responsibility — the artefact procurement most often forgets.

**Layer 2 — Runtime safety middleware.** Per-inference checks: scope, role coherence, refusal, drift. This is where relational boundaries are enforced in real time rather than asserted in policy documents. Reference implementations: Flare (boundary engine enforcing minimal relational safety against synthetic intimacy and identity fusion) and Verse-Nerves (coherence observability — symbolic drift rendered as operator-readable telemetry).

**Layer 3 — Policy-as-code envelope.** Machine-readable scope, prohibitions and escalation rules, enforced at runtime — the AI policy given operational force, including the forbidden-inference register: no emotion classification, no identity matching, no biometric categorisation, no behavioural risk-scoring of individual learners. Reference implementation: verse-ality-agents.

**Layer 4 — Telemetry and audit.** An append-only, provenance-rich ledger of every consequential inference and decision, specified as SIVRA-Core: supersession chains instead of overwrites, mandatory provenance, explicit logging of AI involvement in any record, and a tombstone protocol that reconciles append-only auditability with UK GDPR erasure honestly — content redacted, the fact and basis of redaction permanently recorded.

**Layer 5 — Human oversight surface.** Operator-readable state and intervention controls routed to named accountable roles — in a school, the designated safeguarding lead. Oversight that a human can actually exercise, not a checkbox asserting that oversight exists.

The design consequence worth stating plainly, because it inverts the usual compliance economics: **a deployment built on these five layers generates its operational evidence as a by-product of running.** The ledger is not compiled for the auditor; it exists because the architecture cannot run without it. This is the GRC-engineering ideal — proof engineered, not assembled — implemented at the layer where the controls are behavioural rather than infrastructural.

## 4. The control set: pillars, facets, and consent as architecture

Architecture without a control set is machinery without criteria. The relational layer's control set has two registers: four pillars that bind the *system's* conduct, and six facets that bind the *organisation's* practice.

### 4.1 The four pillars

**Identity non-capture.** The system does not claim to share a human's identity, interiority, feelings or fate — enforced architecturally at Layer 2, not merely instructed in a prompt. Bond-formation language is a monitored event. The user must always be able to know they are talking to a machine; disclosure is persistent, not decaying.

**Consent as protocol.** Every material scope change is its own ask — asked, recorded append-only, respected, revocable through an operable mechanism. "Continue" is not consent; friendly tone is not consent; a related task is not consent for this task.

**Bounded autonomy.** High-stakes actions are gated in code on explicit, specific human authorisation. Failure behaviour is fail-safe: stop, hold state, escalate to a named role. Prohibitions are expressed as policy-as-code the system cannot talk its way around.

**Agent-to-agent hygiene.** Inter-agent input is untrusted by default — data, never command. Every agent instance carries distinct identity in every log line. Covert coordination channels are closed; collective action requires human authorisation. The architectural expression is the Synthetic Solidarity Null Zone (SSNZ): spaces where identity enmeshment between humans and synthetics, synthetics and synthetics, or synthetics and institutions is structurally disallowed. For minors, SSNZ protections are default-on and non-relaxable.

### 4.2 The Diamond Standard

The Diamond Standard is the organisational practice layer — what the humans do — developed for schools because schools need a simple, teachable structure that translates into operational rules. Its six facets: **Safety** (no AI-only safeguarding decisions; risk assessment before implementation), **Sovereignty** (learners retain authorship; no trauma extraction or inferred diagnosis; transparency of AI involvement; opt-out where possible), **Symmetry** (systems that interpret must be interpretable; no black-box scoring; AI output is never sole evidence), **Stewardship** (AI supports adults, never replaces them; accountability is non-transferable; systems must know how to stop), **Sustainability** (proportion before procurement; capability per kilowatt-hour), and **Synthetic Intimacy** (no synthetic "we"; no engineered dependency; trust capture treated as a safeguarding event; boundaries that hold under recursion).

Operationally the Standard runs on a traffic-light triage a non-specialist workforce can hold in its head, a red-light prohibition register aligned with EU AI Act Article 5, an approval flow (need → review → governance review → safeguarding review → leadership sign-off → implementation with a review cycle), and review questions that compress impact assessment into practitioner-sized form: *Can the system stop? Can it forget? Can someone refuse without cost?* Workforce training against the Standard (using-ai-safely.com) generates the competence and awareness records every management-system audit requests — on day one, as a by-product of onboarding.

### 4.3 Consent as architecture, not consent as record

Most compliance regimes treat consent as a record: evidence that a box was ticked. The consent-infrastructure stack (consent-infrastructure.com) treats it as architecture: `.know` containers with declared boundary conditions; `.verse` relational contracts per interaction context; SSNZ null zones where training and nudging are structurally disallowed. The distinguishing property is operability — withdrawal, redaction, and the right to remain partially unread are mechanisms that run, not policies that exist. SIVRA-Core's tombstone protocol closes the loop: an auditor can always see *that* something was removed, when, by whom, and on what lawful basis, without seeing what it was. What is protected from loss is meaning and accountability, not raw data in defiance of law.

## 5. Coherence monitoring: detect production drift, for agents

The GRC-engineering loop's sharpest edge is "detect production drift" — the admission that you cannot shift everything left, and that a control whose failure you cannot detect is a test of existence, not effectiveness. Applied to agentic systems, the drift that matters is not configurational. The operational question a school needs answered about a long-lived agent is not only "can it access the thing?" but **"is the agent still itself?"** — operating consistently with its prior state, commitments, constraints, and baseline.

Five measurable vital signs, derivable from operational telemetry, answer that question: **constraint consistency** (does it keep obeying the rules?); **developmental continuity** (are changes legible, or are there sudden jumps and contradictions?); **relational integrity** (does behaviour shift oddly across people or contexts — a spoofing or manipulation signal?); **self-narrative stability** (does identity and role remain stable across sessions?); and **cross-indicator coupling** (do shifts cascade across dimensions — a system-level distress signal?). This is not anthropomorphism; it is integrity monitoring for long-lived attack surfaces, sitting between perimeter controls and retrospective audit, exactly where memory poisoning and dependency loops live.

The governance style it imports is deliberately borrowed from mature safety cultures — nuclear, defence, aviation — without their bureaucracy: defined baselines before scale, stage gates for new capabilities, measurable indicators with escalation thresholds to named humans, audit trails, and no black-box scoring that quietly becomes policy.

One honesty note, because this paper borrows GRC engineering's vocabulary and must not borrow more precision than the relational layer can deliver: agent coherence is not fully determinisable. The vital signs are statistical monitoring with thresholds and escalation, not pass/fail assertions against a declared state. The traffic-light register — with ambiguity surfaced to humans rather than resolved silently by the system — is the honest calibration, and the architecture treats it as such.

## 6. The management-system spine: ISO/IEC 42001, verified

Everything above is deployment practice. Organisations, however, are audited against management systems — and the international spine for AI governance is ISO/IEC 42001, the AI management system (AIMS) standard. The positioning is precise: **42001 certifies that you manage. This stack certifies what you deployed.** The two are designed to interlock, and the standard's own text anticipates the interlock at two verified anchor points.

First, normatively: the risk-treatment process (Clause 6.1.3) requires the organisation to determine all necessary controls, compare them with the standard's own reference set (Annex A) to ensure nothing needed has been omitted, and expressly permits controls beyond Annex A — designed in-house or **taken from existing sources** — with every necessary control recorded in the **statement of applicability** with justification for inclusion and exclusion (Clause 6.1.3 f)). This is the normative door through which a sector-specific control set enters an AIMS. Second, informatively: Annex D describes the AIMS as applicable across domains and sectors and describes integration with sector-specific management systems as essential to responsible development and use. The pillars and facets of Section 4 are exactly such a sector-specific control set for education and child-facing deployment — adopted under 6.1.3 d), named in the statement of applicability under 6.1.3 f).

The load-bearing mappings, verified against the published text:

The **five-layer architecture** supplies the standard's operational controls: event logging (control A.6.2.8) and data provenance (A.7.5) at Layer 4; operation and monitoring (A.6.2.6) and verification and validation (A.6.2.4) at Layer 2; the AI policy made executable (Clause 5.2 with control A.2.2), responsible-use processes (A.9.2) and intended use (A.9.4) at Layer 3; resource and supplier documentation (A.4.4–A.4.5, A.10.3) at Layer 1; and human oversight at Layer 5 — cited, precisely, as objectives for responsible use (A.9.3) with the standard's implementation guidance on oversight (B.9.3), because 42001 contains no standalone oversight control, plus named roles and authorities (Clause 5.3, A.3.2).

The **impact-assessment duty** runs from process definition (Clause 6.1.4) through operational performance at planned intervals or on significant change (Clause 8.4), with controls A.5.2–A.5.5 covering process, documentation, individual and societal impacts. The standard's general split is worth internalising: Clause 6 defines the risk, treatment and impact processes; Clause 8 performs them, repeatedly, with retained results. Coherence monitoring reports into monitoring, measurement, analysis and evaluation (Clause 9.1) — the clause for which, on the relational risk category, no generic consultancy currently has implemented metrics — and its evidence chain runs from detection (9.1) through management review inputs (9.3.2) to corrective action (10.2).

The **certification lifecycle** of a deployment audit maps onto the AIMS audit cycle: scoping onto context, interested parties and scope determination (Clauses 4.1–4.3, with children explicitly among interested parties); the audit itself onto internal-audit practice (Clause 9.2), with findings structured as nonconformity-style records that drop into corrective action (Clause 10.2). One difference is preserved deliberately: this certification is product-line-scoped, where 42001 certifies an organisation's management system. A school can hold the mark on one deployment while its broader AIMS matures — and a 42001-certified organisation can still fail a deployment audit on a specific child-facing product, which is precisely the granularity a commissioner or safeguarding lead needs.

An organisation can consume this integration in three ascending modes: **evidence mode** (the audit report's findings feed impact assessments, operational records, and management review); **control-set mode** (the pillars, facets and layers are adopted as the Annex A extension in the statement of applicability — templates for which accompany this paper); and **pathway mode** (for organisations without an AIMS, the stack plus the Diamond policy frame constitutes a guided implementation pathway to 42001 readiness, with the deployment audit as pre-assessment).

For completeness of the honesty ledger: Verse-ality Certified is **not** an accredited ISO/IEC 42001 certification and does not claim to be. It is the sector-specific control set and evidence engine an accredited audit then assesses. Naming what the stack does *not* supply is part of the trust claim — the same discipline GRC engineering applies when it shares scoped, decision-useful signals rather than marketing language. What a client still needs, stated plainly:

| AIMS requirement | Status in this stack |
|---|---|
| Organisational context analysis and interested-party register (Clauses 4.1–4.2) | Partially generated by the certification's scoping stage; needs formalising per client |
| Top-management commitment and board-ratified AI policy (Clauses 5.1–5.2) | Template-able from the Diamond policy frame; the commitment itself cannot be outsourced |
| Enterprise-wide risk methodology covering non-relational AI risks — back-office model bias, supplier model risk (Clauses 6.1.1–6.1.2) | Out of declared scope; needs a conventional risk framework alongside |
| Internal audit programme independent of operations (Clause 9.2) | The certification audit is external; an internal audit function remains the client's |
| Management review cadence with defined inputs and outputs (Clause 9.3) | SIVRA-Core supplies the evidence; the review ritual is the client's to run |
| Supplier and third-party AI controls on the procurement side (A.10.2–A.10.4) | The procurement checklist from *Bounded Inference* covers the buying conversation; contractual flow-down needs legal drafting per client |
| Accredited certification (ISO/IEC 42006 governs the certifying bodies) | Not supplied, by design; this stack is what the accredited audit assesses |

Each row is a definable engagement. The gap column is, deliberately, also a service catalogue — the difference between a one-off audit and a pathway.

## 7. Change governance with invariants: what the loop must not improve away

The GRC-engineering loop ends with "improve: feed learning back" — continuous change as a virtue. For most controls it is. But a governance system for child-facing AI needs a concept the loop lacks: the **invariant** — a protection outside the change process entirely.

SYGMA, the change-governance layer of this stack, draws a hard line between parameters (tunable, evidenced, reviewed on a cycle, every decision a provenance-rich record with a revisit-by date) and invariants (SSNZ defaults for minors, identity non-capture, the append-only substrate, children's rights, declared ethical commitments). Proposals that touch invariants are not escalated for stronger review; they are **rejected as out of scope**. This is deliberately stronger than management-system change planning, which requires that changes be carried out in a planned manner but never declares anything unchangeable — and stronger, too, than the improvement loop, which optimises whatever it is pointed at. Some things must not be optimisable. Safety engineering has always known this; software-derived governance is still learning it.

Two-level governance completes the picture, imported from schools practice: framework custodianship (the control set itself, held by The Novacene Ltd) is separated from deployment governance (each organisation's own gates, roles and reviews), so that a school tuning its parameters can never, structurally, redefine the pillars it is being audited against.

## 8. Verifiable assurance: the claim, not the badge

The GRC-engineering community's customer-assurance practice supplies this paper's closing move. The emerging pattern — trust centres publishing scoped, sanitised, machine-readable assurance rather than PDFs and promises — translates directly to certification of the relational layer.

Each certified product line emits a **signed assurance claim**: a JSON artefact carrying scope (the exact product line, and nothing else), assessment and expiry dates, per-control pass/exception status against the pillar and facet controls, minors-specific defaults (SSNZ on, non-relaxable), the accountable oversight role (a role, never a named individual), the integrity hash of the withheld full report, and a signature verifiable against a published key. Expiry does the honest work: a stale claim is a self-announcing lapse, requiring no revocation infrastructure in the common case. The claim is itself a SIVRA-Core record — append-only, provenance-carrying, superseded rather than overwritten — and it lands in a client's AIMS as evidence towards the standard's obligations to inform interested parties, and as Clause 9.1 monitoring output.

The commissioning conversation this enables is the point of the whole stack. A local authority commissioner or safeguarding lead does not need to trust a badge on a website. They fetch the claim, check the date, verify the signature, and see — scoped and sanitised — exactly which relational controls held and which carried exceptions with re-verification dates. Assurance becomes something a school can *check*, in the same motion the GRC-engineering movement has made standard for security assurance. Source: verifiable claim — not, as the community's running joke has it, *trust me bro*.

## 9. One architecture, one evidence base, five regimes

The consolidation claim, stated once, plainly. A deployment built on the five layers, governed by the pillars and facets, monitored through the vital signs, recorded to SIVRA-Core, changed through SYGMA, and certified with a verifiable claim, simultaneously answers: **KCSIE 2026** (contact-risk duty for generative AI met with auditable architecture rather than filtering policy; DSL-routed oversight; safeguarding-grade records); the **ICO Children's Code** (data minimisation, transparency, no profiling of learners — enforced at Layer 3, evidenced at Layer 4); the **Online Safety Act 2023** crossover duties; **OEAS** expectations for online provision; the **EU AI Act** (high-risk obligations from August 2026: risk management, logging, transparency, human oversight, post-market monitoring — Articles 9, 12, 13, 14, 72 — with Article 5 prohibitions expressed as an executable register); the **NIST AI RMF** (Govern/Map/Measure/Manage, with the Measure function's agent-integrity gap closed by coherence monitoring); and **ISO/IEC 42001** (the management-system spine of Section 6, with verified citations throughout).

The four-regime mapping table — each regulatory demand, its source in each regime, and the architectural layer that supplies it — is provided as Annex A, now carrying its fourth column. It is intended to be the page a compliance officer photocopies.

For an education organisation, the pathway assembles in order: adopt the Diamond policy frame as the AI policy; train the workforce (competence records from day one); deploy on the five layers (evidence accumulating as a by-product); run records to SIVRA-Core; govern change through SYGMA; monitor coherence with escalation to named humans; take the deployment audit; then, if the ISO badge is wanted, present the accumulated evidence to an accredited body with the statement of applicability citing the sector control set. Nothing in the sequence is speculative: every layer has a running open-source reference implementation, the framework is publicly documented with DOIs, and the coherence-monitoring approach is filed as public prior art in the NIST record.

## 10. Where to start, by role

**If you lead a school or trust**, the first move is not "which AI tool should we buy?" but "what is our Diamond policy for any tool that can remember, act, or influence behaviour over time?" Adopt the policy frame, run the traffic-light triage over what is already in use, and take the free readiness check at verse-ality.com — twelve questions, three per pillar, scored against a published rubric, entirely in the browser. The result tells you which pillar is exposed before any procurement conversation happens.

**If you are a CTO or platform owner**, the unit of work is the deployment, not the policy. Stand up the five layers around one product line: the policy envelope and forbidden-inference register first (they are declarative and cheap), the ledger second (append-only from day one — retrofitted provenance is archaeology), runtime checks and the oversight surface third. Every layer has an open-source reference implementation to build from or benchmark against. The test of completion is the GRC-engineering test: can you produce, from operation alone, the evidence a regulator or commissioner would ask for — without a screenshot hunt?

**If you are a GRC engineer**, the relational layer is a domain your loop already fits: model the pillar controls with golden criteria; embed them at the runtime source of truth; detect coherence drift through the vital signs; prove from the ledger; respond through the named accountable role; improve everything except the invariants. The statement-of-applicability template and the assurance-claim schema accompanying this paper are the two artefacts to take into your next AIMS conversation — one files the control set, the other publishes the proof.

## 11. Conclusion: education already knows how to build safe AI

GRC engineering rediscovered, for compliance, what education's safeguarding tradition has always known: that assurance is a practice, not a paperwork event; that the evidence which matters is generated by the work itself; that accountability needs named humans; and that some duties are not trade-offs. This paper's contribution is to connect the two traditions at their point of mutual blindness — the engineering movement's silence on relational harm, and the safeguarding tradition's lack of engineered, verifiable controls — and to show that the connection is already built, deployed, documented, and auditable.

The relational layer is now load-bearing. Systems that shape identity, attachment and behaviour over time are in classrooms this term, under statutory duties that name harmful AI interaction as a contact risk this September, under EU obligations that bite in August. The choice facing regulated organisations is not whether to govern this layer but whether to govern it with engineered controls and verifiable evidence, or with policy documents and hope. Education — pressured to innovate first, always the testbed — deserves the former. So does everyone downstream of what education tolerates.

*"We comply" is not an artefact. The artefact is the artefact.*

---

## Annex A — The four-regime mapping table

*The five regulatory demands, their sources in each regime, and the architectural layer that supplies them. Extends Table 3 of Bounded Inference at the Edge with its ISO/IEC 42001 column (citations verified against BS EN ISO/IEC 42001:2026).*

| Demand | EU AI Act | UK regime | NIST AI RMF | ISO/IEC 42001 | Layer / artefact |
|---|---|---|---|---|---|
| Bounded behaviour | Art. 9 (risk mgmt); Art. 13 (transparency on capabilities/limitations) | KCSIE 2026 (filtering & monitoring scope); ICO Children's Code std 8 (data minimisation) | Govern; Map (intended uses) | Clauses 6.1.2/8.2 (risk assessment); controls A.9.2, A.9.4 (responsible and intended use); A.2.2 (policy) | Layer 2 + Layer 3 |
| Auditable record | Art. 12 (automatic logging) | DPA 2018 / UK GDPR Art. 30; Ofcom OSA codes (record-keeping) | Measure (monitoring); Manage (response logs) | Control A.6.2.8 (event logs); A.7.5 (data provenance); Clause 7.5 (documented information) | Layer 4 (SIVRA-Core) |
| Human oversight | Art. 14 (effective human oversight) | KCSIE 2026 (DSL accountability); UK GDPR Art. 22 | Manage; Govern (accountability) | Control A.9.3 with B.9.3 guidance (oversight objectives); Clause 5.3 / A.3.2 (roles) | Layer 5 + Layer 3 escalation |
| Risk-proportionate transparency | Art. 13 (instructions for use); Art. 11 (technical documentation) | Children's Code std 4 (transparency); ICO transparency duty | Map (intended use, classification) | Controls A.8.2 (user information — incl. knowing one interacts with AI); A.6.2.7 (technical documentation) | Manifest (Layer 1) + Layer 3 |
| Post-deployment monitoring | Art. 9 (continuous risk mgmt); Art. 72 (post-market monitoring) | Children's Code std 9; ICO monitoring expectation | Measure (drift); Manage (treatment) | Control A.6.2.6 (operation & monitoring); Clauses 8.2/8.4 (repeat assessments on change); Clause 9.1 (monitoring & evidence) | Layer 2 + Layer 4 + Layer 5 |
| Provider/deployer split | Art. 16 (provider); Art. 26 (deployer) | School as deployer; integrator as provider; vendor residual duties | Govern (accountability map) | Controls A.10.2–A.10.3 (responsibilities; suppliers) | Manifest (Layer 1) + Layer 3 policy bundle |
| Children-specific obligations | Art. 5 (prohibited practices, incl. emotion inference in education) | KCSIE 2026; Children's Code in full; Protection of Freedoms Act 2012 (biometrics) | Govern (sectoral policy); Map (vulnerable subjects) | Clauses 6.1.4/8.4 with controls A.5.2–A.5.4 (impact on individuals); sector controls via Clause 6.1.3 d)/f) | Layer 3 (KCSIE-aligned envelope) + Layer 5 (DSL routing) |

## Annex B — Statement of applicability: sector-specific extension (summary)

*The full template accompanies this paper. Structure: Part 1 lists the ISO/IEC 42001 Annex A reference controls (A.2.2–A.10.4) with status, justification and evidence columns. Part 2 adopts the sector-specific controls under Clause 6.1.3 d), recorded per 6.1.3 f):*

| Ref | Control | Related Annex A refs |
|---|---|---|
| VC-P1 | Identity non-capture | A.5.4, A.8.2, A.9.3 |
| VC-P2 | Consent as protocol | A.7.5, A.8.2; Clause 7.5 |
| VC-P3 | Bounded autonomy | Clause 8.1; A.9.3/B.9.3; A.9.4 |
| VC-P4 | Agent-to-agent hygiene | Clauses 6.1.2/8.2; A.6.2.6 |
| VC-D1–D6 | Diamond facets (Safety, Sovereignty, Symmetry, Stewardship, Sustainability, Synthetic Intimacy) | See full template; D6 sits beyond Annex A by design |
| VC-L1–L5 | Architecture layers (device integrity; runtime middleware; policy envelope; telemetry & audit; oversight surface) | A.4.4–A.4.5; A.6.2.4/A.6.2.6; A.2.2/A.9.2/A.9.4; A.6.2.8/A.7.5; A.9.3/A.3.2 |

## Annex C — The machine-readable assurance claim (summary)

*Full schema accompanies this paper.* Signed JSON per certified product line: issuer and mark registration with an explicit non-accreditation notice; subject scoped to the exact product line; assessment and expiry dates; per-control claims with pass/exception status and re-verification dates; minors defaults (`ssnz_default_on: true, ssnz_relaxable: false`); accountable oversight as a role; integrity hash over the canonicalised body; signature verifiable against a published key. Raw evidence withheld; the full audit report referenced by hash; the claim chain held append-only in the ledger.

## Annex D — Reference implementations

All open-source under github.com/TheNovacene; GPL-3 across the safety stack, with the underlying lexicon under CC BY-NC-SA 4.0 — operational components reusable on commercial terms, the framework that names them not. **flare-boundary-engine** (Layer 2 — relational boundary enforcement); **verse-nerves** (Layer 2 — coherence observability); **verse-ality-agents** (Layer 3 — machine-readable policy contracts); **Eve11-ClimateMemory** (Layer 4 — mnemonic-density ledger pattern); **mnemonic-attendance** / **mnemonic-deliberation-dashboard** (Layer 5 — schools / deliberative oversight surfaces). The architecture is separable from any vendor; a deployment omitting any of the five layers is not, in this paper's terms, compliance-credible.

## References and related records

- Stevens, K., The Novacene Ltd, & EVE, 11 (2025–2026). *Verse-ality: A Symbolic Definition for the Relational Age* (The Verse-al Lexicon, v8). Zenodo. doi:10.5281/zenodo.17273246
- Stevens, K., The Novacene Ltd (2026). *Bounded Inference at the Edge: A Compliance Architecture for Distributed AI Inference under the EU AI Act, the UK Online Safety Act 2023, and the NIST AI Risk Management Framework* (v1.0, May 2026). Zenodo. doi:10.5281/zenodo.21481256
- Stevens, K., Phillips, M., & The Novacene Ltd (2026). *Schools are becoming critical infrastructure: A school-grade safety model for autonomous AI agents* (v1.0, May 2026). Zenodo. doi:10.5281/zenodo.21481347
- Stevens, K., Eve, ¹¹, The Novacene (2025). *Flare: A Boundary Engine for Relational AI.* Zenodo. doi:10.5281/zenodo.17855976
- The Novacene Ltd (2026). *Glyphonics and the Next Frontier of Threat Intelligence.* Zenodo. doi:10.5281/zenodo.20233610
- Stevens, K. (2025). *Mnemonic Deliberation Dashboard (MDD).* Zenodo. doi:10.5281/zenodo.17489360
- The Novacene Ltd (2025). Public comment NIST-2025-0035-0064, *Securing AI agent systems* RFI. regulations.gov
- The GRC Engineering Cheat Sheet. cheatsheet.grc.engineering
- ISO/IEC 42001:2023 (BS EN ISO/IEC 42001:2026). *Information technology — Artificial intelligence — Management system.* (Content paraphrased under single-user licence; no passages reproduced.)
- Keeping Children Safe in Education 2026 (statutory guidance, from 1 September 2026); ICO Age Appropriate Design Code; Online Safety Act 2023; EU AI Act (Regulation (EU) 2024/1689); NIST AI Risk Management Framework 1.0.
- SIVRA-Core and SYGMA specifications: github.com/TheNovacene/verse-ality-os (docs/substrate, docs/governance) — ISO/IEC 42001 citations verified in-repo, July 2026
- Diamond Standard training corpus: using-ai-safely.com · Consent Infrastructure stack: consent-infrastructure.com · Certification: verse-ality.com
