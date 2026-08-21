# Delightful-Blocks

A Forge mod for Minecraft 1.20.1 adding a set of decorative/ore blocks (bricks, pillars, desert sand, an "icey" block, ruin block, sand rock, and a topaz ore/block set). Originally generated with [MCreator](https://mcreator.net/) (mod id `delightfulblocks`, base package `net.mcreator.delightfulblocks`).

Source for this repo was reconstructed from the released mod jar (`Delightful_Blocks_1.0.0.jar`), which only contained resources and compiled `.class` files (no `.java` source was shipped in the jar).

## Layout

- `src/main/resources/` — mod resources extracted from the jar, laid out in the standard Forge/Gradle source-set location:
  - `META-INF/mods.toml` — mod metadata (Forge 1.20.1, loader `[47,)`)
  - `assets/delightfulblocks/` — blockstates, block/item models, textures, `en_us` lang file
  - `data/delightfulblocks/` — recipes, worldgen (configured/placed features for topaz ore), forge biome modifiers
  - `data/minecraft/tags/blocks/mineable/` — tool tags for the added blocks
  - `pack.mcmeta` — resource pack descriptor
- `compiled-reference/` — the original compiled `.class` files from the jar (`net/mcreator/delightfulblocks/...`), kept **as-is, undecompiled**, purely as a reference for what logic needs to be reimplemented as real `.java` source (blocks, items, ore worldgen feature, and the mod init/registration classes). These are not meant to be part of a Gradle build.

## What's missing

- Actual `.java` source under `src/main/java/net/mcreator/delightfulblocks/...` — the jar shipped compiled bytecode only. The classes in `compiled-reference/` show the package/class structure to reproduce (blocks: `BrickBlock`, `BrickPillarBlock`, `DesertSandBlock`, `IceyblockBlock`, `PillarblockBlock`, `RuinblockBlock`, `SandrockBlock`, `TopazBlockBlock`; items: `TopazItem`, `DelightfulBlocksItemItem`; worldgen: `TopazBlockFeature`; registration: `DelightfulblocksMod`, `DelightfulblocksModBlocks`, `DelightfulblocksModItems`, `DelightfulblocksModFeatures`, `DelightfulblocksModTabs`).
- A Gradle build (`build.gradle`, `gradle.properties`, ForgeGradle wrapper) to actually compile/package the mod — not present in the jar and not yet set up here.
