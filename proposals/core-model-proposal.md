
A Data Model for GDPR Compliance Management
===========================================

Implementing a GDPR solution involves people, processes, documentation and a technical implementation. All of these things need to be held together in a cohesive fashion in order to achieve and maintain compliance. One of the initial key activities is to audit the state of the business so that the correct technical and process solutions can be implemented. The results of this audit are likely to be word documents or maybe graphical documents such as Visio Diagrams. While this is useful, we think that in addition, or instead of this kind of document, the result of the audit should be in data.  

Creating data as the result of the audit offers several properties. The data can be rendered into documentation, it can be used to drive the implementation phase, it can be processed in order to provide greater understanding about the organisation, data flow and data compliance.

Further, rather than having many different data models of this domain (by model we mean types and property types), having a community model based on open standards means that once an organisation has a data that conforms to that model it can make use of all of the tools in the community for deriving value from that data.  

To facilitate this we have defined an open standards based model that can be used to capture the state of an organisation in respect to GDPR compliance.  

Scope
=====

This model is designed to be simple and easy to use, and as with any model its likeness to reality will be broken and misaligned in places. This model serves a purpose to improve an organisations understanding of systems, data, consent in relation to data processing activities, in order to improve their ability to be compliant with GDPR. It is not designed to allow the complete, accurate, modelling of organisations.  

The Model
=========

The model is broken down into types and property types. For each type we provide a description, an identifier, and list of properties that may, or must, be on instances of that type.

Logical Overview
----------------

The following high level diagram captures the core types and relationships of the model.




Identification Scheme
---------------------

To help interoperability and ensure clarification of concept descriptions, we use URIs as the means to identify the subjects we are defining. All identifiers begin with the following prefix:

http://data.gdpr-open.org/gdpr/schema

and an example of the full URI for the person concept is:

http://data.gdpr-open.org/gdpr/schema/Person

The followind types define a name, an identifier and the set of properties that instances of the type can or must have. Note that some properties are reference properties. Reference properties are ones that point at (or reference) other objects. When defining a reference property we indicate the allowed type of the referenced object. 

Organisational Unit
-------------------

Name: Organisational Unit
Identifier: http://data.gdpr-open.org/gdpr/schema/Orgunit

An organisational unit is an common abstract concept for anything from a person to a company. It is often an actor in a process, or has legal responsibilities.

Orgnisational Unit is a super type of other types such as Person, Company, State, County, Government and Department. Some of these subtypes are defined below, and additional ones can be added. The rest of this model only uses this super type where it is the target of a reference property.

Person
------

Name: Person
Identifier: http://data.gdpr-open.org/gdpr/schema/Person

A single individual. A uniquely identifiable person, living or dead. 

Company
-------

Name: Company
Identifier: http://data.gdpr-open.org/gdpr/schema/Company

A legal entity that is registered and has a company number.

Department
----------

Name: Department
Identifier: http://data.gdpr-open.org/gdpr/schema/Department

A group within a company. Often responsible for some function, such as HR, IT. Often has a leader.

Consent
-------

Name: Consent
Identifier: http://data.gdpr-open.org/gdpr/schema/Consent

The notion of consent is that a user has given their consent for a given set of data to be used for a spefic processing activity. This concept defines the consent between a set of data and a business process. A consent is managed by a system and collected by a system. A consent also has one or more human readable descriptions that are displayed to the user.

System
------

Name: System
Identifier: http://data.gdpr-open.org/gdpr/schema/System

A system is a software application that stores and processes data. It is connected with datatypes; those it stores, receives and sends out, and with business processes that it implements. 

Data Type
---------

Name: Data Type
Identifier: http://data.gdpr-open.org/gdpr/schema/Datatype

A datatype is a way to describe types of discrete entities that are contained within a system. This could correlate with tables in a relational database, or the logical resources exposed by a REST API. A DataType should describe the list of property types that may be found on instances of that type.


Property Type
-------------

Name: Property Type
Identifier: http://data.gdpr-open.org/gdpr/schema/Propertytype

A datatype is a way to describe types of discrete entities that are contained within a system. This could correlate with tables in a relational database, or the logical resources exposed by a REST API. A DataType should describe the list of property types that may be found on instances of that type.


Business Process
----------------

Name: Business Process
Identifier: http://data.gdpr-open.org/gdpr/schema/BusinessProcess

Processing Activity
===================

Name Processing Activity
Identifier: http://data.gdpr-open.org/gdpr/schema/ProcessingActivity

Any computation that uses data in order to support a business process. Such as process could be manual or automated. It includes, sending a monthly newsletter, analysis of purchasing habits, and access to a GDPR portal.

Role
----

Name: Role
Identifier: http://data.gdpr-open.org/gdpr/schema/Role

A role is set of responsibility undertaken by an individual or organisational unit. 

As well as defining the type, we also define a set of instances that are specific to GDPR modelling. 

The following instances of this vocabulary are defined:

GDPR Compliance Officer
+++++++++++++++++++++++

Name: GDPR Compliance Officer
Identifier: http://data.gdpr-open.org/gdpr/role/gdpr-compliance-officer


Data Security Officer
+++++++++++++++++++++

Name: Data Security Officer
Identifier: http://data.gdpr-open.org/gdpr/role/data-security-officer


Data Category
-------------

Name: Data Category
Identifier: http://data.gdpr-open.org/gdpr/schema/Datacategory

This type is used for defining a controlled vocabulary of how senstive and critical data is, were it to be compromised. 

The following vocabulary terms are some basic values that can be used to categorize data importance.

Critical
++++++++

Name: Critical
Identifier: http://data.gdpr-open.org/gdpr/datacategory/critical

Data classed as critical means that the loss of this data would have critical detremental affects on the data subject. Examples being: health data, bank account access codes, CC details. 

Severe
++++++

Name: Severe
Identifier: http://data.gdpr-open.org/gdpr/datacategory/severe

Data classed as critical means that the loss of this data would have severe detremental affects on the data subject. Examples being: shopping history, credit ratings, home address, family photos, personal correspondance, partial payment details.

Inconvenient
++++++++++++

Name: Inconvenient
Identifier: http://data.gdpr-open.org/gdpr/datacategory/inconvenient

Data classed as inconvenient means that the loss of this data would be inconvenient for the data subject. Examples being: email address. 

Regulation
----------

Name: Regulation
Identifier: http://data.gdpr-open.org/gdpr/schema/Regulation

A regulation is a statutary document that consists of a numbers of articles that together provide a set of rights to citizens.  

We define here GDPR as a regulation for convenience.

GDPR
++++

Name: GDPR
Identifier: http://data.gdpr-open.org/gdpr/datacategory/gdpr

The EU GDPR as defined by: URL to the PDF.

Article
-------

Name: Article
Identifier: http://data.gdpr-open.org/gdpr/schema/Article

Regulations consist of articles. An article can be part of one regulation. Each article is pertinent to one or more rights.

See the following document for all GDPR articles and the rights to which they are relevant.

Right
-----

Name: Right
Identifier: http://data.gdpr-open.org/gdpr/schema/Right

A right is a idea about what a person can expect from government and commercial actors in the society in which they live. 

There are several core rights in GDPR and we have defined them as such:

Right to Access
+++++++++++++++

Name: Right To Access
Identifier: http://data.gdpr-open.org/gdpr/right/right-to-access

Right to Erasure
++++++++++++++++

Name: Right to Erasure
Identifier: http://data.gdpr-open.org/gdpr/right/right-to-erasure

Right to Rectification
++++++++++++++++++++++

Name: Right To Rectification
Identifier: http://data.gdpr-open.org/gdpr/right/right-to-rectification

Right to Informed
+++++++++++++++++

Name: Right To Be Informed
Identifier: http://data.gdpr-open.org/gdpr/right/right-to-be-informed

Right to Consent
++++++++++++++++

Name: Right To Consent
Identifier: http://data.gdpr-open.org/gdpr/right-to-consent


Complete Model in RDF
=====================

The complete model can be found as JSON-LD, and RDF NTriples. 

// todo

The RDF schema for the model can be found here.

// todo


Example 1
=========

The following example shows how a retail business that sells mobile phones might look when represented using the GDPR semantic data model.








