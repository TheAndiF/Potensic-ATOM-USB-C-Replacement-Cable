# Prototype build notes

## Electrical identity first

The two ends are **not interchangeable**:

- **P1 / CONTROLLER:** uses the controller-side SBU-to-shield-ground arrangement in the schematic.
- **P2 / PHONE:** has its own SBU arrangement (A8 and B8 interconnected, not tied to shield ground).

Use the KiCad schematic as the wiring authority. Re-check the pads on both the *front* and *solder* sides of the actual breakout boards; the pad pattern may be mirrored.

## Reported prototype

1. Two USB-C breakout boards with exposed pads; refer to the parts list for the example.
2. Approximately **10 cm** of separate insulated wires between boards.
3. USB 2.0 D+ and D− were **twisted**; a short untwisted test also functioned. This is not evidence of guaranteed signal integrity at arbitrary lengths.
4. Two **56 kΩ, 1%** resistors mounted on a separate small experiment board.
5. A 3D-printed holder (STL provided) secures the assembly and provides strain relief.
6. Low-resistance continuity and resistance checks were performed before connecting the controller and phone.

## Connecting to the remote controller

The employed breakout boards **do not physically fit** the recessed/particular controller port. A suitable USB-C extension (with the required SBU connections) was used.

The physical cable gender is a **mechanical choice**, depending on whether the breakout board exposes a male connector or female socket:

- Controller → adapter: SBU-capable male-to-female extension **or** SBU-capable male-to-male cable with suitable female breakout.
- Adapter → phone: inexpensive **USB 2.0 data-capable** male-to-male cable worked in the tested setup; an equivalent appropriate connector arrangement can also be built.

The SBU-capable requirement concerns **signal continuity**, not a need for high-speed USB 3.x data transfer. Some USB 2.0-only cables omit SBU. Advertised USB4 / Thunderbolt / DisplayPort Alt Mode support is a useful selection clue, but continuity must not be assumed merely from a product title.

## Safety checks

Before connecting powered devices, verify against the schematic:

- No unintended short between VBUS and GND.
- P1 and P2 are correctly identified.
- The CC-to-VBUS resistances are approximately 56 kΩ and the corresponding inter-CC path approximately 112 kΩ.
- Required data and SBU contacts match the diagram, including the specified shield-ground distinctions.
- The assembly cannot flex solder joints or let exposed contacts touch metal parts.

**Never use the adapter as a general-purpose charger or USB cable. Never connect it to the controller charging port.**

