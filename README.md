# Potensic ATOM USB-C Replacement Cable

Reverse-engineered replacement for the directional USB-C cable between a **Potensic ATOM remote controller** (DSRC02A) and an **Android smartphone**.

The original cable was investigated with a multimeter, its wiring was reconstructed in KiCad, and a working prototype was built and tested. This repository shares the schematic, editable design, 3D-printable holder, construction notes and observed behavior.

> **Independent, unofficial project.** Not affiliated with or endorsed by Potensic. This is an experimental hardware build; check all connections before connecting devices. Do not use this adapter for charging, or plug it into the controller's charging port.

## What is included?

- [`hardware/schematic/`](hardware/schematic/) — KiCad schematic and PDF, revision **0.4.10**.
- [`hardware/3d/`](hardware/3d/) — printable STL holder providing strain relief.
- [`docs/wiring-and-measurements.md`](docs/wiring-and-measurements.md) — measured wiring and reference values.
- [`docs/build.md`](docs/build.md) — prototype construction and cable selection.
- [`docs/tests-and-compatibility.md`](docs/tests-and-compatibility.md) — what was and was not tested.
- [`docs/bom.md`](docs/bom.md) — bill of materials, including example supplier links.
- [`docs/release-checklist.md`](docs/release-checklist.md) — pre-publication work and decisions.

## Why isn't a regular USB-C cable enough?

The original cable includes non-standard-for-a-plain-data-cable connections involving **SBU** as well as two **56 kΩ** resistors between each side's **CC (A5)** contact and **VBUS**. A generic USB-C-to-USB-C cable did not work as a replacement in the tested setup.

The design is **directional**: the **CONTROLLER / P1** end and **PHONE / P2** end must not be swapped. The available schematic is the authority for actual pad connections; connector labels on third-party breakout boards must be verified with a multimeter.

### Cable sections are not equivalent

| Section | Observed requirement | Physical connection options |
| --- | --- | --- |
| Remote controller → adapter | SBU-capable, fully wired USB-C connection | Male-to-female extension **or** male-to-male cable, depending on breakout-board socket/plug selection |
| Adapter → Android phone | Ordinary USB 2.0-capable **data** cable worked | Tested with an inexpensive male-to-male USB-C cable |

The tested breakout boards cannot be inserted directly into the recessed controller connector. A suitable extension is therefore needed **for that specific mechanical build**. A USB-C cable advertised as USB 3.x with DisplayPort Alt Mode support, or USB4, is a practical way to look for SBU conductors; marketing terminology alone does **not** establish correct pin continuity. USB 3.x data rates are **not** required by the observed Android AOA communication.

## Demonstrated result

- Prototype constructed from USB-C breakout boards, approximately 10 cm of wire, two 56 kΩ resistors on a separate small board, and a 3D-printed holder.
- USB D+ / D− were twisted in the final prototype; operation was also observed without twisting.
- The Android device displayed a prompt concerning Android Open Accessory (AOA) mode.
- A short practical drone flight was performed with live video and controller inputs.
- The remote-controller USB-C plug was successfully tested in **both 180°-reversed orientations**.

This is a **single reported prototype test**, not an electrical compliance, durability, or cross-device certification.

## Compatibility

| Drone/controller | Status |
| --- | --- |
| Potensic ATOM / DSRC02A / Android phone | **Tested successfully** with this build |
| Potensic ATOM SE, ATOM LT | The manufacturer sells one replacement cable for the ATOM/ATOM SE/ATOM LT family; **this homemade adapter has not been tested** with those drones |
| Other controllers or iOS devices | **Not tested** |

Manufacturer cable listing: https://store.potensic.com/products/usb-cable-for-atom-series-drone

## Important limitations

1. **Not a USB-standard cable design:** the SBU/CC configuration follows measurements of a specific original cable. Do not use as a general-purpose USB-C or charging cable.
2. **Do not reverse P1/P2.** The two sides have different SBU handling.
3. **Not all USB-C extensions carry SBU.** Confirm the actual extension and connector pinout before use.
4. **Breakout-board pin labels can differ.** Verify mirrored pad rows, pin numbering, shield/ground interconnections and orientation with a multimeter.
5. This project was built without oscilloscope or protocol analyzer measurements. Internal controller behavior remains an inference.

## Status and license

Documentation draft intended for an initial **v0.1.0** public release. **Hardware design and STL:** CERN-OHL-S-2.0. **Documentation and measurements:** CC BY 4.0. See [`LICENSE.md`](LICENSE.md) and the complete texts in [`LICENSES/`](LICENSES/). The author's public attribution and repository URL still need to be filled in before publication.

