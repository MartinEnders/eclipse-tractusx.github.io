---
id: software-development-view-requirements-kit
title: Software Development View
description: 'Software Development View Requirements Kit'
sidebar_position: 4
---

# Software Development View


## Architecture

### Component Diagram

The flowchart illustrates the interactions between four main components in the system:

#### Components
- **Requirement System**: Core component responsible for requirement management
- **Digital Twin Registry**: Stores and manages digital twin information
- **Submodel Service**: Handles submodel data and operations
- **Eclipse Dataspace Connector (EDC)**: Facilitates data exchange between partners

#### Interactions
The system architecture demonstrates how components interact to facilitate requirement exchange:

- **Requirement System Operations**
  - Registers Digital Twins and Submodel Descriptors in the Digital Twin Registry
  - Provides Requirement Submodels to the Submodel Service
  - Uses the Eclipse Dataspace Connector to request requirements and send notifications
- **Eclipse Dataspace Connector (EDC)**
  - Handles notifications sent from partners back to the Requirement System
  - Acts as the communication bridge between partners
- **Digital Twin Registry**
  - Provides Digital Twins to the Eclipse Dataspace Connector
- **Submodel Service**
  - Provides Submodels to the Eclipse Dataspace Connector

```mermaid
flowchart LR

reqSysC[Requirement System]
dtrC[Digital Twin Registry]
submodelC[Submodel Service]
edcC[Eclipse Dataspace Connector]

reqSysC -- Register Digital Twins and Submodel Descriptors --> dtrC
reqSysC -- Provide Requirement Submodels --> submodelC
reqSysC -- Use EDC to Request Requirements and send notifications --> edcC
edcC -- Handle Notifications sent from partner --> reqSysC
dtrC -- Provide Digital Twins --> edcC
submodelC -- Provide Submodels --> edcC

```

### Requirement Exchange Sequence

The sequence diagram illustrates the requirement exchange flow between a Customer (e.g., an OEM) and a Supplier:

1. **Initial Requirement Creation**:
  - Customer creates a requirement in their requirements system and registers it in their DTR and creates a submodel.
  - Customer's system sends a notification through the EDC to the Supplier

2. **Requirement Request**:
  - Supplier's system requests the requirement details through the EDC
  - The requirement is transferred from Customer's DTR to Supplier's DTR and submodel service

3. **Requirement Update**:
  - After processing, Supplier updates the requirement in their requirements system
  - Supplier sends a notification about the update through the EDC back to the Customer
  - Customer is notified about the requirement update

4. **Next interactions**:
  - The process can be repeated for further updates or new requirements in an interactive manner between the Customer and Supplier.

The diagram shows the core components involved in this exchange:
- Requirement Systems (on both Customer and Supplier sides)
- Digital Twin Registry (DTR) & Submodel Services
- Eclipse Dataspace Connector (EDC) for secure data exchange
- Solid lines indicate dataflow
- Dashed lines indicate initialization of a request

```mermaid

sequenceDiagram
    participant oemReqSys as Requirement System Customer
    participant oemDtr as DTR & Submodel Service Customer
    participant oemEDC as EDC Customer

    participant supEDC as EDC Supplier
    participant supDtr as DTR & Submodel Service Supplier
    participant supReqSys as Requirement System Supplier

    oemReqSys->>oemDtr: Requirement (DTR + Submodel)
    oemReqSys->>oemEDC: Notification
    oemEDC->>supEDC: Notification
    supEDC->>supReqSys: Notification
    supReqSys-->>supEDC: Request Requirement


    supEDC-->>oemEDC: Request Requirement
    oemEDC-->>oemDtr: Request Requirement

    oemDtr->>oemEDC: Requirement

    oemEDC->>supEDC: Requirement
    supEDC->>supDtr: Requirement (DTR + Submodel)

    supDtr->>supReqSys: Requirement

    supReqSys->>supDtr: Update Requirement
    supReqSys->>supEDC: Notification (updated Requirement)
    supEDC->>oemEDC: Notification (updated Requirement)
    oemEDC->>oemReqSys: Notification (updated Requirement)


```

## Requirements Aspect Model

The following section gives an overview of the requirements aspect model. The requirements aspect model is a submodel that contains the requirements information and the status of the requirement.

| Digital Twin Type | Aspect Model | Mandatory Version | Optional Versions | KIT | Standard |
| :-- | :-- | :-- | :-- | :-- | :-- |
| PartType | Requirements | 1.0.0 | | Requirements | CX-..TODO.. |


### Example of a Requirements Aspect Model


```json

{
  "uuidV4Property": "urn:uuid:48878d48-6f1d-47f5-8ded-a441d0d879df",
  "relations": {
    "relatedRequirementIdentifier": "UfzQhdgLLfDTDGspDb",
    "requiremementRelationshipType": "QvBQYuxiXXVytGCxzVllpgTJKhRQq"
  },
  "requirementStatus": {
    "timestampstatus": "2025-05-08T20:07:39.458+02:00",
    "statusValue": {
      "customerStatus": "<empty>",
      "supplierStatus": "<empty>",
      "supplierComment": "yedUsFwdkelQbxeTeQOvaScfqIOOmaa",
      "customerComment": "eOMtThyhVNLWUZNRcBaQKxI"
    }
  },
  "requirementInformation": {
    "foreignID": "dpHYZGhtgdntugzvvKAXLhM",
    "metadata": "VLhpfQGTMDYpsBZxvfBoeygjb",
    "createdDate": "2025-05-08T20:07:39.459+02:00",
    "author": "JxkyvRnL",
    "reqifType": "Functional",
    "specification": "RYtGKbgicZaHCBRQDSx",
    "reqifName": "UMaAIKKIkknjWEXJUfPxxQHeWKEJ",
    "description": "LlN",
    "lastChange": "2025-05-08T20:07:39.459+02:00",
    "version": {
      "versionPredecessor": "1.0.0",
      "versionNumber": "1.0.1"
    },
    "longName": "gNfZBdyFGRajVfJNonEnOinZj"
  }
}

```



## EDC Setup

In order to set up the EDC for the requirements use-case, the following steps are necessary:

- [Setup for the DTR](../digital-twin-kit/software-development-view/) in order to provide access to the Digital Twins for the partners
- [Notifications](../industry-core-kit/software-development-view/notifications) to inform the partners about new requirements or updates. In the requirements use-case the standardized notifications from the Industry Core Kit are used.







## Notice

This work is licensed under the [CC-BY-4.0](https://creativecommons.org/licenses/by/4.0/legalcode).

- SPDX-License-Identifier: CC-BY-4.0
- SPDX-FileCopyrightText: 2025 Dräxlmaier GmbH & Co. KG
- SPDX-FileCopyrightText: 2025 Schaeffler AG
- SPDX-FileCopyrightText: 2025 Mercedes Benz Group AG
- SPDX-FileCopyrightText: 2025 ZF Friedrichshafen AG
- SPDX-FileCopyrightText: 2025 Contributors to the Eclipse Foundation