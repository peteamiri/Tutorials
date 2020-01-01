# The Open Group Architecture Framework (TOGAF)

is an enterprise architecture framework that provides a step by step approach for designing, planning, implementing, and governing an enterprise information technology architecture.

It is typically modeled at four levels:

* Business Architecture
* Application Architecture
* Data Architecture
* Technology (Infrustructure) Architecture

These levels are refered to as Basic TOGAF Architectural domains.

It relies heavily on modularization, standardization, and already existing, proven technologies and products.

##### For more information see

## TOGAF Basic Concepts

The followings are TOGAF basic concepts

* Enterprise Definition
* Enterprise Architecture Domains
* Architect Development Method
* Deliverable, Artifacts, and Building Blocks
* Enterprise Continum
* Archtecture Repository
* Establishing & Maintaining Enterprise Architecture Capability

This document is broken donw into the sections based on the TOGAF basic concepts.

##### For more information see

## Section 1 Enterprise Definition
The section will deal with the followings

* what is TOGAF Stand for
* What is the Architeccture in this context
* What is Enterprise in this context

##### For more information see

## Section 2 Enterprise Architecture Domains

There are four architecture domains:

* `Business Architecture` defines the business strategy, governance, organization, and key business processes

* `Data Architecture` describes the structure of an organization's logical and physical data assets and data management resources

* `Application Architecture` provides a blueprint for the individual applications to be deployed, their interactions, and their relationships to the core business processes of the organization

* `Technology Architecture` (A.K.A. Infrustructre Architecture) describes the logical software and hardware capabilities that are required to support the deployment of business, data, and application services; this includes IT infrastructure, middleware, networks, communications, processing, standards, etc.

* `Secuirty Architecture` is a very important aspect of Architecture that mainly should be part of each of the above domains.

##### For more information see

## Section 3 Architect Development Method (ADM)

Phases within the ADM are as follows:

* `Preliminary Phase`: describes the preparation and initiation activities required to create an Architecture Capability including customization of the TOGAF framework and definition of Architecture Principles

* `Phase A`: Architecture Vision describes the initial phase of an architecture development cycle
It includes information about defining the scope of the architecture development initiative, identifying the stakeholders, creating the Architecture Vision, and obtaining approval to proceed with the architecture development.

* `Phase B`: Business Architecture describes the development of a Business Architecture to support the agreed Architecture Vision

* `Phase C`: Information Systems Architectures describes the development of Information Systems Architectures to support the agreed Architecture Vision

* `Phase D`: Technology Architecture describes the development of the Technology Architecture to support the agreed Architecture Vision

* `Phase E`: Opportunities & Solutions conducts initial implementation planning and the identification of delivery vehicles for the architecture defined in the previous phases

* `Phase F`: Migration Planning addresses how to move from the Baseline to the Target Architectures by finalizing a detailed Implementation and Migration Plan

* `Phase G`: Implementation Governance provides an architectural oversight of the implementation

* `Phase H`: Architecture Change Management establishes procedures for managing change to the new architecture

* `Requirements` Management examines the process of managing architecture requirements throughout the ADM

##### For more information see

## Section 4 Deliverable, Artifacts, and Building Blocks

* A deliverable is a work product that is contractually specified and in turn formally reviewed, agreed, and signed off by the stakeholders.
  - Deliverables represent the output of projects and those deliverables that are in documentation form will typically be archived at completion of a project, or transitioned into an Architecture Repository as a reference model, standard, or snapshot of the Architecture Landscape at a point in time.

* An artifact is an architectural work product that describes an aspect of the architecture
  - Artifacts are generally classified as catalogs (lists of things), matrices (showing relationships between things), and diagrams (pictures of things). Examples include a requirements catalog, business interaction matrix, and a use-case diagram. An architectural deliverable may contain many artifacts and artifacts will form the content of the Architecture Repository.

* A building block represents a (potentially re-usable) component of enterprise capability that can be combined with other building blocks to deliver architectures and solutions
  - Building blocks can be defined at various levels of detail, depending on what stage of architecture development has been reached. For instance, at an early stage, a building block can simply consist of a name or an outline description. Later on, a building block may be decomposed into multiple supporting building blocks and may be accompanied by a full specification. Building blocks can relate to "architectures" or "solutions".

    - Architecture Building Blocks (ABBs) typically describe required capability and shape the specification of Solution Building Blocks (SBBs); for example, a customer services capability may be required within an enterprise, supported by many SBBs, such as processes, data, and application software

    - Solution Building Blocks (SBBs) represent components that will be used to implement the required capability; for example, a network is a building block that can be described through complementary artifacts and then put to use to realize solutions for the enterprise

##### For more information see

## Section 5 Enterprise Continum

Enterprise Continum is mainly is a view of Enterprise Repository or simply `virtual repostiory` that provides a design from a very generic to  very specifc architecture. It is intwnded to facilitate a better reuse of the architecture (design).

The simplest way of thinking of the Enterprise Continuum is as a `virtual repository` of all the architecture assets - models, patterns, architecture descriptions, and other artifacts - that exist both within the enterprise and in the IT industry at large, which the enterprise considers itself to have available for the development of architectures for the enterprise.

##### For more information see


## Section 6 Archtecture Repository

The major components within an Architecture Repository are as follows:

* The Architecture Metamodel describes the organizationally tailored application of an architecture framework, including a metamodel for architecture content

* The Architecture Capability defines the parameters, structures, and processes that support governance of the Architecture Repository

* The Architecture Landscape is the architectural representation of assets deployed within the operating enterprise at a particular point in time - the landscape is likely to exist at multiple levels of abstraction to suit different architecture objectives

* The Standards Information Base (SIB) captures the standards with which new architectures must comply, which may include industry standards, selected products and services from suppliers, or shared services already deployed within the organization

* The Reference Library provides guidelines, templates, patterns, and other forms of reference material that can be leveraged in order to accelerate the creation of new architectures for the enterprise

* The Governance Log provides a record of governance activity across the enterprise

* The Architecture Requirements Repository provides a view of all authorized architecture requirements which have been agreed with the Architecture Board

* The Solutions Landscape presents an architectural representation of the SBBs supporting the Architecture Landscape which have been planned or deployed by the enterprise

##### For more information see

## Section 7 Establishing & Maintaining Enterprise Architecture Capability

## Resources

* [TOGAF 9.2](https://pubs.opengroup.org/architecture/togaf9-doc/arch/)
* [Wiki](https://en.wikipedia.org/wiki/The_Open_Group_Architecture_Framework)
* [Blog](http://www.mikethearchitect.com/togaf/)
* [Simple Description](https://setandbma.wordpress.com/2011/01/25/what-is-togaf-without-jargon/)
* [Articke](https://www.developer.com/java/ent/article.php/3374171/TOGAF-Establishing-Itself-As-the-Definitive-Method-for-Building-Enterprise-Architectures-in-the-Commercial-World.htm)
* [TOGAF Summary](http://wiki.glitchdata.com/index.php?title=TOGAF_Summary)
* [Togaf](https://github.com/pankajchopra/togaf)
* [TOGAF Blog](http://togaf9certprep.blogspot.com/)
* [TOGAF](https://www.visual-paradigm.com/guide/togaf/what-is-togaf/)
* [TOGAF](https://www.visual-paradigm.com/tutorials/togaf-adm-tool-for-enterprise-architecture.jsp)
* [TOGAF](https://www.visual-paradigm.com/features/togaf-adm-tools/)
* [Summary](https://www.visual-paradigm.com/guide/togaf/togaf-91-framework/)
* [Article](https://www.ibm.com/developerworks/rational/library/jan07/temnenco/index.html)
* [Introduction](https://medium.com/@anioko/how-to-use-togaf-framework-for-requirement-gathering-part-1-b4dc5e1efca1)
* [sOME vIDEO](https://www.goodelearning.com/courses/enterprise-architecture/togaf-9-foundation/what-is-togaf)
* [Summary](https://www.archimetric.com/what-is-togaf/)
* [Exam Summary](http://www.enterprise-architecting.com/eaex/togaf.aspx)
* [Summary](http://www.togaf.com/admref/admreference.html)
* [Goof Overview](https://www.visual-paradigm.com/guide/togaf/what-is-togaf/)
* [TOGAF ADM](https://www.visual-paradigm.com/guide/togaf/togaf-adm-tutorial/)




# Youtube Resources
* [Course -1](https://www.youtube.com/watch?v=yGWn0qKtS7U&list=PLUDQ1dvtmiWKuB9L1QHYVDoFV5zmLSOi_)
# Archimate
