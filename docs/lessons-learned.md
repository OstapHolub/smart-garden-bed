# Lessons Learned

This file only lists things that actually happened during the build, not
anticipated or hypothetical lessons.

## Build the base first, fit the box to reality afterward

The wooden base was designed in Fusion 360, built, sanded, and finished
before the planter box dimensions were finalized. Rather than trusting the
original CAD target dimensions for the box, the box is being sized against
the base's actual, measured mounting frame. A hand-built frame doesn't
match a CAD model to the millimeter, and fitting the box afterward avoided
a mismatch that would only have shown up at final assembly.

## Label every part before finishing

Before sanding and oiling, every board was disassembled and hand-labeled
directly on the end grain (see photos in
[`photos/assembly`](photos/assembly)) — which piece it is, its
orientation, and which side faces up. With many nearly-identical boards
in the base (legs, crossbeams, shelf slats), this made reassembly after
finishing straightforward instead of a guessing game.

## Hidden fasteners, with one exception

Most fasteners in the base are driven from the inside or underneath so
they don't show on the visible faces. The top corners of the frame do use
small metal corner brackets that are visible from the outside — a
deliberate trade-off for joint strength at the corners that take the most
load, rather than a design that was fully fastener-free.

## Surface prep takes longer than expected

Sanding through multiple grits and applying two coats of oil (with drying
time between coats) took up a disproportionate share of total build time
compared to cutting and assembling the frame itself.

## Measuring mistakes happen even when you plan for them

The base's mounting frame measures 100 × 50 cm, and the planter box was
designed at 99 × 49 cm specifically to fit inside it with clearance. A
measuring or assembly error during the box build still resulted in a box
measuring 99 × 53 cm — 4 cm too wide on the 50 cm dimension. At the time,
the assembled box looked finished (see the "final" photos in
[`timeline.md`](timeline.md), Day 10) — the mistake only surfaced once it
was test-fitted against the mounting frame and confirmed not to fit. The
affected panels have since been trimmed and the cut edges oiled, but the
box hasn't been reassembled or re-fitted yet. Planning around a target
dimension doesn't prevent execution mistakes — it's still worth a dry
fit-check before assuming an assembled part matches the plan, not just
before finishing it.

## Design for service, not just for the first assembly

The removable-box concept and the planned spare cable conduit both exist
because of the same underlying decision: sensors and wiring will fail or
need replacing at some point, and the design should not require digging
through soil or dismantling the planter to get at them.
