# Pinout

## Status: not finalized

No GPIO pins are assigned yet. This file lists what needs to be connected,
not which physical pins connect to them. Pins must not be assigned until
the actual ESP32-C3 SuperMini board revision's pinout and
boot-strapping-pin constraints have been checked — some ESP32-C3 pins have
special behavior at boot (e.g., strapping pins that must be a specific
level during reset) and picking one blind can produce a board that won't
boot or won't flash.

## Required I/O

| Signal | Type | Count | Notes |
|---|---|---|---|
| Soil moisture sensors | Analog (ADC) | 2 | One per sensor |
| DS18B20 data | Digital, 1-Wire | 1 | Needs 4.7 kΩ pull-up to 3.3 V |
| I²C bus (AHT20 + BMP280) | Digital, I²C (SDA/SCL) | 2 | Shared bus, both sensors on it |
| Valve MOSFET control | Digital output | 1 | Drives the MOSFET module gate/input |

Total: 2 ADC-capable pins, 3 general digital GPIOs (1-Wire + 2 for I²C),
plus whatever the chosen board exposes for USB/UART/programming.

## TODO before assigning pins

- Confirm which physical pins on the specific ESP32-C3 SuperMini
  revision in hand are ADC-capable.
- Check which pins are boot-strapping pins and avoid using them for
  signals that could be active during reset (e.g., avoid driving the
  valve MOSFET from a strapping pin).
- Confirm the board's default I²C pins (if any silkscreen/vendor default
  exists) before choosing others.
- Record the final mapping here once pins are chosen, and again in the
  firmware's pin definitions once `firmware/` is scaffolded.
