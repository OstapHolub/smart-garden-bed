# Licensing

This repository uses separate licenses for different kinds of content, which is common practice for hardware + firmware + documentation projects.

| Content | License | Applies to |
|---|---|---|
| Firmware / software | [MIT](LICENSE-MIT.md) | `firmware/`, `home-assistant/` automation configs |
| Hardware design | [CERN-OHL-P v2](LICENSE-CERN-OHL-P.md) | `mechanical/`, `enclosure/`, `electronics/` (schematics, wiring diagrams, pinouts, mechanical drawings) |
| Documentation & photos | [CC BY 4.0](LICENSE-CC-BY-4.0.md) | `docs/`, `README.md`, photos, renders |

Rationale:

- **MIT** for firmware keeps reuse simple and unencumbered — this is a small hobby codebase, not something that needs copyleft protection.
- **CERN-OHL-P** (permissive variant) was chosen over the strong/weak reciprocal variants because there's no strong need to force downstream derivatives to stay open; it's the hardware-design equivalent of a permissive software license.
- **CC BY 4.0** for docs and photos allows reuse and adaptation as long as attribution is given.

If a file doesn't fall clearly into one of the three categories above, treat it as covered by the license of the directory it lives in.
