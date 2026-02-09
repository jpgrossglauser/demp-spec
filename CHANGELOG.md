# Changelog

All notable changes to this project will be documented in this file.
The format is based on [Keep a Changelog 1.1.0](https://keepachangelog.com/en/1.1.0/) and this project adheres to [Semantic Versioning 2.0.0](https://semver.org/spec/v2.0.0.html).

---

## [0.6.0] – 2026-02-09

### Added
  
- **Accessibility**  
  - Added a new top-level **Accessibility** section.

- **Identity Binding Methods**
  - Introduced a normative **Identity Binding** model.

- **Certification of Federations**  
  - Extended the Certification model to include **Federations**.

- **Conformance Section**  
  - Introduced a **Conformance** section.

- **Source Repository Section**  
  - Documented the canonical and mirror source repository for DEMP-SPEC.

- **Licensing**
  - Added a dedicated **License** section to the specification for legal clarity.
  
### Changed

- **Project Management**
  - Formalized the **Apache License, Version 2.0** as the governing license for the specification.
  - Formalized Git-based version control, designating GitLab as the canonical repository and GitHub as a mirror.
  - Introduced canonical, versioned specification URLs under `/spec/{version}`.

- **Alert Model Clarifications**
  - Clarified the semantics of **Zone**, **System**, **Federated**, and **Open Alerts**.
  - Refined Open Alert propagation normative definition to emphasize voluntary forwarding and non-guaranteed reach.

- **Federation Governance**
  - Strengthened normative language around Federation governance agreements.
  - Explicitly tied Consensus Decision-Making (CDM) enforcement to applicable agreements and policies (AMA, CDMA, CRA, OAP).

- **Consensus Decision-Making (CDM)**
  - Clarified override semantics: CDM may be bypassed only when an entity with sufficient privileges is both available and authorized.
  - Renamed and clarified deterministic resolution as **Deterministic Fallback Resolution**.

- **Security and Trust**
  - Clarified the scope of Authentication to explicitly cover SIS–Federation interactions.
  - Harmonized Certification Authority terminology.

- **Document Structure and Editorial Refinements**
  - Applied textual refinements for clarity, consistency and normative precision.
  - Updated internal references, anchors and links to improve navigability and cross-section coherence.
  - PDF exports now use **A4 paper size**.
  - Moved the **Revision History** into Introduction.
  - Moved the **Audience** section into Introduction.
  - Renamed the former *Scope* section to **Overview** for conceptual clarity.
  - Improved consistency and normative precision across Architecture, Security and Trust sections.
  
### Removed

- **Redundant Structural Sections**  
  - Removed sections that duplicated or reduced the clarity of normative content without adding protocol-level requirements.

## [0.5.0] - 2026-01-13

### Added

- **Alert Levels**  
  Introduced a normative **Alert Level** model defining escalation tiers and response expectations.

- **Certification**  
  Added a new normative **Certification** section defining the trust, certification and verification model for DEMP, including certification subjects, authorities and auditability requirements.

  - **Independent Certification Authority (ICA)**  
    Added a normative definition of **Independent Certification Authorities**, including lifecycle management requirements (issuance, expiry, suspension and revocation) and peer oversight capabilities.

  - **Certification Framework**  
    Established a unified **Certification Framework** defining mandatory properties of certifications, including cryptographic verifiability, issuer attribution and time-bounded validity.

  - **Certified Entity and Certified SIS**  
    Introduced explicit definitions for **Certified Entities** and **Certified Safety Information Systems (SIS)** as first-class trust subjects within DEMP.

  - **Auditability Requirements**  
    Added mandatory auditability of trust-related events, including append-only audit registries and pseudonymity by design.

- **Chain of Trust**  
  Introduced a formal **Chain of Trust** model defining how trust is verified, enforced and recorded across Safety Information Systems (SIS). Trust assertions are now explicitly defined as cryptographically verifiable claims derived from certifications.

- **Privileges-Based Authorization Model**  
  Introduced an extensible, privileges-based authorization model allowing Safety Information Systems (SIS) to grant fine-grained operational privileges to Entities.

### Changed
- **Alert Status Model**  
  Reworked alert lifecycle semantics.

- **Federation**  
  Clarified the definition of a Federation and refined the semantics of a Hierarchical Federation.

- **Network Discovery**  
  Clarified that participation in network directories is strictly voluntary and does not affect SIS autonomy.

- **Safety Information System (SIS) Responsibilities**  
  Clarified and formalized SIS responsibilities by explicitly defining normative requirements for data exchange, data processing, data storage and security.

- **Document Structure**  
  Reworked multiple sections to improve clarity, normative precision and consistency.

- **Consensus Decision-Making (CDM)**  
  Updated to align with the privileges-based authorization model, removing reliance on explicit Authoritative Entities and simplifying the deterministic fail-safe resolution mechanism.

### Removed

- **Alert Severity Model**  
  Removed the Alert Severity model. Alert escalation and response expectations are now exclusively defined through the normative **Alert Level** model.

- **Authoritative Entity Concept**  
  Removed the dedicated **Authoritative Entity** concept. Authority and override behavior is now defined through an extensible, privilege-based authorization model.

---

## [0.4.0] - 2025-12-19

### Added
- **Versioning**  
  The Markdown (MD) file is now the canonical source for future versions.

- **Section 5.8.5 (Tie-Breaking)**  
  A deterministic fallback procedure is now a mandatory requirement.

### Changed
- **Section 5.6 (Alerts)**  
  Refined the normative definition of an Alert.

- **Section 5.1.6 (Wide Area Network - WAN)**  
  Internet reachability is no longer mandatory.

- **Section 5.7.1 (Federation Structure)**  
  Relaxed hierarchical federation constraints.
  
- **Document**  
  Minor editorial refinements with no normative impact.
---

## [0.3.0] - 2025-10-28

### Added
- Introduced subsection **5.3.1.1 Mobility** under *5.3.1 Physical Zones*, defining the distinction between *static* and *dynamic* Physical Zones based on the behavior of their spatial references.  
- Added a normative rule requiring that each Safety Information System (SIS) **MUST** continuously maintain the latest known spatial references of every Physical Zone for accurate situational awareness.  

### Changed
- Replaced the term **geospatial data** with **spatial references** in all normative descriptions concerning Physical Zones to achieve a more abstract and interoperable conceptual layer.  
- Minor text edits for clarity, without technical change.

---

## [0.2.0] - 2025-10-08

### Added
- New section **5.1.9 Ad Hoc Network** under *5.1 DEMP Network*, defining support for local mesh and peer-to-peer (P2P) ad hoc communication between participating entities.  
- Specification PDF files have been (re)generated from the Markdown sources using **Pandoc** to improve consistency of formatting and structure.

### Changed
- Clarified that the specification explicitly follows **Semantic Versioning 2.0.0** for version management.  
- Updated the public specification URL from **`https://demp.ch/spec.html`** to **`https://demp.ch/spec/latest`** to establish a stable reference for the most recent version of the DEMP Specification.

---

## [0.1.0] - 2025-04-02

### Added
- Initial public release of the **Decentralized Emergency Management Protocol Specification (DEMP-SPEC)**.  
- Defined core components: **Network**, **Safety Information System (SIS)**, **Safety Zones**, **Entities**, **Devices**, **Alerts**, **Federations**, **Consensus Decision-Making**, and **Chain of Trust**.  
- Established terminology and normative keywords as per [RFC 2119](https://tools.ietf.org/html/rfc2119).  
- Published in Markdown and PDF formats at [demp.ch/releases](https://demp.ch/releases).

---
[0.6.0 PDF]: https://demp.ch/releases/demp-spec-0.6.0.pdf  
[0.6.0 MD]: https://demp.ch/releases/demp-spec-0.6.0.md
[0.5.0 PDF]: https://demp.ch/releases/demp-spec-0.5.0.pdf  
[0.5.0 MD]: https://demp.ch/releases/demp-spec-0.5.0.md
[0.4.0 PDF]: https://demp.ch/releases/demp-spec-0.4.0.pdf  
[0.4.0 MD]: https://demp.ch/releases/demp-spec-0.4.0.md
[0.3.0 PDF]: https://demp.ch/releases/demp-spec-0.3.0.pdf  
[0.3.0 MD]: https://demp.ch/releases/demp-spec-0.3.0.md  
[0.2.0 PDF]: https://demp.ch/releases/demp-spec-0.2.0.pdf  
[0.2.0 MD]: https://demp.ch/releases/demp-spec-0.2.0.md  
[0.1.0 PDF]: https://demp.ch/releases/demp-spec-0.1.0.pdf  
[0.1.0 MD]: https://demp.ch/releases/demp-spec-0.1.0.md
