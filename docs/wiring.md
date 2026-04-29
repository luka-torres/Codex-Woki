# Wiring and GPIO Mapping

## Overview
The design uses one 4x4 keypad (8 signal lines) and 12 LED channels.

## Keypad Pin Mapping
| Keypad Signal | Pico W GPIO |
|---|---|
| C1 | GP19 |
| C2 | GP18 |
| C3 | GP17 |
| C4 | GP16 |
| R1 | GP26 |
| R2 | GP22 |
| R3 | GP21 |
| R4 | GP20 |

The diagram adds 1kΩ pull-ups from R1-R4 to 3V3.

## LED Pin Mapping
| Logical LED | Key Label | Pico W GPIO |
|---|---|---|
| ledPins[0] | 1 | GP11 |
| ledPins[1] | 2 | GP10 |
| ledPins[2] | 3 | GP9 |
| ledPins[3] | 4 | GP8 |
| ledPins[4] | 5 | GP7 |
| ledPins[5] | 6 | GP6 |
| ledPins[6] | 7 | GP5 |
| ledPins[7] | 8 | GP4 |
| ledPins[8] | A | GP3 |
| ledPins[9] | B | GP2 |
| ledPins[10] | C | GP28 |
| ledPins[11] | D | GP27 |

Each LED anode is driven from GPIO through a 220Ω resistor, and cathodes are tied to GND.

## Power/Ground
- Pico 3V3 feeds keypad pull-up network.
- Common GND shared by keypad/LED circuitry.
