---
id: adoption-view-geometry-kit
title: Adoption View
description: 'Adoption View Geometry Kit'
sidebar_position: 2
---

<!-- TODOs: 


Reference Implemenation
- Where is the reference implementation sitting? What repo? 



Section Use Case

- Use Case selection: WG needs to align on Use Cases we are gonna describe that are relevant
  - Currently Engineering Collaboration as the Use Case favoured. 
  
- User Journey Diagram and description. We need to describe how a user would interact with geometry. Meaning the use case of: Geometry is created -> Shared with Partner 2 -> Partner 2 Reviews -> Gives back to Partner 1 ... see WG Miro HANNES
- Customer Joureny: https://eclipse-tractusx.github.io/docs-kits/kits/requirements-kit/adoption-view#customer-journey HANNES 


Section: Geometry understanding
- Description of structure of Geometry vs. BOM Structure. See SBOM Standard https://github.com/catenax-eV/product-standardization-prod/blob/R25.09-CX-XXXX-CarSBOM/standards/CX-XXXX-CarSBOM/CX-XXXX-CarSBOM.md#53-tier-n-sbom-propagation-option-1 SARAH 


Describe Relevant Related Standards: 
- Geometry Standard
- Binary Exchange (Standard or aspect model)
- Master Data 
SARAH 


Example Files and Understanding: 
- Describe participant overview (how many and role) 
- Descibe Overall "Product" the full bike
- Descibe SupplyChain of participants (Who supplies what to whom)
- Provide description of 3D Data set Motorbike with definition of participants and data ownership
MICHAEL 
 
 -->

## Vision & Mission

### Vision

The vision of the **Geometry KIT** is to enable secure and sovereign exchange of engineering geometry information across the entire value chain and all n-tier levels in Catena-X. It focuses on making 3D assets—such as CAD models and their associated metadata from Data-Management-Systems — discoverable, accessible, and reusable for data-driven use cases without compromising data sovereignty.

The Kit provides a uniform, standards-based foundation for interoperability between Business Partners when sharing geometry information. It covers master data (Stammdaten) and geometry, ensuring that participants can build consistent, trusted engineering data chains throughout the lifecycle of products and components.

### Mission

The Geometry KIT bundles the necessary Catena-X standards, profiles, APIs, semantic models, and reference implementations to publish, discover, request, and consume geometry information in the dataspace. It provides clear guidance and tooling to map data from enterprise PLM/CAE systems into Catena-X-compliant representations and exchange files efficiently and securely.

By adopting existing Catena-X standards the Geometry KIT enables rapid implementation of multiple engineering use cases around geometry data exchange.


## Business Value & Benefits

### Business Value
The Geometry KIT enables companies to build secure, cross-company engineering collaboration use cases within Catena-X. By providing standardized models and interfaces for 3D data exchange, it reduces integration costs, accelerates development cycles, and improves data quality. Companies benefit from faster iterations, streamlined onboarding, and robust IP protection—leveraging Catena-X’s architecture to collaborate efficiently while maintaining data sovereignty.

### Todays Challenge


Today, companies face significant challenges when exchanging engineering-grade geometry data across organizational boundaries. Critical 3D CAD data is often locked away in isolated systems, accessible only to a few experts. Sharing geometry with partners typically requires manual exports, data conversions, or the use of static screenshots and lightweight viewers—processes that are time-consuming, error-prone, and result in loss of detail and context. These workarounds create data silos, slow down collaboration, and increase the risk of inconsistencies and downstream errors.

Security and intellectual property protection add further complexity: companies must ensure that sensitive design data is only accessible to authorized partners, while still enabling efficient collaboration. The lack of standardized, automated processes for geometry exchange leads to duplicated efforts, high integration costs, and limited ability to leverage 3D data throughout the product lifecycle. As a result, engineering teams struggle to keep data up-to-date, respond quickly to changes, and fully realize the value of their 3D assets in cross-company projects.

### Benefits for OEM, Suppliers and Solution Provider

#### OEM and suppliers
The Geometry KIT empowers OEMs and suppliers to streamline cross-company engineering collaboration. By bundling key standards—such as the Geometry Standard, SingleLevelSceneNode, Masterdata Standard, Binary Exchange, and the Digital Twin Standard — it enables essential use cases like DMU analysis to be implemented efficiently within Catena-X. Leveraging the Catena-X architecture, OEMs and suppliers can securely exchange 3D data and collaborate across company borders, with IP protection and data sovereignty ensured by the underlying Catena-X design. This reduces manual effort, accelerates design cycles, improves data consistency, and enables automated feedback loops and faster onboarding throughout the supply chain.


#### Solution Provider
By implementing and aligning their offerings with Catena-X, solution providers can position their products for secure, standards-based data exchange and connect to a growing network of participants within the Catena-X ecosystem. This alignment puts their solutions at the forefront of modern geometry data exchange, enabling seamless integration, interoperability, and access to new business opportunities across industries. Solution providers benefit from increased market relevance, the ability to address customer requirements for secure collaboration, and the potential to drive innovation in digital engineering workflows.

## Use Case


### Digital Mock-Up Analysis: A Cross-Company Collaboration Use Case

Digital Mock-Up (DMU) Analysis is a central use case in the design phase of physical products, where OEMs and suppliers must collaborate closely to develop and adjust their products in line with requirements from both sides. During this phase, engineers regularly review, comment, and align on the current development status, communicating necessary changes and feedback iteratively. DMU Analysis enables teams to ensure the evolving product meets all requirements before physical prototypes are built.

At its core, DMU Analysis empowers engineers to perform essential digital engineering tasks on 3D models and assemblies—such as taking precise measurements, comparing design variants, inspecting internal and external structures, and visualizing key properties or changes. These capabilities allow teams to validate fit, function, and compliance with requirements, identify potential issues early, and communicate findings clearly—all before any physical prototype is built.

This frequent, iterative exchange and review of engineering data between partners is the core collaboration scenario that the Geometry KIT enables, making secure, automated, and standards-based 3D data sharing possible across company boundaries.

#### High-Level Scenario

In a typical DMU Analysis workflow, one partner (e.g., a supplier) creates or updates a 3D model and publishes it as a Digital Twin with geometry data into the Catena-X dataspace. Another partner (e.g., an OEM) discovers, pulls, and reviews this geometry data in their own environment, performing analyses such as clash detection, assembly verification, and feedback annotation. The process is iterative: feedback is provided, updates are made, and the cycle repeats until the design is accepted—all while maintaining data sovereignty and security. Also see User Journey section for more details. 

#### Practical Variants of DMU Analysis

While the core DMU Analysis workflow remains consistent, its practical application can take several forms depending on the engineering context, data sensitivity, and collaboration needs. The following common variants illustrate how the use case is adapted in real-world scenarios:

**1. Basic Build Room Analysis**

In early design phases, engineers often need to ensure that a future part will fit within the available space of an assembly. For this purpose, it is common to exchange only simplified geometry—such as bounding boxes or build room-defining surfaces—rather than full detailed models. This approach enables rapid spatial checks and early alignment between partners, while minimizing the exposure of sensitive design details.

**2. Exchange of Different Levels of Detail**

Not all collaboration requires the full geometric detail of a part or assembly. Depending on the phase of development and the sensitivity of the data, participants may choose to share reduced or simplified models (e.g., envelope geometry, de-featured shapes) to protect intellectual property or because such information is sufficient for the task at hand. Conversely, as the design matures and discussions move into detailed engineering, high-fidelity models with full precision may be exchanged to enable thorough analysis and validation.

**3. Exchange of Different File Formats**

Because partners often use different CAD systems and engineering tools, DMU Analysis scenarios frequently require the exchange of geometry in multiple formats. Common standards include JT and STEP, but native formats from systems like CATIA, Creo, or NX may also be used. The Geometry KIT supports this diversity by enabling the secure, standards-based transfer of various file types, ensuring interoperability across company and system boundaries.

These variants demonstrate the flexibility of DMU Analysis within Catena-X: from lightweight, early-phase checks to detailed, high-precision collaboration, and across a range of data formats. By supporting these different forms, the Geometry KIT ensures that engineers and implementors can tailor their data exchange to the needs of each project phase—balancing efficiency, security, and technical requirements.

## User Journey

The following simplified diagram illustrates the circular, iterative flow of engineering collaboration and review for 3D geometry data in Catena-X:

```mermaid
flowchart TD
	subgraph Partner_1 ["Partner 1"]
		A["Create/Update 3D Model"]
		D["Review Feedback & Update Model if Needed"]
	end

	subgraph Partner_2 ["Partner 2"]
		B["Pull Geometry Data<br/>Review & Annotate (DMU, Bauraum, etc.)"]
		C["Accept / Request Changes / Comment"]
	end

	A --> B
	B --> C
	C --> D
	D -- "If changes required" --> A
	C -- "If accepted" --> E["Process Complete"]
```

**Description:**

1. Partner 1 (Supplier) creates or updates a 3D model and publishes it as a Digital Twin with geometry data via EDC into the Catena-X dataspace.
2. Partner 2 (Customer/Partner) pulls the geometry data into their environment and performs review/analysis (e.g., DMU Analysis, Buildroom checks).
3. Partner 2 annotates, comments, and either accepts the data or requests changes.
4. Partner 1 reviews the feedback and, if needed, updates the model and republishes a new Digital Twin.
5. The cycle repeats until the geometry is accepted, ensuring efficient, sovereign, and standards-based cross-company collaboration.

<!-- Specials within the scenario: 

- Geometry Detail Exchange
- DMU Light Review with Bounding Box and without Geometry load
-->


### User Journey System Flow

## Geometry understanding

The following section describes the difference in structure of the SingleLevelSceneNode and the BOM structure. It also makes clear how both work together. The SingleLevelSceneNode and SingleLevelBOM aspect models in Catena-X serve two complementary but clearly distinct purposes.

The SingleLevelSceneNode defines the geometric and spatial structure within a single digital twin. It organizes geometry data by describing how individual objects or assemblies are positioned, transformed, and related to one another inside that twin. Each SingleLevelSceneNode represents a geometric object or group of objects, identified by its own Catena-X ID. Through its child items, a scene node can reference other scene nodes, but only those that belong to the same digital twin (and therefore are provided by the same participant). These hierarchical relationships are purely spatial — they define how geometry is composed and arranged, not how different products or business entities are connected or how assebly throughout multiple participants work. The model also contains information such as transformation matrices, bounding volumes, and metadata that describe the geometry’s placement and extent. In essence, the SingleLevelSceneNode provides the internal geometry structure that can be used for visualization, simulation, or digital mock-up purposes.

The BOM structure, on the other hand, describes the logical and semantic product structure that spans multiple digital twins. Instead of focusing on geometry, it defines how different components — potentially originating from different business partners — are related in a product hierarchy. Each child item in the BOM points to the Catena-X ID of another digital twin, allowing an OEM’s twin, for example, to reference parts or sub-assemblies provided by suppliers. Through this model, the overall product composition across the supply chain can be represented consistently. These connected digital twins can contain geometry data as well but don't have to.

In short, SingleLevelSceneNode connects geometry within one digital twin, whereas SingleLevelBOM connects digital twins with each other. The SingleLevelSceneNode model builds the internal spatial view of a twin, while the BOM model builds the external structural view across organizational boundaries — together forming a complete digital representation of both the product’s geometry and its multi-partner assembly hierarchy. The overview can be found in the following table.

| Feature                       | **SingleLevelSceneNode**                                                                                | **SingleLevelBOM**                                                                                            |
| ----------------------------- | ------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------- |
| **Purpose / Function**        | Represents the **spatial and geometric structure** within a single digital twin.                        | Describes the **logical and functional product structure** (bill of materials) across multiple digital twins. |
| **Scope / Level**             | Applies **only within one digital twin** — i.e., within its own data instance.                          | Connects **multiple digital twins** — components or assemblies across business partners.                      |
| **Type of Relationship**      | **Geometric / spatial** relationships between parts (e.g., transform, bounding volume).       | **Structural / semantic** relationships (e.g., which component belongs to which assembly).                    |
| **Main Entity**               | `modelItems` — links to a geometry data object or group of objects.                                                          | `childItem` — describes the relationship between parent and child twins.                       |                          |
| **Linking Mechanism**         | Via `childItems`: connects **own geometries (SceneNodes)** hierarchically. No external references.      | Via `childItems`: connects **different digital twins**, forming a product structure.                          |
| **Data Content**              | geometry as data ressource, transformations, bounding volumes.                                               | Product metadata, identifiers, classifications, and references to other aspects (e.g., Part Type).            |
| **Typical Use Case**          | Visualization, simulation, DMU analysis, or digital mock-up of a geometry model.                                            | Building a complete product structure across company boundaries.                                              |


## System Overview: Data Flow Across Partners

The following diagram shows the main systems involved in the user journey, clearly differentiating between both partners. Each partner has its own data source, EDC, and business application. The Digital Twin Registry enables discovery and linkage across the ecosystem.

```mermaid
flowchart TB
    subgraph Partner1["Partner 1 (Data Producer)"]
        P1APP["Business App<br/>(Create/Publish/Review Feedback)"]
		P1DS["Data Source<br/>(3D Data Persist/Update)"]
        P1EDC["EDC"]
        
    end

	DTR["Digital Twin Registry"]

    subgraph Partner2["Partner 2 (Data Consumer)"]
        P2APP["Business App<br/>(Discover/Review/Annotate)"]
		P2DS["Data Source<br/>(Local Copy/Updates)"]
        P2EDC["EDC"]
        
    end

    

    %% Data Producer Flows
    P1APP -- "Update 3D Data" --> P1DS
	P1DS -- "Read 3D Data" --> P1APP
    P1EDC <-- "Register/Update Twin & Submodel" --> DTR
	P2EDC <-- "Register/Update Twin & Submodel" --> DTR
    P1DS -- "Expose Data" --> P1EDC
	P1EDC -- "Receive Data" --> P1DS
    P1EDC -- "Offer/Exchange Data" --> P2EDC

    %% Data Consumer Flows
    P2EDC -- "Request Data" --> P1EDC
    P2EDC -- "Provide Data" --> P2DS
    P2DS -- "Load Data" --> P2APP
    P2APP -- "Review/Annotate" --> P2DS

    %% Discovery
    P2APP -- "Discover Twin/Model" --> DTR
```

**Description:**
- Each partner has its own Data Source (for persisting and updating 3D data), EDC (for secure data exchange), and Business Application (for creation, review, and annotation).
- The Digital Twin Registry enables discovery and linkage of geometry data across partners.
- Data flows from Partner 1's app to their data source, is registered in the DTR, and exchanged via EDC to Partner 2, where it is consumed and reviewed in their own environment.



## Example Files and Understanding

### Basic Bike Example with 2 Participants

The simplest example of geometry data being shared in the Catena-X ecosystem involves 2 participants. These participants are the OEM and Tier 1. The following example provides a guide for who owns what data and how these data are shared and used. The example consists of a bike, assembled from 2 components. A bike frame and a drive train. The geometry data for these components correspond to 2 STEP files, asm_frame.step and asm_drive.step, respectively. Both can be found in the basic-example directory of this KIT. Both can been seen rendered below.

<div style="display: flex;  justify-content: center; gap: 16px; align-items: flex-start;">
  <img src="./resources/basic-example/img/bike-frame.png" alt="Bike Frame" width="300"/>
  <img src="./resources/basic-example/img/bike-drive-train.png" alt="Bike Drive Train" width="300"/>
</div>
<br>

In this example, the OEM owns the bike, builds the frame, and assemble the bike from components provided by various suppliers. Here, a single suppler is considered, Tier 1, who provides the bike drive train. The diagram below depicts how the geometry data workflow between the OEM and Tier 1 could look, but it is stressed this is only an example, and data sharing workflows will vary in design and complexity.

<br>
<div style="display: flex;  justify-content: center; gap: 16px; align-items: flex-start;">
  <img src="./resources/basic-example/img/bike-2-participants-workflow.jpg" alt="2 Participants Workflow" width="1000"/>
</div>
<br>

Here, the workflow starts on the left and progressed to the right as a function of time.

1. Initially, the OEM provides access to the Digital Twin, which includes the Digital Master Data (DMD) and SingleLevelSceneNode, for the bike by posting the asset on the Digital Twin Registry. The STEP file is included in this and is linked to SingleLevelSceneNode via the Binary Data Exchange. 

2. The Tier 1 can then access and assess the Digital Twin and associated assets via the Digital Twin Registry. These processes usually occur via each counterpart's EDCs, but these are omitted for simplicity. The Tier 1 analyses the geometry data provided by the OEM, in this instance the bike frame, but this could also be a Bauraum or equivalent.

3. The Tier 1 creates their own Digital Twin for the drive train, including the STEP file, linked to SingleLevelSceneNode via the Binary Data Exchange, and iterates on it to meet the OEM's constrains and specifications.

4. When ready, the Tier 1 provides access to their Digital Twin of the drive train. The OEM can then use this data to inspect the Tier 1 component, provide feedback and answer questions. Both parts can be used by both parties to perform DMU Analysis. 

6. The Tier 1 then incorporates feedback from the OEM into their design and continues to iterate. 

7. Once again, when ready, the Tier 1 provides access to their updated Digital Twin of the drive train.

8. Once the OEM is satisfied, the Aspect Model for the combined Frame and Drive Train can be approved. This is the last step in this example.

<br>
<div style="display: flex;  justify-content: center; gap: 16px; align-items: flex-start;">
  <img src="./resources/basic-example/img/bike-frame-and-drive-train.png" alt="Bike frame and drive train combined" width="300"/>
</div>
<br>

In theory, both the OEM and Tier 1 can view each others geometry data throughout the entire workflow, following the 1 up 1 down principal, after the initial sharing of participant's Digital Twin.

#### Table of Data Ownership

<br>
<div style="display: flex;  justify-content: center; gap: 16px; align-items: flex-start;">
<table>
  <tr>
    <th><strong>OEM</strong></th>
    <th><strong>Tier 1</strong></th>
  </tr>
  <tr>
    <td>asm_frame.step</td>
    <td>asm_drive.step</td>
  </tr>
  <tr>
    <td>SLSN_frame_payload.json</td>
    <td>SLSN_drive_payload.json</td>
  </tr>
</table>
</div>
<br>

The table above summarizes who owns what data during evolution of the workflow.

## Associated CX-Standards

### Single Level Scene Node 
urn:samm:io.catenax.single_level_scene_node:1.0.0#

The "Single Level Scene Node" is a core concept in the Catena-X Geometry Aspect Model, providing a standardized way to represent a geometric object and its direct properties within a 3D scene as part of a Digital Twin in Catena-X. Each node encapsulates references to geometry data (such as CAD files or tessellated meshes), transformation information (position, rotation, scale), and metadata. This structure simplifies data exchange and integration across systems, ensuring that each geometric entity can be independently described, linked, and consumed by partners.

For full details, see the Catena-X [Geometry Standard (CX-0156)](https://github.com/catenax-eV/product-standardization-prod/blob/R25.12-release-bundle/standards/CX-0156-Geometry/CX-0156-Geometry.md).


### Masterdata
https://github.com/catenax-eV/product-standardization-prod/blob/R25.12-CX-XXXX-Geometry/standards/CX-0154-MasterDataManagement/CX-0154-MasterDataManagement.md 

The Masterdata standard (CX-0154) is essential as it provides the structured, interoperable foundation for exchanging all relevant product master information—including references and metadata for 3D geometry—across the value chain. It ensures that 3D data is always contextualized with accurate, up-to-date master information, enabling seamless discovery, retrieval, and integration of 3D models in Catena-X. Our 3D standard builds on this by specifying how geometry and related data are referenced, described, and linked within the masterdata framework, ensuring consistency, traceability, and interoperability for all 3D-centric use cases. The 3D/geometry standard can be used in combination with master data, but it is not mandatory—3D data may also be exchanged independently where appropriate.


### Digital Twin Standard
The Digital Twin standard (CX-0002) is fundamental for Catena-X as it defines how assets are digitally represented, uniquely identified, and made discoverable across the network. It provides the architecture and APIs for registering, linking, and accessing digital twins and their aspects (such as 3D geometry, simulation, or master data) in a standardized, interoperable way. This enables seamless integration, traceability, and lifecycle management of 3D information and related data, forming the backbone for all data-driven collaboration and automation scenarios in the ecosystem. In the future, the 3D standard will enable Catena-X participants to communicate 3D data and information directly via digital twins, making 3D data exchange an integral part of the Catena-X dataspace.


### BinaryExchange
The BinaryExchange aspect model is essential for standardized, secure, and interoperable exchange of binary files—such as 3D models—across the Catena-X dataspace. It provides a common structure for describing, referencing, and accessing binary data, including metadata, content type, and access mechanisms via the Dataspace Protocol (DSP).

#### Binary vs. Encoded Data:
Most aspect models, including BinaryExchange, are designed to reference or link to binary files (e.g., via a URI), not to embed the raw file content directly in the aspect payload. However, in some cases—such as for small files, or when direct embedding is required—binary data may be included as a base64-encoded string.

Base64 Encoding:
Base64 encoding converts binary data into a text format, making it safe to include in JSON, XML, or other text-based payloads. This is useful when:

The file must be embedded directly in the aspect model (e.g., for transport in a single message).
The receiving system cannot handle binary payloads natively.
There are constraints on the transport protocol (e.g., HTTP APIs that expect text).
Interoperability and Clarity:
The encoding method (e.g., base64) must be clearly specified in the aspect model’s schema or metadata (such as the contentType property in BinaryExchange). This ensures that all participants know how to decode and use the file data, avoiding misinterpretation or data corruption.


## Notice

This work is licensed under the [CC-BY-4.0](https://creativecommons.org/licenses/by/4.0/legalcode).

- SPDX-License-Identifier: CC-BY-4.0
- SPDX-FileCopyrightText: 2025 Dräxlmaier GmbH & Co. KG
- SPDX-FileCopyrightText: 2025 Schaeffler AG
- SPDX-FileCopyrightText: 2025 Mercedes Benz Group AG
- SPDX-FileCopyrightText: 2025 ZF Friedrichshafen AG
- SPDX-FileCopyrightText: 2025 Contributors to the Eclipse Foundation
