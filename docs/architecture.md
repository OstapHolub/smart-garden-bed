# Architecture

This describes the intended system architecture. Mechanical structure is
built; electronics and firmware are not — treat everything below the
mechanical section as a plan, not a description of working hardware.

## Mechanical

```text
        removable planter box (in progress)
                    |
        mounting frame (part of the base)
                    |
        permanent wooden base (built)
        - 4 legs
        - top load-bearing frame
        - center crossbeam
        - lower shelf (individual slats)
                    |
                 terrace floor
```

The base and box are mechanically independent: the base stays outside
year-round, the box is meant to be lifted out and stored. This drives the
electronics architecture too — anything mounted in/on the box needs
connectors, not permanent wiring, at the boundary between box and base.

## Electronics (planned)

```text
220 V AC mains
     |
     v
external adapter (certified, outside the project enclosure)
     |
     v
12 V DC  ---> MOSFET module ---> solenoid valve (NC, DN15, 1/2")
     |
     v
LM2596 buck converter
     |
     v
5 V DC ---> ESP32-C3 SuperMini
                 |
                 +-- ADC x2  <- capacitive soil moisture sensors
                 +-- GPIO (1-Wire) <- DS18B20 soil temperature
                 +-- I2C <- AHT20 (air temp/humidity) + BMP280 (air pressure)
                 +-- GPIO -> MOSFET module (valve control)
```

No mains voltage (220 V) exists past the external adapter. Everything
inside the project's own enclosure is 12 V or 5 V.

Terminal blocks (planned, not yet wired):

- 2-pin: POWER IN, VALVE
- 3-pin: SOIL LEFT, SOIL RIGHT, SOIL TEMP
- 4-pin: AIR SENSOR / I²C, SPARE

See [`../electronics/wiring.md`](../electronics/wiring.md) and
[`../electronics/power.md`](../electronics/power.md) for details, and
[`../electronics/pinout.md`](../electronics/pinout.md) for why specific
GPIO pins aren't assigned yet.

## Firmware (planned)

```text
main.cpp
  |
  +-- sensors/      soil moisture, DS18B20, AHT20/BMP280 reads + calibration
  +-- irrigation/    valve control, max-runtime fail-safe, reboot-safe OFF state
  +-- networking/    Wi-Fi, local API / MQTT (not yet decided)
  +-- diagnostics/   status reporting, error/fault surfacing
```

Safety behavior the firmware must implement once written (see
[`requirements.md`](requirements.md)):

- Valve defaults to OFF on every boot.
- A maximum continuous-watering timeout cuts power to the valve
  regardless of sensor state.
- No irrigation decision is made from a single uncalibrated sensor
  reading.

## Home Assistant (planned)

Not started. Intended to expose sensor readings and irrigation status,
and eventually automations — only after manual valve control has been
validated on real hardware.
