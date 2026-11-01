# Moose.HapisMods

A collection of Harmony mods for Rust powering the Hapis custom map.

## Note
These plugins have been passed around many times over the years and are quite literally a total mess. If you feel so inclined to clean them up and fix/add features, all PRs are welcome. 

## Mods

- **Hapis.CargoPath** — Tracks Cargo Ship spawn/stop points read from the map data. Also reads the cargo path from RustEdit 2 maps.
- **Hapis.Deployables** — Manages custom deployable prefabs saved in the map data.
  - Spawns RustEdit 2 map entities
  - RustEdit 2 settings: indestructible entities, sign images and radiation zones
  - Custom map signs can't be drawn on or picked up (admin with god and fly on can)
  - Door spam E fix for map doors, no more stuck or out of sync doors
  - Door brushing fix, no more rubber-banding next to moving map doors
- **Hapis.IO** — Restores electrical/IO connections from map data and protects managed IO entities from damage and unauthorized access.
  - Reads IO from RustEdit 2 maps
  - Custom apartments: rooms numbered B1, B2... and kept after a restart, mailboxes linked
  - Guard toll opens the door for the payer and their team, closes when they walk away
  - Master key break-in works standing at the door
  - Elevator buttons move one floor at a time
- **Hapis.NPC** — Custom NPC spawner and AI behavior system (scientists, bandits, scarecrows, and more), including equipment and targeting logic.
  - Reads NPC spawners from RustEdit 2 maps
  - NPCs take cover, peek, reload, heal, strafe and retreat (when `UseRustEditNPCLogic` is off)
  - NPCs can't see through deployables or glass
- **Hapis.Extra** — Extra Hapis features.
  - Chinook drops at named spots (Legacy Offices, Milly, Sewer) on timers, `/chinook <name>` and `/chinookgone`
  - Old locked crates removed
  - Crude pumps and water sources filled
  - Taking oil and adaptors from pumps blocked
  - Startup console command
  - Config in `HarmonyConfig/HapisExtras.json`

## Shared
`src/Shared` is built into every mod: Title-Case logging and the RustEdit 2 map reader. All the mods work on RustEdit 1 and RustEdit 2 maps.
