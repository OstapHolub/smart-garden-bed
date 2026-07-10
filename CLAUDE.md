# Repository guide for Claude Code

This is a hobby hardware/firmware project (Smart Garden Bed), not a
software product. A few conventions specific to this repo:

## Honesty rules

- Never mark a planned feature as done. Use the status markers already in
  `README.md` and `docs/roadmap.md`: ✅ Completed, 🚧 In progress,
  📋 Planned, 🧪 Not yet validated.
- Don't call anything "waterproof" without a documented test. Don't call
  irrigation "automatic" until it has actually run unattended and that's
  recorded in `docs/timeline.md` or `docs/lessons-learned.md`.
- BMP280 measures temperature and pressure, not humidity — AHT20 is the
  humidity sensor in the air sensor pair. Don't conflate them.
- Don't assign specific GPIO pins in `electronics/pinout.md` without
  checking the actual ESP32-C3 SuperMini pinout and boot-strapping pin
  constraints first.

## Structure

- `docs/photos/` holds web-sized, privacy-checked copies of build photos
  (resized/recompressed with `sips`, PII removed via pixelation where
  needed). Originals stay outside the repo (`~/Desktop/photos`) and are
  never modified.
- `mechanical/fusion360/` will hold the Fusion 360 source once it's added;
  as of the initial repository build, no `.f3d` file is present yet.
- `firmware/` is intentionally empty right now (no PlatformIO project, no
  code). Don't scaffold firmware here unless the user explicitly asks for
  it — this was deliberately deferred until electronics prototyping
  starts and there's real hardware to write against.
- Licensing is split by content type; see `LICENSE-DECISION.md` before
  adding a blanket `LICENSE` file.

## Working with photos

If more photos are added later, follow the pattern in
`docs/timeline.md`/`docs/photos/*`: rename to `dNN-short-description.jpg`,
recompress with `sips -s formatOptions 80`, and check for identifying
metadata or visible PII (license plates, faces, addresses) before adding
them to a public-facing directory.
