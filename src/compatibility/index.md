# Compatibility

This page is a reference for what is required for a data pack to be considered
compatible with Lantern. This is a useful reference for external data packs 

## Location

In each dimension, the cuboid from `-30000000 0 8880` to `-29999985 1 8895` is
reserved for Lantern internal use. Modifying blocks in this area is strictly
forbidden, except when specifically allowed in this documentation.

Additionally, data packs that depend on Lantern are encouraged to use the cuboid
from `-30000000 2 8880` to `-29999985 255 8895` for any purpose, and should not
impose additional restrictions on these positions.

Therefore, a library that wishes to provide its own forceloaded utilities should
use its own chunk, rather than the chunk at `-30000000 0 8880`.

## Entity + UUID

The UUID `cb-0-0-0-1` is reserved for an armor stand provided by Lantern. Data
packs must not kill the armor stand or not leave it outside of a Lantern
forceloaded chunk. Additionally, summoning another entity with the same UUID is
expressly forbidden.

## Loot Table

The `minecraft:yellow_shulker_box` loot table is overridden by Lantern. For a
data pack to be compatible with Lantern, it must not make its own changes to
this loot table. However, it may include a verbatim copy of the loot table (for
example, Minecraft Phi and AESTD do this).

A copy of Lantern's `minecraft:yellow_shulker_box` loot table is available
[here][yellow_shulker_box].

[yellow_shulker_box]: https://lanternmc.com/yellow_shulker_box.json
