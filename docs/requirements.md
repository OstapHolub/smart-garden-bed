# Requirements

## Functional

- Hold soil for small plants (greens, strawberries, or similar) in a
  terrace setting.
- Allow the soil-bearing planter to be removed and stored separately from
  the permanent base.
- Monitor soil moisture at two points in the bed.
- Monitor soil temperature.
- Monitor air temperature, humidity, and atmospheric pressure near the
  bed.
- Control a solenoid valve to water the bed based on sensor readings
  (planned; not implemented).
- Expose sensor data and irrigation status to Home Assistant (planned; not
  implemented).

## Non-functional / constraints

- **Fits a specific terrace corner.** Target footprint at project start
  was approximately 1000 × 500 mm; the actual base was built to this
  target and then measured — see
  [`../mechanical/cut-list.md`](../mechanical/cut-list.md).
- **No exposed mains voltage.** The only 220 V AC in the system is inside
  a certified external adapter; everything past that point runs at 12 V
  or 5 V.
- **Fail-safe valve behavior.** The solenoid valve is Normally Closed, so
  loss of power stops water flow. Firmware must also enforce a maximum
  continuous watering time and default the valve to OFF after every
  reboot.
- **No single-sensor irrigation decisions.** The system should not open
  the valve based on one uncalibrated reading; moisture sensors need
  dry/wet calibration before they're trusted for automation.
- **Serviceable electronics.** Sensors and wiring must be replaceable
  without disturbing the soil or dismantling the planter box. At least two
  cable conduits are planned into the box.
- **Weather resistance for electronics** (not yet validated). Enclosure
  and cable entries need to handle rain, condensation, and water tracking
  down cables — planned via cable glands with a drip loop, not yet built
  or tested.

## Explicitly out of scope for now

- Full automation without human oversight — planned as a later milestone,
  not a v1 requirement.
- Remote (outside local network) access or control.
- Multi-bed or multi-zone irrigation.
