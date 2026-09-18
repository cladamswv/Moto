# DIRTLINE MX Arcade 3.2.1 hotfix

Fixes the Godot 4.3 runtime parse failure in `Main.gd` where `bx` and related race-start locals relied on Variant type inference from arrays. The race-start arrays and derived positions now use explicit GDScript types.

The GitHub runtime smoke test marker is now `DIRTLINE_SMOKETEST_V321_PRESENTATION_PARSESAFE`.
