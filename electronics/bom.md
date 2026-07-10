# Bill of Materials

Quantities marked "Purchased" reflect that some components were bought as
part of multi-unit kits, so the quantity on hand can exceed what a single
controller needs.

| Component | Purpose | Required qty | Purchased qty | Status | Notes |
|---|---|---|---|---|---|
| ESP32-C3 SuperMini (USB-C) | Main controller | 1 | 1 | ✅ Purchased | — |
| Capacitive soil moisture sensor | Soil moisture, 2 points in the bed | 2 | Kit (exact spare count not recorded) | ✅ Purchased / 🧪 Not tested or calibrated | Analog output into ADC |
| DS18B20 (waterproof, 2 m cable) | Soil temperature | 1 | 1 | ✅ Purchased | 1-Wire; needs 4.7 kΩ pull-up between DATA and 3.3 V if not already on the module |
| AHT20 + BMP280 combo breakout | Air temperature, humidity (AHT20), pressure (BMP280) | 1 | 1 | ✅ Purchased | Shared I²C bus; BMP280 does **not** measure humidity |
| Solenoid valve, Normally Closed, DN15 / 1/2", 12 V DC | Irrigation control | 1 | 1 | ✅ Purchased | Coil current and minimum operating pressure not yet verified |
| MOSFET driver module | Valve switching | 1 | 1 | ✅ Purchased | Flyback protection not yet confirmed |
| External adapter, 220 V AC → 12 V DC (~2 A) | Main power | 1 | 1 | ✅ Purchased | Only point in the system where mains voltage exists |
| DC female panel connector, 5.5 × 2.1 mm | Power inlet | 1 | Not recorded | 📋 Planned | — |
| LM2596 buck converter | 12 V → 5 V for ESP32-C3 | 1 | Not recorded | 📋 Planned | — |
| Screw terminal block, 2-pin | POWER IN, VALVE | 2 | Not recorded | 📋 Planned | — |
| Screw terminal block, 3-pin | SOIL LEFT, SOIL RIGHT, SOIL TEMP | 1 | Not recorded | 📋 Planned | — |
| Screw terminal block, 4-pin | AIR SENSOR / I²C, SPARE | 1 | Not recorded | 📋 Planned | — |
| 4.7 kΩ resistor | DS18B20 1-Wire pull-up | 1 | Not recorded | 📋 Planned | Only needed if not already on the DS18B20 module |
| Enclosure (3D printed) | Electronics housing | 1 | 0 | 📋 Planned | See [`../enclosure/README.md`](../enclosure/README.md) |
| Cable glands | Weatherproof cable entry into enclosure | TBD | 0 | 📋 Planned | With drip loop |

## Irrigation plumbing (not electronics, tracked here for now)

| Component | Purpose | Required qty | Purchased qty | Status | Notes |
|---|---|---|---|---|---|
| PE mainline tubing, 16 mm | Main irrigation line | TBD | 0 | 📋 Planned | — |
| Microtube, 4 mm | Dripper feed lines | TBD | 0 | 📋 Planned | — |
| Drippers | Point watering at plants | TBD | 0 | 📋 Planned | — |
| Filter | Protect drippers from debris | TBD | 0 | 📋 Planned | Needed if source water isn't already filtered |
| Pressure reducer | Match supply pressure to drip system spec | TBD | 0 | 📋 Planned | Needed depending on actual supply pressure |
