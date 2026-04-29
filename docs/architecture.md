# Architecture

## Firmware Style
The firmware in `src/main.cpp` is Arduino-style C++:
- `setup()` initializes all LED GPIOs as outputs and sets LOW.
- `loop()` polls keypad events and applies action mapping.

## Modules
- **Input module (implicit):** `Keypad keypad` object configured with key map, row pins, column pins.
- **Output module (implicit):** `ledPins[]` array indexing 12 LED channels.
- **Control logic:** `switch(key)` dispatches actions per key press.

## Behavior Mapping
- `1..8`: turns on corresponding blue LED output (latched ON until another command changes it).
- `9`: turns on LED group 1..8.
- `0`: turns off LED group 1..8.
- `A..D`: turns on corresponding red LED output.
- `*`: turns on group A..D.
- `#`: turns off group A..D.

## Timing
- Main loop includes `delay(10)` to reduce polling rate and debounce pressure.

## Assumptions
- GPIO numbering follows RP2040 Arduino core conventions (`GPx`).
- External 1k pull-ups on keypad rows are kept as in supplied diagram.
