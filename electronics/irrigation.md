# Irrigation Electronics

## Status: planned, not built or tested

## Valve

- Normally Closed (NC) solenoid valve, DN15 / 1/2", 12 V DC.
- Normally Closed was chosen specifically so that a power loss leaves the
  valve shut instead of open — see the fail-safe requirement in
  [`../docs/requirements.md`](../docs/requirements.md).

## Drive circuit

- Driven through a MOSFET module rather than directly from a GPIO pin.
- **Not yet verified**: the solenoid coil's actual current draw. This
  needs to be measured/confirmed against the MOSFET module's rated
  switching current before relying on it.
- **Not yet verified**: whether the MOSFET module includes flyback
  (freewheeling diode) protection for the inductive solenoid coil. If it
  doesn't, a flyback diode needs to be added across the coil — without
  one, switching off an inductive load like a solenoid can produce a
  voltage spike that damages the MOSFET.
- **Not yet verified**: the valve's minimum operating pressure. Some
  solenoid valves need a minimum line pressure to open/seal correctly;
  this needs to be checked against the actual water supply pressure
  before assuming the valve will work as installed.

## Firmware-side safety (not yet implemented)

- Maximum continuous-watering timeout, enforced in firmware regardless of
  sensor state.
- Valve defaults to OFF on every boot/reboot.
- No irrigation decision based on a single, uncalibrated sensor reading —
  see [`../docs/requirements.md`](../docs/requirements.md).

## Hydraulic side

See [`../planter/drainage-and-liner.md`](../planter/drainage-and-liner.md)
for the box-side drainage plan and the project root README's Irrigation
section for the planned plumbing layout (16 mm PE mainline, 4 mm
microtube, drippers). The exact hydraulic schematic is not finalized.
