
# CPWG: Coplaner Waveguide with Ground

[CPWG: Coplaner Waveguide with Ground](https://share.gemini.google/r7GyEd47uC2q)

Achieving a target differential impedance like **90 $\Omega$** (standard for USB 2.0/3.x high-speed pairs) 
on a standard 2-layer FR-4 board is notoriously difficult using standard microstrips. Standard 2-layer boards 
feature a thick dielectric core (typically $\approx 1.5\text{ mm} / 60\text{ mils}$), which forces standard 
microstrip trace widths to be excessively wide—often over 1.0–1.5 mm—to achieve target impedances.

**Coplanar Waveguide with Ground (CPWG)**—also called Grounded Coplanar Waveguide (GCPW)—solves this by shifting 
field containment from the distant bottom layer to the top layer.

---

## Why Standard Microstrips Fail on 2-Layer FR-4

In a standard edge-coupled microstrip configuration, trace impedance is largely governed by:

* Trace width ($W$)
* Substrate thickness ($h$)
* Substrate dielectric constant ($\varepsilon_r \approx 4.2 - 4.5$ for FR-4)

On a **4-layer or 6-layer stackup**, the dielectric height ($h$) from Layer 1 to the Layer 2 ground 
plane is thin (typically $0.1\text{ mm} - 0.2\text{ mm}$). This allows reasonable trace widths 
($\approx 0.12\text{ mm} - 0.2\text{ mm}$) and gaps ($\approx 0.12\text{ mm}$) to reach $90\ \Omega$ 
differential impedance ($Z_{\text{diff}}$).

On a **2-layer PCB ($h \approx 1.5\text{ mm}$)**:

1. To maintain $90\ \Omega$ differential impedance with a distant ground reference, trace widths ($W$) must expand drastically.

2. Wide traces consume excessive board real estate and cannot physically route into fine-pitch component pads (e.g., USB connectors, IC pins, ESD protection diodes).

3. Attempting to force narrow traces with large gaps leads to weak coupling and uncontrolled impedance, spiking crosstalk and EMI.

---

## How CPWG Solves the 2-Layer Impedance Problem

CPWG introduces coplanar ground pours alongside the signal traces on the **top layer**, 
separating them by a narrow dielectric gap ($S$).

By adding co-planar ground reference floods:

* **Capacitance increases locally:** Electric field lines terminate laterally into the adjacent top-layer ground pour rather than solely down toward the distant bottom plane.
* **Trace widths shrink:** The additional side-coupling allows you to reduce trace width ($W$) down to manufacturable, routing-friendly dimensions (e.g., $0.2\text{ mm} - 0.35\text{ mm}$) while still landing on target for $90\ \Omega$ differential impedance.
* **Tight field containment:** Radiated emissions and susceptibility to nearby signals drop significantly.

---

## Differential CPWG (Diff-CPWG) Geometry

For a $90\ \Omega$ differential pair (such as USB D+/D-), the total differential impedance $Z_{\text{diff}}$ depends on five variables:

$$\begin{aligned} W &\quad \text{Trace width} \\ S &\quad \text{Inter-trace gap (between D+ and D-)} \\ G &\quad \text{Ground gap (between signal trace and top ground pour)} \\ h &\quad \text{Substrate thickness (e.g., 1.6 mm)} \\ t &\quad \text{Copper thickness (e.g., 1 oz } \approx 35\ \mu\text{m)} \end{aligned}$$

```
   Top Ground       Signal D+      Signal D-       Top Ground
  +-----------+    +---------+    +---------+    +-----------+
  |  Copper   |  G | Copper  |  S | Copper  |  G |  Copper   |
  +-----------+    +---------+    +---------+    +-----------+
  ============================================================  <- Dielectric (h ~ 1.5mm)
  +-----------------------------------------------------------+
  |                   Bottom Ground Plane                     |
  +-----------------------------------------------------------+

```

### Typical 2-Layer FR-4 Parameter Window ($90\ \Omega$ $Z_{\text{diff}}$)

| Parameter | Approx Value (1.6 mm FR-4) |
| --- | --- |
| **Trace Width ($W$)** | $0.25\text{ mm} - 0.35\text{ mm}$ ($10 - 14\text{ mil}$) |
| **Trace-to-Trace Gap ($S$)** | $0.15\text{ mm} - 0.20\text{ mm}$ ($6 - 8\text{ mil}$) |
| **Trace-to-Ground Gap ($G$)** | $0.15\text{ mm} - 0.25\text{ mm}$ ($6 - 10\text{ mil}$) |
| **Bottom Reference** | Solid Ground Plane on Layer 2 |

---

## Critical Layout Guidelines for CPWG Implementation

1. **Via Fence (Via Stitching):**
Place ground vias along the top coplanar ground flood on both sides of the differential pair.
* **Spacing ($d$):** Keep via-to-via pitch less than $\lambda / 10$ at the highest frequency harmonic (typically $\le 1.5\text{ mm} - 2.0\text{ mm}$ apart).
* **Distance to edge:** Keep vias close to the copper edge facing the signal trace. This suppresses parasitic parallel-plate waveguide modes between the top coplanar ground and the bottom ground plane.


2. **Maintain Constant Coplanar Clearance ($G$):**
Ensure the top ground pour maintains an exact, uniform distance ($G$) along the entire length of the traces. Auto-fill polygons often leave uneven serrated edges around pads—use explicit clearance keepouts or dedicated guard traces tied to ground.
3. **Continuous Bottom Ground Plane:**
Do not break or route traces on the bottom layer directly beneath the CPWG pair. Even though top-layer coupling is strong, the bottom layer carries significant return current.
4. **2D/3D Field Solver Required:**
Standard empirical microstrip formulas (like Wheeler or Hammerstad) do **not** accurately calculate CPWG impedance due to the complex multi-directional field distribution. Always use a 2D BEM/FEM field solver (e.g., KiCad's internal calculator, Altium's Simbeor solver, or Saturn PCB Toolkit) to finalize $W$, $S$, and $G$ for your board shop's specific stackup.