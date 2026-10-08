# PP-SPEC-054: Proof of Efficacy Mapping to ISO/IEC 27001:2022

| Field | Value |
|---|---|
| Status | DRAFT v0.1 |
| Author | Craig Ellrod, Nebulonium, Inc. (dba HACKERverse®) |
| Date | October 8, 2026 |
| License | CC BY 4.0 |
| Maps to | ISO/IEC 27001:2022 (Edition 3) including ISO/IEC 27001:2022/Amd 1:2024; Annex A controls as aligned with ISO/IEC 27002:2022 (Edition 3) |
| Series | Proof Protocol Framework Mapping Specifications |

---

## 1. Purpose

This specification defines how information security management system (ISMS) requirements and Annex A control references in ISO/IEC 27001:2022 can be bound to Proof Protocol test cases, evidence, and efficacy results.

The upstream source remains authoritative for its own requirements, identifiers, terminology, and guidance. This document defines a **Proof Protocol mapping** and does not supersede, reproduce, modify, or certify conformance to the upstream source.

## 2. Scope

ISO/IEC 27001:2022, *Information security, cybersecurity and privacy protection: Information security management systems: Requirements*, is the third edition, published October 2022 by ISO and IEC. It has been amended by ISO/IEC 27001:2022/Amd 1:2024, *Climate action changes*. As shown on the ISO catalogue at the time of drafting, both are published (stage 60.60) and no revision is listed. Annex A of ISO/IEC 27001:2022 lists information security controls aligned with ISO/IEC 27002:2022, *Information security, cybersecurity and privacy protection: Information security controls* (third edition, February 2022), which provides control guidance.

ISO/IEC 27001 supplies external requirement and control context that can identify what should be examined or tested. Proof Protocol supplies an independent evidence model for determining what happened during a test and whether a selected control performed as claimed.

Independent witnessing, proof validity, evidence capture, packaging, anchoring, and efficacy semantics are defined elsewhere in the Proof Protocol specification family.

## 3. Core Question

Proof of efficacy asks:

> **Was there a control, and did it work?**

A framework requirement, criterion, principle, or obligation may identify a condition of interest. A product, architecture, policy, process, or safeguard may claim to satisfy or mitigate that condition. Proof Protocol binds the external context, test, control, observed behavior, downstream outcome, and evidence into a result that can be independently examined.

Most ISO/IEC 27001 clause requirements concern the establishment, operation, and improvement of a management system and are not empirical control tests. An Annex A control included in a Statement of Applicability is a declared selection. Neither is, by itself, evidence that a control operated. Proof Protocol can supply tested evidence for controls whose operation is empirically testable.

A Proof Protocol result does **not** by itself establish legal, audit, regulatory, or standards conformance unless the applicable authority separately determines that the evidence is sufficient.

## 4. Metric Definitions

Against a defined corpus or test condition, each applicable empirical case is recorded as **blocked**, **detected**, **missed**, or **INVALID** where those verdicts are meaningful.

Relevant measurements can include containment rate, detection rate, miss rate, false-positive rate, robustness under bypass or failure conditions, version-level results, and **INVALID** when required evidence is incomplete or broken.

Not every upstream requirement is empirical. Governance, documentation, organizational, legal, and procedural requirements MUST NOT be converted into efficacy scores merely because they can be referenced by a proof record.

## 5. Evidence Produced

Mapped tests can produce:

- **Proof records** binding external context, test case, control, system/version, verdict, timestamp, and evidence references;
- **ProofStamp™** trusted timestamps bound to evidence/verdict objects;
- **ProofBundle™** packages containing proof records, metrics, corpus manifests, and environment/context;
- **ProofRegister™** records for issued proof artifacts; and
- corpus and environment manifests identifying the tested conditions.

## 6. Mapping to ISO/IEC 27001:2022

Exact clause and control references and titles SHOULD be taken from the authoritative edition being mapped, including any amendment, and recorded in the ProofBundle™ by reference only. ISO/IEC text MUST NOT be copied into proof records or ProofBundles. This specification does not redefine ISO/IEC requirements.

| ISO/IEC 27001:2022 context | Proof Protocol treatment | Evidence |
|---|---|---|
| ISMS clause requirement (clauses 4 to 10) | Record the clause reference as non-empirical context. Management-system requirements MUST NOT be scored as efficacy. | Requirement metadata; assertion record |
| Information security risk assessment and risk treatment | Record the treated risk reference as context for selecting test conditions. | Requirement metadata |
| Statement of Applicability | Record the declared applicability and implementation status as an organizational assertion, separate from tested results. | Assertion record |
| Annex A control reference | Bind the Annex A control reference and edition to one or more reproducible test cases where the control's operation is empirically testable. | Proof record; corpus manifest |
| ISO/IEC 27002:2022 control guidance | Treat as upstream scoping guidance by reference. Do not reproduce guidance text. | Requirement metadata |
| Asserted control implementation | Record the asserted control separately from observed behavior. | Control descriptor |
| Control operation | Exercise the defined condition and capture whether the control operated and whether the protected objective was achieved. | Execution evidence; outcome evidence |
| Exception/failure condition | Exercise negative, bypass, misuse, or failure cases where applicable. | Proof records; robustness evidence |
| Monitoring, measurement, analysis and evaluation | A ProofBundle™ MAY be referenced as an input to the organization's own monitoring and measurement. It does not establish that the clause requirement is met. | ProofBundle |
| Internal audit and certification audit | Package evidence and provenance for independent examination. Proof Protocol results are not audit findings or certification decisions. | ProofBundle |
| Amendment context (Amd 1:2024) | Record the amendment in the edition reference. Climate action changes are non-empirical and MUST NOT be scored as efficacy. | Requirement metadata |
| System/version context | Bind material system, policy, configuration, and environment versions to the result. | Environment descriptor |

A Proof Protocol result for an Annex A control establishes tested behavior for the defined condition. It does not establish ISMS conformity or certification.

## 7. Interoperability Rules

1. The authoritative upstream source, edition/version, and applicable identifier SHOULD be recorded.
2. Upstream identifiers and terminology MUST NOT be silently redefined.
3. Proof Protocol verdicts are Proof Protocol results; they are not upstream certifications, audit opinions, legal determinations, or endorsements.
4. A control's presence, configuration, activation, detection, and efficacy are distinct facts.
5. A policy decision, alert, log entry, or control trigger does not by itself establish efficacy when the claim concerns a downstream protected outcome.
6. Target, application, tool, SIEM, vendor, service, resource, or equivalent evidence SHOULD complete the evidence round trip when required to establish the result.
7. Missing required evidence MUST yield **INVALID**, not PASS.
8. Material changes to the tested system, policy, control, environment, mapping, or corpus SHOULD trigger retesting where they can affect the result.
9. Non-empirical requirements MUST remain distinguishable from empirically tested efficacy assertions.

## 8. Framework-Agnostic Architecture

> **Threat, control, audit, and regulatory frameworks are pluggable inputs to Proof Protocol. Proof Protocol is framework-agnostic.**

External frameworks can identify **what to test or examine**. Proof Protocol independently establishes **whether the control worked and what evidence proves that result**.

No external framework is required for Proof Protocol to operate. An implementation MAY use ISO/IEC 27001:2022, another recognized framework, a proprietary threat model, several frameworks simultaneously, or no external framework when the test condition is otherwise sufficiently defined.

Adding, replacing, muting, or removing a framework mapping does not alter the Proof Protocol architecture, evidence model, Proof of Efficacy determination, ProofBundle™, ProofStamp™, ProofRegister™, or independent corroboration requirements.

A framework mapping therefore establishes **interoperability**, not architectural dependency.

## 9. Relationship to Proof Protocol

This mapping is part of the Proof Protocol specification family maintained by Nebulonium, Inc.

The relationship is intentionally asymmetric:

> **ISO/IEC 27001:2022 supplies management-system requirements and control references. Proof Protocol supplies the evidence model for independently examining whether a selected control performed as claimed.**

No affiliation, endorsement, certification, audit opinion, or sponsorship by ISO or IEC is implied.

## 10. Source Framework, Attribution, and License

ISO/IEC 27001:2022, ISO/IEC 27001:2022/Amd 1:2024, and ISO/IEC 27002:2022 are copyrighted works jointly published by the International Organization for Standardization (ISO) and the International Electrotechnical Commission (IEC). ISO states on its standards pages and copyright page (https://www.iso.org/copyright.html) that "All ISO publications and materials are protected by copyright" and that "Any use, including reproduction requires our written permission." ISO's copyright page also states that, apart from ISO Open Data, ISO content may not be used for machine learning or artificial intelligence purposes. Permission requests are directed to ISO (copyright@iso.org) or the ISO member in the user's country.

ISO's guidance on its name and logo (https://www.iso.org/iso-name-and-logo.html) asks that standards be cited in full (for example, with edition year), that the ISO logo not be used, and that no one claim endorsement, approval, or certification by ISO; ISO notes that it does not perform certification.

This specification cites standard numbers, edition years, the amendment reference, clause and control references, and short titles for identification only. It reproduces no requirement, control, or guidance text, and contains no ISO/IEC content. Catalogue metadata obtained from ISO Open Data is licensed by ISO under the ODC Attribution License (ODC-By) v1.0 and, if used, MUST carry ISO's attribution.

This Proof Protocol mapping is independently authored and licensed under **CC BY 4.0**. That license applies only to original Proof Protocol material in this repository. It does not relicense external standards, regulations, criteria, frameworks, or trademarks.

Where upstream material is copyrighted or access-controlled, contributors MUST NOT copy protected normative text into this repository merely to make the mapping self-contained. Reference identifiers and independently authored descriptions should be used where legally appropriate.

### Required attribution

ISO's public pages do not prescribe an acknowledgment line for citing standard numbers. The following verbatim ISO statement and recommended notice are used:

> "All ISO publications and materials are protected by copyright" and "Any use, including reproduction requires our written permission." (https://www.iso.org/copyright.html)

> ISO/IEC 27001:2022, ISO/IEC 27001:2022/Amd 1:2024, and ISO/IEC 27002:2022 are copyright ISO and IEC. "All ISO publications and materials are protected by copyright" (https://www.iso.org/copyright.html). This repository cites standard numbers, clause and control references, and titles for identification only and reproduces no ISO/IEC text. ISO does not perform certification, and no endorsement, approval, or certification by ISO or IEC is claimed.

If ISO Open Data catalogue metadata is incorporated, ISO's suggested attribution applies verbatim: "This work is based on the iso_deliverables_metadata dataset from ISO Open Data" "licensed under ODC Attribution License (ODC-By) v1.0" (https://www.iso.org/open-data.html).

Because only identifiers and short titles are cited, no ISO/IEC text is reproduced or relicensed under CC BY 4.0. Implementers who need requirement or control text MUST obtain it from ISO, IEC, or an authorized national body under their own license.

## 11. Versioning

This mapping is versioned independently of ISO/IEC 27001. Material upstream changes, including a new edition, amendment, or corrigendum of ISO/IEC 27001 or ISO/IEC 27002, SHOULD trigger a mapping review and, where necessary, a new version identifying the edition mapped.

---

*Proof Protocol · proofprotocol.io · CC BY 4.0*
