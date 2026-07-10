# Electronics

## Status

Components are selected and ordered. Nothing has been wired, prototyped,
or tested yet — everything in this directory describes a plan, not a
working circuit.

## Contents

- [`bom.md`](bom.md) — bill of materials: what's needed, what's been
  bought, and what's still unverified.
- [`pinout.md`](pinout.md) — planned GPIO usage on the ESP32-C3
  SuperMini; no pins are finalized yet.
- [`power.md`](power.md) — power architecture from 220 V AC mains down to
  5 V logic power.
- [`wiring.md`](wiring.md) — planned terminal block layout and signal
  routing.
- [`irrigation.md`](irrigation.md) — solenoid valve and drive electronics.
- `datasheets/` — component datasheets (empty for now).
- `diagrams/` — wiring/schematic diagrams (empty for now; planned once
  prototyping starts).

## System summary

One ESP32-C3 SuperMini reads two capacitive soil moisture sensors
(analog), one waterproof DS18B20 soil temperature sensor (1-Wire), and an
AHT20 + BMP280 combo breakout (I²C, air temperature/humidity/pressure),
and drives a 12 V DC Normally Closed solenoid valve through a MOSFET
module. Power comes from an external 220 V AC → 12 V DC adapter, stepped
down to 5 V for the ESP32-C3 via an LM2596 buck converter. See
[`../docs/architecture.md`](../docs/architecture.md) for the full diagram.

## Safety notes

- The valve is Normally Closed — loss of power stops water flow.
- Flyback protection for the valve coil needs to be confirmed on the
  MOSFET module and added if missing (see [`irrigation.md`](irrigation.md)).
- No mains voltage exists past the external adapter.
- Firmware (not yet written) must enforce a maximum continuous-watering
  timeout and default the valve to OFF after every reboot — see
  [`../docs/requirements.md`](../docs/requirements.md).
