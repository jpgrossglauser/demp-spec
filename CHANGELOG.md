# Changelog

All notable changes to this project will be documented in this file.
The format is based on [Keep a Changelog 1.1.0](https://keepachangelog.com/en/1.1.0/) and this project adheres to [Semantic Versioning 2.0.0](https://semver.org/spec/v2.0.0.html).

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
[0.4.0 PDF]: https://demp.ch/releases/demp-spec-0.4.0.pdf  
[0.4.0 MD]: https://demp.ch/releases/demp-spec-0.4.0.md
[0.3.0 PDF]: https://demp.ch/releases/demp-spec-0.3.0.pdf  
[0.3.0 MD]: https://demp.ch/releases/demp-spec-0.3.0.md  
[0.2.0 PDF]: https://demp.ch/releases/demp-spec-0.2.0.pdf  
[0.2.0 MD]: https://demp.ch/releases/demp-spec-0.2.0.md  
[0.1.0 PDF]: https://demp.ch/releases/demp-spec-0.1.0.pdf  
[0.1.0 MD]: https://demp.ch/releases/demp-spec-0.1.0.md
