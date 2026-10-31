# Series Overview

## Hardware Design With AI Co-Pilot

- Parts:

[ESP32-S3-WROOM-1-N8 (Microcontroller Module)](https://www.hqonline.com/product-detail/rf-transceiver-module-espressif-esp32-s3-wroom-1-n8-2500411082)   

[ESP32-S3-WROOM-1U-N8R8](https://www.hqonline.com/product-detail/wifi-and-bluetooth-modules-espressif-esp32-s3-wroom-1u-n8r8-2500402375)  

> HLK-5M05, HLK-10M05
> HLK-PM01, HLK-PM03

[HLK-5M05 AC DC 220 V TO 5V 5W 5 Isolated Switching Step-Down Module Converter](https://www.amazon.it/HI-Link-HLK-5M05-Switching-Step-Down-Converter/dp/B077ZRWR5C/ref=asc_df_B077ZRWR5C?mcid=f4eae3e3a9383baa9a9cef2d9b10cb44&tag=googshopit-21&linkCode=df0&hvadid=711155295770&hvpos=&hvnetw=g&hvrand=12215674342559514681&hvpone=&hvptwo=&hvqmt=&hvdev=c&hvdvcmdl=&hvlocint=&hvlocphy=1008463&hvtargid=pla-2365041559107&psc=1&hvocijid=12215674342559514681-B077ZRWR5C-&hvexpln=0)    

[HLK-PM03 220V a 3.3V 3W AC-DC Isolato Step Down Modulo di alimentazione](https://www.amazon.it/RAKSTORE-HLK-PM03-isolato-Modulo-alimentazione/dp/B0C596GQ3D/ref=sr_1_5?dib=eyJ2IjoiMSJ9.Dk15wsKfg0b1tkzGdhdDTtFAoTT-xP4oDu7aJ5cNW5ftzKY4OE6GvUzSYM0mSprr355ePslbfinUZRXUuFYBdQsIQGQUYwfZpRcb63s-ZDtsjDsGrhnY_DAXmt3p_ukOlSSBUp7scnuC7Jmd1zEkjrChpeHhr7aOTPc4vV_i43FDZCf52OIlUChUuCDQg6Hz-CrezP0NpVdOtwNGVtlp77y4tx2ILlZECIQELJCRk4V3Cn0tr6mzQtXOJnIpbT3OtqzpSIizNUQsoCjN7fMTXZCKP_e5Ah2x15wMTelMeEs.kwoGwVObVSuuGQ_8yHSAsk5gqio3JYQgl3MnE-2bI9I&dib_tag=se&keywords=HLK-PM03&qid=1793453730&sr=8-5)


[RTC Module](https://www.hqonline.com/search/DS3231)  

---

EP-3
Project setup & Power+MCU circuit design
EP-4
INPUT/OUTPUT circuit
EP-5
Schematic review & Footprint assignment

---



---

## EP-2 : Features, Working & Design Planning

[Hardware Design With AI Co-Pilot | EP-2 : Features & Design Plan | Ampnics](https://www.youtube.com/watch?v=ZCfjKgXZC-I)   

Features

- LED & Sound Feedback
- Push Buttons for manual operation
- Real time clock (RTC)
- Remote Control (Gen-Al or Cloud)
- On board PWR Supply
- USB Port for Programming & Debugging

## Block Diagram of the design

1. Power Supply: 

- the PCB needs stable power 
- use an AC to DC converter to bring down the mains voltage to a safe DC level
- the safe DC level feeds into the Power Supply Block (PSB) that distributes regulated voltage to the other parts of the PCB
- A Low Dropout (LDO) regulator compoment is used to supply with power all the sensitive components such as the Microcontroller, the RTC anD the switches.

---

2. AC to DC converter

- brings down the mains voltage to a safe DC level
- the safe DC level output of the AC-DC converter is used as input of a DC Power Block to generate a regulated DC voltage to distribute to the rest of the board 

---

3. LDO [Low-Dropout Regulator]

- the safe DC level output of the AC-DC converter is also fed into a LDO to generate at its output a
noise-free DC level used to power noise-sensitove components suche as RTC, switches, some FPGA, 
some Microcontrollers, etc.  

---

4. INPUT Devices

- RTC
- switches

---

5. Processing Unit

This is normally a microcontroller or an FPGA.

[Hardware Design With AI Co-Pilot | EP-5 : Schematic Review & Footprint | Ampnics Ampnics](https://www.youtube.com/watch?v=g14nOuirc1c)  

---

6. OUTPUT Device

- Buzzer
- LEDs (LED Arrays)
- LCD Display
- Relays


---

## EP-1 : Introduction & Setup

[Hardware Design With AI Co-Pilot | EP-1 : Intro & Setup | Ampnics](https://www.youtube.com/watch?v=z6l4urOoXyE)  

---

# EP-6: Mechanical design & component placement

[Hardware Design With AI Co-Pilot | EP-6 : Board outline & Component placement | Ampnics](https://www.youtube.com/watch?v=qOU23NVi12E)  

---

# EP-7: Track Designing & Silkscreen labelling

[Hardware Design With AI Co-Pilot | EP-7 : USB, I2C & GPIO tracks designing | Ampnics](https://www.youtube.com/watch?v=7tiu6dTseCc&t=1s)   


---

# EP-8 Dseign checks & Manufacturing Preparation

[Hardware Design With AI Co-Pilot | EP-8 : ERC, DRC, BOM and Gerber File | Ampnics](https://www.youtube.com/watch?v=R1q_x9aNpcQ)  

---

# EP-9 Last minute checkup, PCB ordering & Hardware Testing

[Hardware Design With AI Co-Pilot | EP-9 : PCB Ordering & Hardware Testing | Ampnics](https://www.youtube.com/watch?v=_K-F-xFSYas)  

---

EP-10
Firmware development, Final Demonstration & Project Sharing

---

