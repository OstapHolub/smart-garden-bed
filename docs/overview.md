# Project Overview

## What this is

Smart Garden Bed is a raised garden bed for a terrace, designed as two
separate structures:

1. A permanent wooden base with four legs, a top frame, a center
   crossbeam, and a lower shelf, built to stay outside through the
   seasons.
2. A removable planter box that sits in a mounting frame on top of the
   base, sized to hold soil and, eventually, drip irrigation plumbing and
   soil sensors.

The long-term goal is to add an ESP32-C3 controller that reads soil
moisture, soil temperature, and air temperature/humidity/pressure, and
that can open a solenoid valve to water the bed automatically. None of the
electronics or firmware work has started as of this writing — see
[`roadmap.md`](roadmap.md) for what's actually planned versus done.

## Why it's split into a base and a box

The base is meant to be permanent — it's finished, sanded, and oiled, and
sits directly on the terrace tiles. The planter box is meant to come off:
in autumn, the soil can be removed, and the box itself can be taken down
and stored (e.g., in a garage) instead of leaving a wood-and-soil
structure exposed to winter weather. This also means the box's design
target and the base's actual finished dimensions have to line up — see
[`../mechanical/cut-list.md`](../mechanical/cut-list.md) for the note on
why the box is being fitted to the base after the fact, rather than to
the original CAD target dimensions.

## Design-to-build path

```text
Fusion 360 design
        |
        v
raw lumber
        |
        v
wooden base
        |
        v
removable planter
        |
        v
electronics prototype
        |
        v
automatic irrigation
```

Photos from the base build are in [`photos/woodworking`](photos)
and [`photos/assembly`](photos), organized in the same order as the
[timeline](timeline.md). Fusion 360 renders will be added to
[`photos/design`](photos) once the model file itself is added to the
repository — see [`../mechanical/fusion360/README.md`](../mechanical/fusion360/README.md).

## Where things live

- [`requirements.md`](requirements.md) — functional and non-functional
  requirements driving the design.
- [`architecture.md`](architecture.md) — how the mechanical, electrical,
  and firmware pieces are meant to fit together.
- [`timeline.md`](timeline.md) — the build log so far.
- [`roadmap.md`](roadmap.md) — what's done, in progress, and planned.
- [`lessons-learned.md`](lessons-learned.md) — decisions and mistakes worth
  remembering.
