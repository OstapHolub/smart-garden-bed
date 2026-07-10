# Power

## Status: planned, not built

## Architecture

```text
220 V AC mains
     |
     v
external adapter (certified, ~12 V DC, ~2 A)
     |
     v
DC female panel connector (5.5 x 2.1 mm) at the enclosure boundary
     |
     +--> 12 V rail --> MOSFET module --> solenoid valve
     |
     +--> LM2596 buck converter --> 5 V --> ESP32-C3 SuperMini (5 V input)
```

## Safety constraints

- The external 220 V AC → 12 V DC adapter is the only place in the system
  where mains voltage exists. It must be a certified adapter, and it
  stays outside the project's own 3D-printed enclosure.
- Nothing inside the enclosure should carry more than 12 V DC.
- The DC input connector at the enclosure boundary is the single power
  entry point — this is also where the POWER IN 2-pin terminal block
  (see [`wiring.md`](wiring.md)) picks up 12 V for the valve circuit.

## Open items

- LM2596 module selection (fixed 5 V output module vs. adjustable, not
  yet decided).
- Verify actual current draw of the ESP32-C3 + sensors to confirm the
  buck converter and adapter are sized adequately — not yet measured.
- Confirm adapter's real-world output under load (2 A is the label
  rating, not yet verified against actual system draw).
