# Roadmap

Status markers: ✅ Completed · 🚧 In progress · 📋 Planned · 🧪 Not yet
validated.

## Mechanical

- ✅ Fusion 360 model of the wooden base.
- ✅ Wooden base built, sanded, finished with two coats of oil, and
  assembled in place on the terrace.
- 🚧 Removable planter box: bottom panel, sanding, finish coats.
- 🚧 Geotextile liner installation.
- 🚧 Planning cable conduit routing for sensors.
- 📋 Add Fusion 360 source file, STEP export, and renders to this
  repository (`mechanical/fusion360/`).
- 📋 Reconcile CAD model with the base's actual measured dimensions.

## Electronics

- ✅ Core components selected and ordered (ESP32-C3 SuperMini, capacitive
  soil moisture sensors, DS18B20, AHT20/BMP280 combo, solenoid valve,
  MOSFET module, buck converter).
- 📋 Breadboard prototyping of the sensor + valve circuit.
- 📋 Verify solenoid coil current and minimum operating pressure.
- 📋 Confirm flyback protection is present on the MOSFET module (add one
  if not).
- 📋 Finalize wiring diagram and terminal block labeling.
- 📋 Finalize GPIO pin mapping against the actual ESP32-C3 SuperMini
  revision, including boot-strapping pin constraints.

## Firmware

- 📋 PlatformIO project scaffold — not started; `firmware/` is currently
  empty.
- 📋 Sensor reading modules (soil moisture, DS18B20, AHT20/BMP280).
- 📋 Soil moisture sensor calibration (dry/wet reference points).
- 📋 Irrigation control logic with a maximum continuous-watering
  fail-safe timeout and valve-OFF-after-reboot default.
- 📋 Networking (Wi-Fi, local API or MQTT).
- 📋 Diagnostics / status reporting.

## Enclosure

- 📋 3D model for the electronics enclosure.
- 📋 Print and fit-check against the actual PCB/terminal layout.
- 📋 Cable gland selection and drip-loop routing.
- 🧪 Weather resistance — not yet tested; do not claim "waterproof" until
  this has a documented test result.

## Irrigation

- 📋 Finalize hydraulic layout (mainline routing, dripper placement,
  filter/pressure reducer if needed).
- 📋 First unattended watering test.
- 🧪 "Automatic irrigation" is not claimed anywhere in this repository
  until an unattended run has actually been observed and logged here.

## Home Assistant

- 📋 Expose sensor readings.
- 📋 Expose irrigation status and manual override.
- 📋 Automations (only after manual control has been validated).

## Documentation

- ✅ Initial repository structure, README, timeline, BOM.
- 📋 Wiring diagrams (`electronics/diagrams/`).
- 📋 Update this roadmap as electronics prototyping starts.
