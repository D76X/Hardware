
[FreeCAD BIM Beginner Tutorial | Create a Garage Building FCB Lounge](https://www.youtube.com/watch?v=WZHyUBfdgJA)   

[Tracing Walls from an Image Floor Plan in FreeCAD BIM FCB Lounge](https://www.youtube.com/watch?v=65Q_4uSTRPM)  

--

# Yorik Van Havre

Construction Management with Peter has used this as its basis.

[Yorik Van Havre](https://www.linkedin.com/in/yorik/)

[BIM with FreeCAD by Yorik van Havre](https://www.youtube.com/playlist?list=PLmKdGVtV5Vnt2cj4IZIv9FM39QHaE1ZaU)  

---

# What is a IFC Schema?

An `IFC Schema (Industry Foundation Classes schema)` is an open, vendor-neutral data model 
and standardized language used in Building Information Modeling (BIM) to describe, store, 
and exchange building and infrastructure data across different software applications. 

[1] (https://www.youtube.com/watch?v=bwM8p98m2Bk), 
[2] (https://revizto.com/resources/blog/what-is-ifc-format), 
[3] (https://www.bimcollab.com/en/resources/blog/what-is-ifc/)

Managed by `buildingSMART` and published as an international standard (`ISO 16739-1`, 
currently at version `IFC 4.3`), it acts as a universal translator so that architectural, 
engineering, and construction tools can share information without data loss or proprietary lock-in. 

[1] (https://en.wikipedia.org/wiki/Industry_Foundation_Classes), 
[2] (https://www.youtube.com/watch?v=rXLOQ-mqebg), 
[3] (https://revizto.com/resources/blog/what-is-ifc-format)

## Core Structure of the IFC Schema

The IFC schema is built on an object-oriented data model defined using the `EXPRESS data specification language` `(ISO 10303-11)`. It organizes everything in the built environment through several key 
architectural components: 

[1] (https://www.linkedin.com/pulse/ifc-schema-explained-sidath-jayasingha-cstrf)

- Four-Layered Modular Architecture: 
	The schema flows downward in a strict one-way dependency ladder:
	
	1. Resource Layer: Basic data types, units, geometry, and materials.
	
	2. Core Layer: Fundamental concepts, relationships, and root classes (IfcRoot).
	
	3. Interoperability Layer: Generic product extensions shared across building disciplines (e.g., IfcWall, IfcDoor, IfcWindow).
	
	4. Domain Layer: Specialized extensions for specific engineering sectors (such as architecture, structural, HVAC, electrical, and civil/infrastructure like roads and railways). 
	
	[1] (https://www.youtube.com/watch?v=q_7i4l7KSeI), 
	[2] (https://www.linkedin.com/pulse/ifc-schema-explained-sidath-jayasingha-cstrf), 
	[3] (https://www.domosoft.ch/blog/the-ifc-schema-structure-and-entities-part-2/), 
	[4] (https://www.bimcollab.com/en/resources/blog/what-is-ifc/), [5] (https://revizto.com/resources/blog/what-is-ifc-format)

- Inheritance & Classes: 
Entities inherit properties from parent classes. For example, `IfcRoot` is the base abstract class that gives almost every identifiable object a globally unique identifier (GlobalId / GUID), name, and description. 

[1] (https://www.domosoft.ch/blog/the-ifc-schema-structure-and-entities-part-2/), 
[2] (https://www.linkedin.com/pulse/ifc-schema-explained-sidath-jayasingha-cstrf), 
[3] (https://www.youtube.com/watch?v=q_7i4l7KSeI)

- Spatial Breakdown Structure: 
Projects are organized hierarchically: `IfcProject → IfcSite → IfcBuilding → IfcBuildingStorey → IfcSpace`.
Every physical component is mapped into this spatial backbone. 

[1] (https://docs.speckle.systems/developers/data-schema/connectors/ifc-schema), 
[2] (https://quadrihelp.trimble.com/Quadri-for-Windows/IFC/Understanding-IFC), 
[3] (https://www.domosoft.ch/blog/the-ifc-schema-structure-and-entities-part-2/)

- Property Sets (Psets) and Relationships: 
Custom or standardized metadata—such as fire ratings, load-bearing status, or manufacturer details—
are attached via Property Sets (Pset_) and linked via explicit relationship classes (inheriting from
IfcRelationship). 

[1] (https://www.bimcollab.com/en/resources/blog/what-is-ifc/), 
[2] (https://www.linkedin.com/pulse/ifc-schema-explained-sidath-jayasingha-cstrf), 
[3] (https://docs.speckle.systems/developers/data-schema/connectors/ifc-schema)

## Common File Encodings

An IFC schema can be serialized into several physical file formats for storage or transfer:

- `.ifc (IFC-SPF)`: An ASCII text-based Step Physical Format file commonly used for detailed BIM exchanges.
- `.ifcXML`: An XML-encoded representation suited for web and database integrations.
- `.ifcZIP`: A compressed archive format used to reduce the size of large building models. 

[1] (https://www.youtube.com/watch?v=bwM8p98m2Bk), 
[2] (https://www.bimcollab.com/en/resources/blog/what-is-ifc/)

---



