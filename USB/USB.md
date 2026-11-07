# USB Design

[How to route USB data lines on a PCB Predictable Designs with John Teel](https://www.youtube.com/watch?v=Itsrdc8tX7M&t=1s)  

---

# 90 ohm differential impendance traces

[Why 2-Layer PCBs Break Under Pressure — Return Currents, Ground Integrity & When to Move to 4 Layers Tech Explorations](https://www.youtube.com/watch?v=8O0vYxu8xHw&t=43s)  

# 90 ohm differential impendance pair on a standard 2-layer PCB

- on a standard 1.6 mm F4 2-layers PCB the dielectric height is approximaly 1.48 mm
- to achieve 90 ohm for a USB differential pair you need a MICROSTRIP approximally 1.12 mm wide trace for each D- and D+
- the spacing between the traces must be at least 0.15 mm
- therefore the overall size of the D+/D- pair trace is: (1.12 * 2 + 0.15) mm = 2.39 mm
- this might be eccessive for some projects, i.e. PCB the size of a thumb-drive

# 90 ohm differential impendance pair on a standard 4-layer PCB

> SGPS = Signal-Ground-Power-Signal
- on a standard 1.6 mm F4 4-layers PCB the dielectric height is approximaly 0.2 mm in a standard SGPS stack
- to achieve 90 ohm for a USB differential pair you need a MICROSTRIP approximally 0.26 mm wide trace for each D- and D+

## Notes

- these are indicative figures, the exact values depends on the choice of the stack and the dialectric properties

# CPWG: Coplaner Waveguide with Ground
> Workaround to achieve a 90 ohm differential impendance pair on a standard 2-layer PCB

- add ground copper on the same layer as the signal traces at both sides with a controlled gap
- a coplanar ground reduces the effective dielectric height of the nearby trace
- this allows to narrow the trace width down to 0.24 mm to achieve the target 90 ohn impendance
- it requires the coplanar gap to be maintained consistently accross the entire trace length
- it requires the bottom layer to remain largerly unrouted beneath the differential pair traces
- stitching vias must be used to connect the coplanar ground to the bottom GRN

---

- USB 2.0 requires a differential impedance od 90 Ohm on the D+ and D- lines
- achieving this on a 2-layer board is possible but the trace width will be MUCH larger that on a 4-layer board
- Low-Speed  USB = 1.5Mb/s
- Full-Speed USB = 12  Mb/s
- High-Speed USB = 480 Mb/s

---

