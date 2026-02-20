# Angel Islands
Adds Floating Islands Over Oceans to Vanilla Worlds. Not compatible with terrain mods.

## Sky river generation notes
The datapack now keeps river shaping decoupled from the core island density so river channels no longer hollow out the underside of islands.

Implemented approach:
- `angel_islands:ridges/islands` now always uses the `no_rivers` ridges signal.
- `angel_islands:terrain/final` now uses `ridges/no_rivers` for density routing.
- New `angel_islands:terrain/river_support` adds a small density reinforcement under river centerlines to keep the landmass solid under water channels.

If you want wider or deeper rivers, tune `Angel_Islands/data/minecraft/worldgen/noise_settings/overworld.json` river `noise_threshold` bands, then adjust `terrain/river_support.json` (`max_exclusive` and gradient strength) to match.
