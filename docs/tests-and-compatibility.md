# Validation, observations and compatibility

## Tests reported by the project author

| Test | Result | Scope |
| --- | --- | --- |
| Reconstructed wiring / resistor measurements | Pass | Multimeter; original cable through breakout boards |
| Custom adapter between DSRC02A and Android phone | Pass | Reported prototype configuration |
| Android accessory-mode prompt | Observed | User saw a system prompt to switch to AOA |
| Video/control during a short flight | Pass | One short flight, reported under five minutes |
| Controller-side USB-C connector orientation reversed by 180° | Pass | Both orientations reported to work |
| Untwisted short D+/D− pair | Worked in a test | Not a general wiring recommendation |
| Plain conventional USB-C-to-USB-C cable replacing special cable | Did not work | Reported setup |
| Alternative extension, ASIN B0BNNHCCD1 | **Not tested** | Potential alternative only |
| ATOM SE, ATOM LT with this adapter | **Not tested** | Manufacturer's cable family alone is not validation |
| iOS devices / other remotes / durability / signal integrity | **Not tested** | No claim of compatibility |

## Evidence boundaries

The AOA-mode prompt and functional test are consistent with Android Open Accessory operation, but they do not prove the internal firmware's use of SBU. The exact functional explanation of the proprietary arrangement has not been independently established.

Manufacturer lists original USB-C, Micro-USB and Lightning cable options for the ATOM family:

- https://store.potensic.com/products/usb-cable-for-atom-series-drone

The remotes' exact compatibility, including model designation **DSRC02A**, should be checked against the relevant Potensic manuals, which are cited in the `sources/` notes. This project does not claim a test of every drone sharing a commercially listed accessory.

