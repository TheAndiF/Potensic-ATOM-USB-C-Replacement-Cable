# Wiring reconstruction and measurements

Source: original directional Potensic ATOM USB-C cable, measured offline with a multimeter through **two USB-C breakout boards**. Primary reproducible record: `hardware/schematic/USB_C_auf_C_Sammelpunkte_Verdrahtet.kicad_sch` and its PDF, revision 0.4.10.

| Test / condition | Recorded nominal result |
| --- | --- |
| Controller (P1) CC A5 → VBUS | ≈ 56 kΩ |
| Phone (P2) CC A5 → VBUS | ≈ 56 kΩ |
| P1 CC → P2 CC | ≈ 112 kΩ (through the resistor/VBUS path; no direct CC wire) |
| P1 VBUS → P2 VBUS | Low resistance / continuity |
| P1 GND → P2 GND | Low resistance / continuity |
| P1 D+ → P2 D+ | Low resistance / continuity |
| P1 D− → P2 D− | Low resistance / continuity |
| P1 SBU A8/B8 → shield ground (SGND) | Low resistance / continuity |
| P2 SBU A8 ↔ B8 | Low resistance / continuity |
| P2 SBU A8/B8 → SGND | Open circuit (OL) |

R1 and R2 are specified in the schematic as **56 kΩ, 1%**, connected **A5 CC to VBUS** on their respective ends. The schematic indicates B5/B6/B7 are not connected. Keep distinct the main GND return and the SGND/shield connections already present on the chosen breakout boards.

**Important:** This table is a guide to reviewing the schematic, **not a substitute** for the exact KiCad net/pad drawing. Do not reinterpret the SBU wiring as an ordinary USB-C cable pinout.

## Measurement method

1. Insert the original cable between two appropriate USB-C breakout boards, with all external power removed.
2. Measure continuity and resistance between the named exposed contacts using a multimeter.
3. Repeat with reversed connector orientation where relevant; confirm the physical pad layout and any built-in ground/shield bridges.
4. Record observed values and translate them to the KiCad drawing.

No oscilloscope, USB protocol analyzer, signal-integrity or compliance testing was performed. The explanation of what the controller internally does with SBU remains **unverified**.

