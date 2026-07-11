# Fusion 360 Model

## Status

The Fusion 360 source is now in this repository: [`garden-base.f3z`](garden-base.f3z),
exported 2026-07-11. A render is available at
[`../../docs/photos/design/garden-base-render.jpg`](../../docs/photos/design/garden-base-render.jpg).

Not yet included: a neutral STEP export or dimensioned PDF drawings — see
[`../exports/`](../exports/).

## What the model covers

This is a Fusion 360 assembly ("Garden Base") covering the permanent
wooden base: four legs, the top load-bearing frame with front/back and
side rails, and the lower slat shelf. It does not cover the removable
planter box, which is being sized against the base's actual built
dimensions rather than modeled first — see
[`../../planter/design.md`](../../planter/design.md).

## Components in the assembly

Based on the part names inside the `.f3z` archive:

| Part | Cross-section |
|---|---|
| Leg 50x50 | 50 × 50 mm |
| Long Rail 50X50 | 50 × 50 mm |
| Short Rail Bottom 50x50 | 50 × 50 mm |
| Short Rail Top 50x50 | 50 × 50 mm |

All structural members use a 50 × 50 mm nominal cross-section. Exact
lengths haven't been pulled from the model yet — that requires opening it
in Fusion 360 to read the driving sketch dimensions, not just inspecting
the archive contents. See [`../cut-list.md`](../cut-list.md).

The render shows the top frame, a center crossbeam, and a slatted lower
shelf, which matches the general shape of the built base — see
[`../../docs/photos/final/d07-final-result-1.jpg`](../../docs/photos/final/d07-final-result-1.jpg)
for comparison.

## Known differences between CAD and the built base

Not yet verified in detail. The base was built from an earlier version of
this design, but the finished, assembled base's exact measured dimensions
have not been checked against this specific exported model — see
[`../cut-list.md`](../cut-list.md). Until that check happens, treat the
model as representative of the design intent, not as a guaranteed exact
match to the physical base.

## Format note

`.f3z` is Fusion 360's own archive format (a zip containing the assembly
and its referenced component files); it requires Fusion 360 (or a
compatible viewer) to open. A neutral STEP export for tools that don't
support `.f3z` is planned but not yet added.

## What to change if you're editing the model

Not yet documented in detail — the four components above all share the
50 × 50 mm rail/leg cross-section, so changing that dimension likely means
updating each part individually rather than a single shared parameter.
This hasn't been confirmed by opening the model.
