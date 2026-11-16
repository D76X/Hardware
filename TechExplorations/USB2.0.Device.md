
# Tech Explorations

[Udemy Peter Dalmaris](https://www.udemy.com/user/peterdalmaris/) 

---

## Board 02: 4-Layer Design

[Design a smart USB drive with kicad - Tech Explorations](https://connect.techexplorations.com/so/smart-usb-thumb-drive-with-kicad)

---

## Udemy Course - Design a smart USB thumb drive

[KiCad Advanced: Design a smart USB thumb drive - Udemy](https://www.udemy.com/course/kicad-advanced-design-a-smart-usb-thumb-drive/?referralCode=57199C5E61F1E8D99584&couponCode=25BBPMXINACTIVE)  

---

# Video 03

[USB 2.0 Signal Integrity — Common Mode Noise, ESD Protection, Eye Diagrams & Component Selection Tech Explorations](https://www.youtube.com/watch?v=xQ76F06EhfU)

1. Common Mode Noise (CMN), and how to suppress it
2. Electrostatic Dischange Protection (EDP) on the USB lines
3. The Eye Diagram

---

# Video 02

[Why 2-Layer PCBs Break Under Pressure — Return Currents, Ground Integrity & When to Move to 4 Layers Tech Explorations](https://www.youtube.com/watch?v=8O0vYxu8xHw&t=43s)  

---

# Video 01

[4-Layer PCB Stackup Strategy — SGPS, Return Currents, EMI & Controlled Impedance Explained Tech Explorations](https://www.youtube.com/watch?v=OJmOt4prsxQ)  

---

# What is the Eye Diagram in PCB design?

An eye diagram (or eye pattern) is a graphical representation of a digital signal created by overlaying thousands or millions of consecutive bit sequences on an oscilloscope or in a simulation tool, forming an eye-shaped waveform. [1] (https://www.protoexpress.com/blog/analyzing-eye-diagrams-for-signal-integrity-high-speed-pcbs/), [2] (https://www.qfpcb.com/eye-diagram/)
You can learn more about signal evaluation in this guide on Measuring and Simulating Eye Diagrams and BER. [1] (https://resources.altium.com/p/what-eye-diagram)

What an Eye Diagram Shows

• The "Eye Opening": The central open space of the diagram represents the voltage and timing margins available for a receiver to sample data cleanly. [1] (https://www.zuken.com/en/blog/understanding-eye-pattern-analysis-pcb-design/), [2] (https://www.qfpcb.com/eye-diagram/)
• Wide, Open Eye: Indicates strong signal integrity, low noise, low jitter, and a low bit error rate (BER). [1] (https://www.linkedin.com/posts/mahmoud~farrag_electronics-signalintegrity-pcbdesign-activity-7484665937875574784-a0FM)
• Closed or Blurry Eye: Signals that the channel is degrading due to issues like timing jitter, voltage noise, attenuation, crosstalk, impedance discontinuities, or poor PCB layout. [1] (https://resources.altium.com/p/what-eye-diagram), [2] (https://www.qfpcb.com/eye-diagram/)

Key Elements Analyzed in PCB Design

• Vertical Axis (Amplitude/Voltage): Shows high and low logic levels and amplitude noise.
• Horizontal Axis (Time/Unit Interval): Divided into bit periods to show clock stability and horizontal timing jitter.
• Crossing Points: Where the rising and falling edges of the waveform intersect; consistency here reflects clock and timing stability.
• Mask Testing: Compliance tests that overlay a predefined boundary (mask) to confirm whether high-speed interfaces like PCIe, USB, Ethernet, or DDR meet industry standards. [1] (https://www.cinch.com/resources/blog/the-role-of-eye-diagrams-in-high-speed-optical-design), [2] (https://www.digikey.gr/en/maker/tutorials/2024/what-is-an-eye-diagram-in-electronics-and-what-is-it-used-for), [3] (https://www.youtube.com/watch?v=FBmn-ZirWE8), [4] (https://resources.altium.com/p/what-eye-diagram)

Why It Matters in PCB Layout

As data rates increase in high-speed digital designs, trace routing, stack-up design, vias, and differential pair matching heavily impact signal quality. Engineers use eye diagrams during simulation and lab testing to catch reflection, electromagnetic interference (EMI), and inter-symbol interference (ISI) before finalizing a board. [1] (https://en.wikipedia.org/wiki/Eye_pattern), [2] (https://resources.altium.com/p/what-eye-diagram)

---

