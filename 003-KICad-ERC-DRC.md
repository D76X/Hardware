# ERC & DRC rules

The following cover the basics of ERC and DRC rules in KiCad.

[11 KiCad ERC Tutorial: Running Electrical Rule Check and Exploring Schematic Setup for Rule Checkers  Tech Record](https://www.youtube.com/watch?v=TZ34jARJMVo)


[ERC/DRC common errors and how to use it like TDD // KiCad Sayanee Basu](https://www.youtube.com/watch?v=Ah65M31v87c)  

[Step-by-Step ERC & DRC Checks in KiCad 9.0 | Complete Beginner’s Walkthrough DIY Hideout](https://www.youtube.com/watch?v=OZhVRyuPJuA)  

[Hardware Design With AI Co-Pilot | EP-8 : ERC, DRC, BOM and Gerber File | Ampnics](https://www.youtube.com/watch?v=R1q_x9aNpcQ)  

---

# DRC: kicad annular width (board setup constraints min 0.1000 mm; actual 0.0500 mm)

In KiCad, the Annular Width (or minimum annular ring) constraint defines 
`the smallest allowable copper ring left around a drilled hole on a pad or via`. 
If a pad's copper rim is thinner than this limit, KiCad triggers a Design Rules Check (DRC) error.

## Locating and Adjusting Constraints

- To change or view this setting in KiCad:

Open your PCB layout and go to `File > Board Setup`.
Select Design Rules on the left menu, then click on Constraints.
Look for Minimum annular ring (or annular width) under the copper constraints tab.
Recommended and Typical ValuesDefault KiCad value: `Usually set to 0.10 mm (approx. 3.9 mils)`.

- Standard Manufacturer limit: 

Most low-cost PCB makers (like JLCPCB or PCBWay) require at least 0.15 mm (6 mils).

- IPC standard recommendation: 

0.15 mm to 0.20 mm ensures reliable plating and alignment during manufacturing.

## Fixing Annular Width Errors

- Adjust the constraint: 

Lower the minimum annular width value in your Board Setup if your fabrication house 
supports smaller rings (check their capabilities first).

- Resize pads/vias: 

Increase the overall diameter of the offending vias or pads in your footprint 
properties or net classes so the copper ring surrounding the drill hole satisfies 
the minimum limit.

---

# DRC : clearance violation on a central thermal or ground pad in KiCad

A clearance violation on a central thermal or ground pad in KiCad usually happens when 
the global Design Rules (DRC) require a larger gap than the spacing designed into the 
footprint or between adjacent pins/vias. 

To fix it, lower your global clearance constraints if they are overly strict, 
resize the pad in the footprint editor, or adjust local pad clearance settings.

## Fixing Clearance Violations on Central Pads

- Adjust Global Constraints: 

Go to `File > Board Setup > Design Rules > Constraints` and check if your 
`copper-to-copper clearance` value is larger than what your manufacturer 
actually requires (e.g., lowering from 0.25 mm to 0.15 or 0.20 mm if supported).

- Edit the Footprint Directly: 

Hover over the component, press Ctrl + E to open it in the Footprint Editor, 
double-click the central pad, and reduce its X/Y dimensions slightly if the 
physical copper is too large for the pitch.

- Modify Local Pad Settings: 

Select the central pad, press E to open Pad Properties, and check the Local Clearance 
and Settings tab to see if an override can properly fit your layout rules.

- Check Thermal Reliefs / Zones: 

If the central pad connects to a ground plane, inspect your zone settings to make 
sure thermal spoke connections are not choked or violating neighboring pin clearances.

---

## DRC: KICad clearance violation PTH (clearance 0.2000 mm actual 0.1649 mm) 

A copper item (track, pad, or zone) is closer to the hole edge than your design rules allow 
(required 0.2000 mm, actual 0.1649 mm). This commonly happens with dense footprints like 
USB-C connectors or tight pitch components.

### Fix the ViolationLower 

- Global Constraints: 

Go to `File > Board Setup > Design Rules > Constraints` and lower the `Copper to hole` 
clearance value if your fabrication house supports tighter gaps (e.g., 0.15 mm).

- Override Pad Settings: 

Hover over the offending pad, press E for Pad Properties, and navigate to 
`Local Clearance and Settings` to reduce the clearance for just that specific pad.

- Edit Footprint Library: 

Right-click the footprint, open Footprint Properties, edit the local clearance settings 
in the pad/footprint options, or use a custom footprint override if it is a standard 
part like a USB-C port that manufacturers can safely build.

- Adjust Trace Routing: 

Move nearby tracks further away or reduce the incoming track width so its rounded 
edge stays outside the forbidden clearance ring of the PTH hole.

[Drill hole in copper zone - how to remove clearance?](https://forum.kicad.info/t/drill-hole-in-copper-zone-how-to-remove-clearance/53911)   

---

# DRC : solder mask aperture bridges items with different nets
# Allow bridged solder mask apertures between pads

The purple areas are soldermask expansion where the copper and pcb will be exposed. 
The expansion is to large so it overlaps. 
Right click the footprint and set soldermask expansion to zero.

what is the soldermask expansion for?

To account for printing tolerances. 
Today you should set the expansion to zero and let the manufacturer adjust to best suit their process.

It can be found in the properties of said footprint at clearance overrides and settings directly in the pcb editor.

To fix a "front solder mask aperture bridges items with different nets" error in KiCad, 
right-click the problematic footprint, select Properties (or Footprint Properties), navigate 
to the Clearance Overrides / Local Clearances or Clearance Overrides and Pad Connections tab, 
and change the Solder mask expansion value to 0.

## Why This Happens

- Overlapping Openings: 

The default or custom expansion creates solder mask openings that spill over and touch adjacent 
pads or traces belonging to different nets.

- Zero Setting: S

etting expansion to zero forces the solder mask clearance opening to match the exact size of 
the pad, removing the overlapping purple clearance rings.

## Allow bridged solder mask aperture between pads

To allow a bridged solder mask aperture between pads in KiCad, open the specific footprint properties, 
go to the clearance overrides tab, and check the option to allow bridged apertures. 
This stops design rule check (DRC) errors when fine-pitch pads share a single mask opening.

## How to Enable Bridged Apertures

- Open your PCB layout and right-click the target footprint.
- Select Properties or edit the footprint directly in the library.
- Navigate to the Clearance Overrides and Settings tab.
- Find and check the box for `Allow bridged solder mask apertures between pads`.
- Save the changes to the footprint or update it on the board.

## Why Use This Setting

- Fine-Pitch Components: 

Close-set pads (like on certain ICs or connectors) have gaps smaller than a manufacturer's 
minimum solder mask dam width.

- Error Reduction: 

It bypasses the "front solder mask aperture bridges items with different nets" DRC warning.

- Manufacturing Reality: 

Prevents tiny, fragile slivers of solder mask from peeling off during production when the 
space between pads is too tight.

[Help with error: "Front solder mask aperture bridges items with different nets"](https://www.reddit.com/r/KiCad/comments/1gjmxna/help_with_error_front_solder_mask_aperture/)    

[DRC : solder mask aperture bridges items with different nets](https://forum.kicad.info/t/6-99-drc-fail-solder-mask-aperture-bridges-items-with-different-nets/35311)  

[Allow bridged solder mask apertures between pads](https://forum.kicad.info/t/allow-bridged-solder-mask-apertures-between-pads/40641)  

[What is a Solder Mask Bridge in PCBs?](https://www.allpcb.com/blog/pcb-design/solder-mask-bridge.html)  

---