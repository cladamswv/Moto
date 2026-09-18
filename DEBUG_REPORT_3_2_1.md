# DIRTLINE MX Arcade 3.2.1 Debug Report

Observed GitHub Actions failure: Godot 4.3 rejected `var bx := start_pos_x + start_offsets[i]` because `start_offsets[i]` was Variant-typed and no set type could be inferred.

Fix: race-start arrays and all derived spawn positions in `Main.gd` now have explicit types. `Main.gd` contains no local `var name := ...` declarations. CI verifies the hotfix before runtime.

Static package audit after repair:
- 63 `res://` references checked
- 7 GDScript files checked for balanced delimiters
- 23 GLB files checked for valid binary glTF headers
- 50 image files verified
- 15 WAV files verified
- 4 OGG files present
- 0 missing-resource errors
- 0 static audit warnings

Final Godot runtime/export validation remains in GitHub Actions because Godot 4.3 is not installed in the packaging container.
