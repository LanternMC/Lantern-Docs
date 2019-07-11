# Compatibility

This page is a reference for what is required for a data pack to be considered
compatible with Lantern. This may be useful not only for data packs that depend
on Lantern, but also those that do not.

## Location

The cuboid from `-30000000 0 8880` to `-29999985 1 8895` is reserved for Lantern
internal use. Modifying blocks in this area is strictly forbidden, except when
specifically allowed in this documentation.

## UUID

The UUID `cb-0-0-0-1` is reserved for an armor stand provided by Lantern. Data
packs that do not depend on Lantern may use neither the armor stand nor its
UUID.

## Loot Table

The `minecraft:yellow_shulker_box` loot table is overridden by Lantern. For a
data pack to be compatible with Lantern, it must not make its own changes to
this loot table. However, it may include a verbatim copy of the loot table (for
example, Minecraft Phi and AESTD do this).

A copy of Lantern's `minecraft:yellow_shulker_box` loot table is available
[here][yellow_shulker_box].

[yellow_shulker_box]: https://lanternmc.com/yellow_shulker_box.json
