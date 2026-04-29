# Pico W Keypad-to-LED Controller

This repository packages a Raspberry Pi Pico W project that reads a 4x4 matrix keypad and controls 12 discrete LEDs.

## Features
- 4x4 keypad scanning via `Keypad` library.
- 12 independent LED outputs on Pico GPIO pins.
- Group actions:
  - `9` turns on LEDs 1-8.
  - `0` turns off LEDs 1-8.
  - `*` turns on LEDs A-D.
  - `#` turns off LEDs A-D.
- Logic preserved exactly from the provided source (`src/main.cpp`).

## Repository Structure

```text
.
├── CMakeLists.txt
├── diagram.json
├── src/
│   └── main.cpp
├── include/
└── docs/
    ├── architecture.md
    └── wiring.md
```

## Components
- 1x Raspberry Pi Pico / Pico W (RP2040 target).
- 1x 4x4 membrane keypad.
- 12x LEDs (8 blue + 4 red in the diagram).
- 12x 220Ω resistors (LED current limiting).
- 4x 1kΩ resistors (keypad row pull-ups).
- Jumper wires + common GND.

## Run in Wokwi
1. Create a new Raspberry Pi Pico project in Wokwi.
2. Copy `src/main.cpp` into the sketch file.
3. Use the provided `diagram.json` wiring.
4. Ensure the `Keypad` library is available in Wokwi libraries.
5. Start simulation.

## Run on Real Hardware (Pico W)
1. Open the project in Arduino IDE or PlatformIO with a Pico/RP2040 Arduino core.
2. Install library: **Keypad** by Mark Stanley & Alexander Brevig.
3. Select board: **Raspberry Pi Pico W**.
4. Wire according to `docs/wiring.md`.
5. Build and flash.

## Notes on Wi-Fi
- This project does not use Wi-Fi.
- No SSID/password is required.
- If Wi-Fi is added later, store credentials in a separate ignored config file (e.g. `secrets.h`) and never commit it.

## Flashing Tips
- If upload fails, hold **BOOTSEL**, connect USB, release BOOTSEL, then retry upload.
- Verify all LED cathodes share GND and each LED anode has a series resistor.
