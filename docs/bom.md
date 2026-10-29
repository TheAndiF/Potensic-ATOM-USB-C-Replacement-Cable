# Bill of materials (prototype)

| Qty | Item | Description / status |
| ---: | --- | --- |
| 2 | USB-C 26-pad breakout boards | Example used: https://www.amazon.de/dp/B0DJVS1FF8 — verify actual pin labeling and solder-side mirroring |
| 2 | 56 kΩ resistor, 1% | R1/R2, CC A5 to VBUS, per schematic |
| 1 | Small experiment board | Holds resistors separately in the reported prototype |
| — | Insulated hookup wire | Approximately 10 cm span, D+ and D− twisted in the final build |
| 1 | 3D-printed holder | STL file in `hardware/3d/`; provides strain relief |
| 1 | USB-C controller-side extender/cable | Tested choice: https://www.amazon.de/dp/B0G3W7FYH6 ; SBU continuity required |
| 1 | USB-C phone-side data cable | Inexpensive USB 2.0-capable male-to-male cable, **tested** |

**Potential alternative, not tested:** https://www.amazon.de/dp/B0BNNHCCD1 (advertised USB4/40 Gbit/s). Physical fit and exact SBU wiring have not been verified for this option.

Tools used: multimeter, soldering equipment and a 3D printer. No oscilloscope was used.

**Mechanical note:** cable gender depends on the chosen male/female breakout boards; only the functional controller versus phone sides are fixed. Product listings are examples, not endorsements, validated pinouts or guarantees of future availability.

