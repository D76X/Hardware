# FreeCAD FAQ

# What is the difference between an assembly project and a BIM/Architecture project in FreeCAD?

The core difference between an **Assembly project** and a **BIM/Architecture project** in FreeCAD comes down to **what you are building, how the objects interact, and the data standards used**. They target entirely different industries (Mechanical Engineering vs. Architecture, Engineering, & Construction).

---

### 1. Assembly Project (Mechanical / Product Design)

An assembly project focuses on **multi-part mechanical systems, mechanisms, and manufacturing tolerances**.

* **Primary Workbenches:** `Assembly` (built-in solver) or add-ons like `A2plus`, `Assembly3`, or `Assembly4`.
* **How it works:** You design individual parts independently (typically using `PartDesign` and `Sketcher` by drawing 2D profiles and extruding, revolving, or pocketing solid geometry). You then bring those separate part files or bodies into an assembly file and tie them together using geometric constraints (e.g., *Coincident, Concentric, Distance, Parallel*).
* **Key Focus:**
* **Kinematics:** Simulating physical movement, rotation, and mechanical joints (hinges, sliders, gears).
* **Interference & Clearance:** Checking if mechanical components collide or fit tightly together.
* **Bill of Materials (BOM):** Generating manufacturing parts lists, fastener counts, and step-by-step engineering drawings via `TechDraw`.

---

### 2. BIM / Architecture Project (AEC)

A BIM (Building Information Modeling) project focuses on **buildings, infrastructure, spatial relationships, and asset lifecycles**.

* **Primary Workbench:** `BIM` (which incorporates underlying architectural tools formerly split into the `Arch` and `Draft` workbenches).
* **How it works:** Instead of assembling loose mechanical parts, you model elements with semantic and spatial intelligence—such as `Walls`, `Slabs`, `Columns`, `Beams`, `Windows`, and `Doors`. Components are context-aware; for example, inserting a window into a wall automatically cuts an opening and binds the objects spatially.
* **Key Focus:**
* **Hierarchical Spatial Containers:** Structures are organized logically from top to down: `Site` $\$rightarrow `Building` $\$rightarrow `Floor / Building Storey` $\$rightarrow `Spaces/Rooms`.
* **Data & Standards (IFC):** Heavily reliant on Industry Foundation Classes (`.ifc`), ensuring that every object carries metadata regarding material properties, fire ratings, structural behavior, and costs.
* **Documentation & Quantities:** Extracting floor plans, automatic section cuts, elevations, and quantitative material take-offs/schedules.



---

### Quick Comparison Summary

| Feature | Assembly Project | BIM / Architecture Project |
| --- | --- | --- |
| **Target Domain** | Mechanical Engineering & Product Design | Architecture & Construction (AEC) |
| **Main Workbenches** | `Assembly`, `PartDesign`, `Sketcher` | `BIM`, `Draft` |
| **Core Components** | Gears, brackets, fasteners, machined parts | Walls, roofs, windows, stairs, structural grids |
| **Relationship Logic** | Geometric constraint solvers (axes, faces, distance bounds) | Spatial containment hierarchies and parametric object intelligence |
| **Primary Output / Export** | STEP, IGES, exploded mechanical drawings, BOMs | IFC (Industry Foundation Classes), floor plans, schedules |

---

# What is the difference between the "Part Design" and "Part" menu items in FreeCAD 1.1 ?

The primary difference between the **Part** and **Part Design** workbenches in FreeCAD 1.1 
lies in their **modeling philosophy**, **data structure**, and **intended workflow**.

---

### Core Differences

| Feature | **Part Design** Workbench | **Part** Workbench |
| --- | --- | --- |
| **Primary Workflow** | **Feature-Based Parametric Modeling** (similar to SolidWorks or Fusion 360) | **Constructive Solid Geometry (CSG)** & Surface Modeling |
| **Container Concept** | Built strictly around the **`Body` container**. All features inside a single `Body` must form a single contiguous solid. | **No required container concept**. Shapes and solids exist independently in the model tree. |
| **History & Timeline** | **Linear Timeline**: Operations act sequentially as features inside the `Body` (e.g., Pad $\rightarrow$ Pocket $\rightarrow$ Fillet). | **Dependency Tree**: Combining objects (e.g., Union, Cut) generates nested child nodes under new Boolean objects. |
| **Booleans** | **Implicit**: Operations like Pocket (cut) or Additive Primitive automatically integrate into the active Body. | **Explicit**: You create two separate solids and manually run Boolean Operations (Fuse, Cut, Intersect). |
| **Sketch Integration** | Uses 2D **Sketcher** sketches attached to planes or faces of the current body. | Uses standalone sketches, primitives (cubes, cylinders), or surfaces extruded into shapes. |
| **Assembly Flexibility** | Designed to create **single, individual mechanical components** to later assemble using Assembly workbenches. | Can combine multiple non-touching objects, boolean complex shapes, and perform surface/sheet operations directly. |

---

### Key Workflows Explained

#### 1. Part Design Workbench (The "Body" Workflow)

* **How it works:** You create a `Body` object, draw a 2D sketch using constraints, and apply a 3D operation like **Pad** (extrude) or **Revolve**. Subsequent sketches/features (Pockets, Fillets, Chamfers) incrementally modify that single piece of material.
* **Best used for:** Complex mechanical parts, 3D printing components, and models requiring sequential modification steps.

#### 2. Part Workbench (The "CSG & Surface" Workflow)

* **How it works:** You build geometry using primitive 3D shapes (cubes, cylinders, spheres) or extruded 2D wires. You then position these shapes independently and execute explicit **Boolean Operations** (Fuse, Cut, Common) to combine them into the desired geometry.
* **Best used for:** Simple geometries, combining multiple non-connected parts, surface modeling, 2D/3D offsets, and working with geometry imported from other software.

---

### Important Usage Tip

Avoid directly mixing tools from both workbenches on the same geometry without using dedicated bridging tools (such as *ShapeBinders* or *Base Features*), as mixing the linear history of Part Design with the tree structure of Part can break model references.

[Workbench Choice in FreeCAD, Part Design vs Part?](https://www.youtube.com/watch?v=ffNOA9XmaU8&utm_source=gemini)
This video provides a direct visual comparison of how workflows differ between the Part Design and Part workbenches when modeling objects in FreeCAD.

---

# What is the 3Dconnexion in FreeCAD?

[FreeCAD 1.x Kurs - Einstellungen Dr. Klipper](https://www.youtube.com/watch?v=bPfzHgd_Zkk)  

[FreeCAD and 3Dconnexion Boost your workflow](https://3dconnexion.com/uk/applications/freecad-freecad/)  

[FreeCAD + 3Dconnexion Optimiere deinen Workflow](https://3dconnexion.com/de/applications/freecad-freecad/)  

---

# How do I set FreeCAD to show a Plane from above?

To view a plane from above in FreeCAD, switch to the Top camera view using the shortcut 2 (or View > Standard views > Top / the Top view toolbar icon). [1] (https://www.youtube.com/watch?v=QPZg2Y8Z8_w), [2] (https://www.youtube.com/watch?v=rxkmMTXDkZk)

Making the Plane Visible (If Needed)

• Origin planes: Expand your Body in the Model tree, select Origin, and press Spacebar (or click the eye visibility icon) to show the XY, XZ, and YZ planes.
• Datum planes: Select the datum plane in the Model tree and press Spacebar if it is hidden.
• Working plane (Draft workbench): Set the working plane to Top (XY) in the Draft plane controls if you are working in Draft. [1] (https://www.youtube.com/watch?v=vSqvENcXSvY&vl=en), [2] (https://forum.freecad.org/viewtopic.php?style=3&t=90790), [3] (https://www.youtube.com/watch?v=0AXm6Our05I)

Switching to Top View

• Press 2 on your keyboard to align the camera directly above the XY plane.
• Click the Top view button on the view toolbar or choose View > Standard views > Top.
• Press V, F (or click Fit all) if your plane or model is off-screen. [1] (https://www.youtube.com/watch?v=rxkmMTXDkZk), [2] (https://www.youtube.com/watch?v=QPZg2Y8Z8_w)

---