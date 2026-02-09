---
version: 0.6.0
dateModified: 2026-02-09T00:00:00+00:00
dateModifiedString: 9 February 2026
---

# Introduction

The **Decentralized Emergency Management Protocol (DEMP)** provides secure,
interoperable, decentralized communication between
[Safety Information Systems (SIS)](#safety-information-system-sis), operating
either as standalone nodes or within a [Federation](#federation). It supports
scalable [Alert](#alert) propagation and information exchange across
[Safety Zones](#safety-zone), [Entities](#entity) and [Devices](#device),
enabling real-time collaborative emergency management.

The **Decentralized Emergency Management Protocol Specification (DEMP-SPEC)**
defines the architecture and implementation guidelines for emergency management built on DEMP.

## Revision History

The full revision history for this specification is maintained at:
[https://demp.ch/spec/CHANGELOG.md](https://demp.ch/spec/CHANGELOG.md)

## Source Repository

The DEMP Specification (DEMP-SPEC) is maintained on
[GitLab](https://gitlab.com) and mirrored to
[GitHub](https://github.com) to support feedback, collaboration and community
engagement. These public repositories provide transparency and spaces for
discussing issues and tracking changes.

- Canonical Repository:
[https://gitlab.com/jpgrossglauser/demp-spec](https://gitlab.com/jpgrossglauser/demp-spec)

- Mirror (read-only):
[https://github.com/jpgrossglauser/demp-spec](https://github.com/jpgrossglauser/demp-spec)

## Versioning

This specification follows [Semantic Versioning (SemVer) 2.0.0](https://semver.org/spec/v2.0.0.html) to manage its
releases and updates. Version numbers reflect changes to the specification and are intended to help stakeholders assess the impact of updates on existing implementations.

For tooling and automation purposes, the current version of this specification
may also be exposed via a `VERSION` file available at [https://demp.ch/spec/VERSION](https://demp.ch/spec/VERSION) 

## Conformance

### Requirement Levels

The key words **"MUST"**, **"MUST NOT"**, **"REQUIRED"**, **"SHALL"**,
**"SHALL NOT"**, **"SHOULD"**, **"SHOULD NOT"**, **"RECOMMENDED"**,
**"MAY"**, and **"OPTIONAL"** in this document are to be interpreted as
described in [RFC 2119](https://www.rfc-editor.org/rfc/rfc2119) and
[RFC 8174](https://www.rfc-editor.org/rfc/rfc8174), when, and only when,
they appear in all capitals, as shown here.

# License

This specification is licensed under the **Apache License, Version 2.0**.

You may use, reproduce, modify and distribute this specification in compliance
with the terms of the Apache License, Version 2.0. The license provides an
express grant of patent rights from contributors and ensures legal clarity and
protection for contributors, integrators and users.

A copy of the license is available at:
[https://www.apache.org/licenses/LICENSE-2.0](https://www.apache.org/licenses/LICENSE-2.0)

Additional attribution and notice information is provided in the
[NOTICE](https://demp.ch/spec/NOTICE) file distributed with this specification.

# Audience

The primary goal of this specification is to provide comprehensive documentation
for **software architects, developers and integrators**, enabling them to design, implement
and integrate DEMP-based systems and applications.

# Architecture

## Network

A **DEMP Network** **MUST** form the backbone for communication between multiple Safety Information Systems (SIS).

### Decentralization

There **MUST** be no central authority managing the DEMP Network operations.

### Interoperability

A DEMP Network **MUST** support interoperability between heterogeneous implementations of Safety Information Systems (SIS), ensuring that they can securely communicate with each other, regardless of their underlying hardware, software or geographical location.

### Communication

A DEMP Network **SHOULD** rely on the Internet Protocol (IP) for communication
([RFC 791](https://www.rfc-editor.org/rfc/rfc791),
[RFC 8200](https://www.rfc-editor.org/rfc/rfc8200)) and **MAY** use the
Domain Name System (DNS) for naming and addressing purposes
([RFC 1034](https://www.rfc-editor.org/rfc/rfc1034),
[RFC 1035](https://www.rfc-editor.org/rfc/rfc1035)).

### Scalability

A **DEMP Network** **MUST** be designed to scale dynamically, allowing Safety Information Systems (SIS) to be added to or removed from the network without disrupting ongoing operations or compromising availability.

### Scope

#### Wide Area Network (WAN)

A **DEMP Network** **SHOULD** be able to operate across Wide Area Networks (WAN), including the public Internet, to enable communication and federation between geographically distributed Safety Information Systems (SIS).

#### Local Area Network (LAN)

A **DEMP Network** **SHOULD** be able to operate within a Local Area Network (LAN), enabling Safety Information Systems (SIS) to function autonomously in isolated, offline or network-restricted environments.

#### Virtual Private Network (VPN)

A **DEMP Network** **SHOULD** support operation over Virtual Private Networks (VPN), enabling secure and controlled interconnection between geographically or administratively separate Safety Information Systems (SIS).

#### Ad Hoc Network

A **DEMP Network** **MAY** support operation within a local mesh or peer-to-peer (P2P) ad hoc network that enables offline or short-range secure data exchange.

### Discovery

#### Directory

A DEMP Network **MAY** provide a directory to facilitate the discovery of Safety Information Systems (SIS). If provided, the directory **MUST** maintain an accurate and up-to-date registry of all participating SIS.

#### Participation

Participation in any discovery mechanism **MUST** be voluntary. A Safety Information System (SIS) **MUST** be able to opt in to or opt out of a Network Directory without affecting its ability to operate within the DEMP Network.

## Safety Information System (SIS)

A **Safety Information System (SIS)** **MUST** monitor, manage, process and exchange
safety-related data for Entities and between Safety Information Systems (SIS),
either as a standalone instance or as a participant in a Federation.

### Data Exchange

A **Safety Information System (SIS)** **SHOULD** ensure reliable information exchange with Entities and other Safety Information Systems (SIS), taking availability constraints into consideration.

### Data Processing

A Safety Information System (SIS) **MUST** process DEMP data in accordance with applicable privacy requirements.

### Data Storage

A Safety Information System (SIS) **MAY** store DEMP data required for operation, recovery and auditability.

### Confidentiality

A **Safety Information System (SIS)** **MUST** protect data exchange, data processing
and data storage against unauthorized access and tampering through **documented**
technical and organizational measures.

### Autonomy

A Safety Information System (SIS) **MUST** be capable of operating autonomously within its defined scope, without requiring continuous connectivity to other Safety Information Systems or external services.

### Deployment

A Safety Information System (SIS) **SHOULD** be deployed in a stable, managed and production-grade environment appropriate for continuous operation, scalability and appropriate levels of availability.

### Hub

A Safety Information System (SIS) **MUST** be accessible by Entities through an access point called a **Hub**.

#### Interface

A **Hub** **SHOULD** be a secure HTTP service providing web-based access to administrative information and interaction features for Entities.

#### Access Control

Access to the **Hub** **MUST** be either public or private (network-restricted). It **MAY** also be subject to authentication.

## Safety Zone

A **Safety Zone** (Zone) **MUST** be a defined physical or virtual area that is monitored for safety events and emergency management purposes.

### Physical Zone

A **Physical Zone** **MUST** be defined by accurate **spatial references**.

#### Mobility

A **Physical Zone** **MAY** be either _static_ or _dynamic_, depending on whether its **spatial references** remain constant over time.

### Virtual Zone

A **Virtual Zone** **MUST** be based on logical boundaries without spatial reference requirements.

### Temporality

A **Safety Zone** **MAY** be defined temporarily for particular time-based events.

#### Time Boundaries

Such zones **MUST** have explicitly defined start and end times specified in Coordinated Universal Time (UTC).

## Entity

An **Entity** **MUST** represent a participant interacting with a Safety Information System (SIS).

### Role

An Entity **MUST** be assigned exactly one Entity role.

#### Individual

An Entity with this role **MUST** represent a single human person acting in an individual capacity.

#### Organization 

An Entity with this role **MUST** represent a structured group acting as a collective participant.

#### Autonomous Agent

An Entity with this role **MUST** represent a software-based agent capable of operating autonomously and interacting with the SIS without direct human intervention.

### Capability

An **Entity** **MUST** expose its technical capabilities to a
**Safety Information System (SIS)**, including the actions and interactions it
is able to perform within the DEMP scope.

### Connectivity

An **Entity** **MUST** reflect its current connectivity state, representing its
ability to establish and maintain communication with a
**Safety Information System (SIS)**.


## Device

A Device **MUST** be able to communicate with a Safety Information System (SIS)
on behalf of an Entity.

### Device Type

A **Device** **MUST** be classified as either a **Software Device** or a
**Hardware Device**. This classification **SHOULD** be taken into account by
interacting **Entities** to ensure correct handling.

### Device Mode

A Device **MUST** operate in either **Active** or **Passive** mode. The selected
mode defines how an Entity **MAY** interact with the Device through the Safety
Information System (SIS).

#### Active Devices

An **Active Device** **MAY** change its operational state in response to a
request issued by an Entity.

#### Passive Devices

A **Passive Device** **MUST NOT** change its operational state in response to
any request issued by an Entity.

## Alert

An **Alert** **MUST** represent a safety, security or emergency situation managed by a Safety Information System (SIS).

### Status

Each Alert **MUST** have exactly one status that reflects its current state within the Safety Information System (SIS).

At least the following alert statuses **MUST** be defined, supported and interpreted as follows:

- **Reported**: This status **MUST** indicate that an Alert has been triggered by the Safety Information System (SIS).

- **Responding**: This status **MUST** indicate that response, coordination or mitigation actions are currently being performed.

- **Resolved**: This status **MUST** indicate that the situation has been addressed and that no further response action is required.

- **Rejected**: This status **MUST** indicate that an alert has been dismissed and **MUST NOT** require further action.

### Level

The Alert level **MUST** indicate the escalation tier of an alert and define the expected response and handling obligations.

At least the following alert levels **MUST** be defined and interpreted as follows:

- **Test**: Alerts of this level **MUST** be used exclusively for testing or training purposes and **MUST NOT** represent real situations.

- **Information**: Alerts of this level **MUST** be intended to convey general information and **MUST NOT** require action or confirmation of reception.

- **Warning**: Alerts of this level **MUST** represent potential safety issues and **MUST** require confirmation of reception.

- **Emergency**: Alerts of this level **MUST** represent situations requiring immediate intervention.

### Zone Alert

A **Zone Alert** **MUST** be generated for situations that could affect a specific physical or virtual Safety Zone within a SIS.

### System Alert

A **System Alert** **MUST** be generated for situations that could affect all Safety Zones within a SIS.

### Federated Alert

A **Federated Alert** **MUST** be generated for situations that could impact multiple Safety Information Systems (SIS) participating in a Federation.

### Open Alert

An **Open Alert** **MUST** be generated for situations requiring widespread propagation across a DEMP Network.

#### Propagation

An Open Alert **SHOULD** be forwarded by the originating Safety Information System
(SIS) to every Federation it participates in. Each Federation member **MAY** subsequently propagate the Open Alert to third-party systems.

## Federation

A Federation **MUST** be a structured group of Safety Information Systems (SIS) that voluntarily and formally collaborate through explicitly defined agreements in order to share information and, where applicable, coordinate decision-making related to safety and emergency management.

### Structure

Federations **MAY** adopt a hierarchical structure. A hierarchical
Federation **MUST** be composed of multiple federation levels, where a Safety
Information System (SIS) may federate with other SIS operating at different
scopes, geographical coverage, responsibilities, or jurisdictions.

### Governance
 
Federation governance **MUST** be explicitly defined through formally adopted
agreements and policies accepted by all participating Safety Information
Systems (SIS).

#### Alert Management Agreement (AMA)

A **Federation** **SHOULD** define an **Alert Management Agreement (AMA)**
describing how, when and where Federated Alerts are triggered, escalated
and handled across participating **Safety Information Systems (SIS)**.

#### Consensus Decision-Making Agreement (CDMA)

A **Federation** **SHOULD** establish a **Consensus Decision-Making Agreement (CDMA)**
that defines the applicable polling mechanisms, decision thresholds and any
extended or overriding decision-making privileges.

#### Conflict Resolution Agreement (CRA)

A **Federation** **SHOULD** define a **Conflict Resolution Agreement (CRA)**
describing how conflicts between participating Safety Information Systems (SIS) are
resolved.

#### Open Alert Policy (OAP)

A **Federation** **SHOULD** establish a common **Open Alert Policy (OAP)**
defining the conditions under which participating Safety Information Systems
(SIS) accept, process or forward Open Alerts.

## Consensus Decision-Making (CDM)

A Consensus Decision-Making (CDM) process **MAY** be used within a Safety
Information System (SIS) or a Federation to resolve specific decisions.

CDM decisions **MUST** be made collectively by participating entities within the
applicable scope and **MUST** be enforced by the hosting SIS or Federation in
accordance with the applicable decision agreements and policies.

### Polling

Polling is the mechanism by which participating entities express a decision
within a Consensus Decision-Making (CDM) process. Polling **MUST** be bounded,
deterministic and time-constrained to ensure safe and predictable outcomes.

#### Time-Bound Polling

The polling mechanism **MAY** be time-bound to ensure prompt decision-making.
 
#### Repeated Poll

A **Safety Information System (SIS)** **MAY** repeat a poll if the outcome cannot be
formally established, provided that the conditions for such repetition are met
within the applicable decision window.

#### Fallback Resolution

If a repeated poll is not feasible due to alert level, time constraints or any other reason, the Safety Information System (SIS) **MUST** apply a deterministic fallback procedure.

The fallback procedure **MUST NOT** rely on additional polling and **MUST**
produce a single, deterministic outcome.

### Override

A Consensus Decision-Making (CDM) process **MAY** be bypassed when an Entity with
sufficient privileges is available and permitted to act within the applicable
scope.

# Security and Trust

## Identity

Identity defines how a Subject within the DEMP scope is uniquely identified and how control over identifiers is established and maintained over time.

### Identifier

An Identity **MUST** be associated with one or more stable and unique identifiers
within the DEMP Network scope.

### Binding

Identity binding methods **MUST** define how an identifier is initially
assigned to a Subject and how this association is established as
authoritative within a defined scope.

Binding **MUST** be explicit and auditable and **MUST NOT** imply global
authority or transitive trust.

At least the following identity binding methods **SHOULD** be supported.

#### Trust-On-First-Use (TOFU)

Under the Trust-On-First-Use (TOFU) binding method, an identifier **MUST** be
accepted on its first encounter and **MUST** be considered trusted as long as
continuity is maintained.

#### Explicit Binding

Under the Explicit Binding method, an identifier **MUST** be bound through an
explicit and trusted verification process.

#### Delegated Binding

Under the Delegated Binding method, an identifier **MUST** be bound through
delegation by another trusted party.

#### Self-Asserted Binding

Under the Self-Asserted Binding method, an identifier **MAY** be claimed without
prior verification and **MUST** be treated as unverified.

## Authentication

Authentication **MUST** be the mechanism by which an Entity proves control over
its Identity to a Safety Information System (SIS), or by which an SIS proves
control over its Identity to a Federation.

## Certification

Certification **MUST** establish *verifiable trust claims* that can be independently validated through a Chain of Trust.

### Authority

A **Certification Authority** **MUST** be an independent organization responsible for evaluating and certifying Entities, Safety Information Systems and Federations in accordance with the applicable Certification Framework.

A Certification Authority:

- **MUST** be organizationally and operationally independent from the subject it certifies  
- **MUST** apply evaluation criteria that are publicly available  
- **MUST** apply evaluation criteria consistently to all subjects it certifies  
- **MUST** be clearly identifiable and accountable  
- **MUST** support certification lifecycle management, including issuance, expiry, suspension and revocation  

#### Oversight

Certification Authorities **MAY** perform peer oversight to assess compliance
with this specification and adherence to recognized best practices.

### Framework

Any certification issued under the Certification Framework:

- **MUST** be issued by a Certification Authority
- **MUST** be unambiguously attributable to a specific Certification Authority
- **MUST** be time-bounded, with an explicit validity period  
- **MUST** support suspension and revocation  
- **MUST** be cryptographically verifiable

## Authorization

Authorization **MUST** define a privileges-based model governing the
permission to perform actions by Entities, Safety Information Systems (SIS), and
Federations within the DEMP scope.

## Auditability

Trust-related events **MUST** be auditable.

Auditability **MUST** allow independent verification that trust-related lifecycle events occurred, were not altered, removed or suppressed.

### Pseudonymity

Audit records **MUST** be pseudonymous by design.

### Registry

To support immutability and non-repudiation, trust-related lifecycle events **MUST** be recorded in an append-only audit registry.

# Accessibility

Implementations **MUST** ensure that alerts and other safety-critical information
remain accessible to all users, regardless of physical, sensory, cognitive or
situational limitations.

## Inclusion

Implementations **MUST** provide an inclusive user experience enabling access for users with disabilities, including but not limited to visual, auditory, motor and cognitive impairments.

## Adaptability

Implementations **MUST** be designed to operate effectively under adverse conditions commonly associated with emergency situations and **SHOULD** optimize resource usage to minimize computational load, network bandwidth and energy consumption.

## Internationalization

Alerts and generic emergency instructions **MUST** be expressed in a language-agnostic form at the protocol level, enabling localized rendering by implementations without altering the underlying semantic meaning.