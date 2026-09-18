# DIRTLINE MX Arcade 3.2.2 Debug Report

Regression target: Android gameplay capture showing missing touch controls, silent motorcycles, and a frozen starting grid.

## Fixes
- Touch HUD: bottom anchored control clusters, explicit z-order, named controls, and Godot 4.3-compatible `icon_max_width` theme override.
- Race start: live-race watchdog and explicit grid activation helper.
- Audio: audible player idle from staging, louder engine mix, lower race-music level, and AI motorcycle engine ambience.
- Presentation: START arch moved behind the grid and near-track billboards reduced so branding does not obscure the race view.
- CI: smoke test now requires visible touchscreen controls, active seven-rider grid, engine streams, player forward movement under simulated throttle, and AI forward movement.

## Static/media audit
- 71 `res://` references checked: 0 missing.
- 7 GDScript files checked for duplicate function declarations and mixed-tab indentation: 0 findings.
- 23 GLB files: valid glTF 2 binary headers and JSON chunks.
- 50 images: decoded successfully.
- 15 WAV files: valid PCM/WAVE with nonzero frames.
- 4 OGG music files: ffprobe validation passed.
- Exact regression guards passed for controls, race activation, audio, start-arch placement, and runtime smoke test coverage.

## Engine-level gate
The included GitHub Action uses Godot 4.3 headless to import the project and run `scripts/SmokeTest.gd` before Android export. It will not upload an APK unless the runtime checks pass.
