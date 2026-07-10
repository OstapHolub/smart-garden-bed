# Wiring

## Status: planned, not built

No wiring diagram exists yet — `diagrams/` is empty. This file describes
the planned terminal block layout only.

## Terminal blocks (planned)

| Block | Pins | Labels | Notes |
|---|---|---|---|
| 2-pin screw terminal | 2 | POWER IN, VALVE | 12 V rail in, valve drive out |
| 3-pin screw terminal | 3 | SOIL LEFT, SOIL RIGHT, SOIL TEMP | Two moisture sensor analog lines + DS18B20 data |
| 4-pin screw terminal | 4 | AIR SENSOR / I²C, SPARE | I²C (power, GND, SDA, SCL) with a spare line for future expansion |

Labels are considered more important than terminal color-coding — every
port must be clearly marked, since color alone isn't reliable across
different terminal block batches.

## Signal notes

- **SOIL LEFT / SOIL RIGHT**: analog outputs from the two capacitive
  moisture sensors, into ESP32-C3 ADC-capable pins (not yet assigned —
  see [`pinout.md`](pinout.md)).
- **SOIL TEMP**: DS18B20 1-Wire data line. Needs a 4.7 kΩ pull-up to
  3.3 V between DATA and VCC if the sensor module doesn't already include
  one.
- **AIR SENSOR / I²C**: shared bus for AHT20 (temperature/humidity) and
  BMP280 (temperature/pressure — not humidity).
- **VALVE**: switched 12 V output through the MOSFET module, not a direct
  GPIO connection to the valve coil.

## TODO

- Produce an actual wiring diagram once prototyping starts
  (`diagrams/`).
- Confirm connector/terminal block part numbers.
- Decide wire gauge for the 12 V valve circuit based on the valve's
  actual coil current draw (not yet measured — see
  [`irrigation.md`](irrigation.md)).
