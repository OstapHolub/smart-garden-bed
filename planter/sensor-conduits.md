# Sensor Conduits

## Status: planning, not built

At least two cable conduits (PVC or electrical conduit tubing) are planned
to run into the planter box:

- One conduit for the active sensor cable bundle (soil moisture ×2, soil
  temperature, and any wiring back to the electronics enclosure).
- One spare conduit for future expansion, so adding a sensor later doesn't
  require cutting into the finished box.

## Why

This exists to satisfy the serviceability requirement in
[`../docs/requirements.md`](../docs/requirements.md): sensors and wiring
should be replaceable without digging through soil or dismantling the box.
A dedicated conduit — rather than cables buried directly in soil — is the
mechanism for that.

## Open questions / not yet decided

- Exact conduit diameter and routing path through the box wall.
- Where the conduit terminates relative to the electronics enclosure
  (see [`../enclosure/README.md`](../enclosure/README.md)) and how the
  cable entry there is sealed against water.
- Strain relief / grommet approach at both ends of the conduit.

## TODO

- Finalize conduit placement once the box's bottom panel design is
  locked in.
- Document actual conduit part numbers once purchased.
