# Shulker Box

```text
-30000000 0 8882
```

Shulker boxes have a very special property, making them stand out even from
other containers--the way a shulker box's contents are dropped is controlled by
the loot table, rather than the game's code. With the correct loot table, a
shulker box's contents can be funneled anywhere with the right `loot` command,
without interfering with how shulker boxes drop in survival.

Being able to funnel a shulker box's contents is useful primarily because it is
the only reliable way to dynamically modify the player's inventory, ender chest,
and equipped armor. Additionally, it is a great way to drop large quantities of
natural-looking items on the ground at once (with `loot spawn`).

Lantern replaces the `minecraft:yellow_shulker_box`'s loot table, and the
shulker box at `-30000000 0 8882` is a yellow shulker box. To funnel the
contents of the shulker box, use the following command:

```bash
loot ... mine -30000000 0 8882 minecraft:air{drop_contents:1b}
```

Needless to say, modifying the `minecraft:yellow_shulker_box` loot table will
likely break this functionality for your data pack and all data packs that rely
on it. Lantern is not the only forceloaded chunk library that uses this exact
loot table--Minecraft Phi and AESTD do as well. If you wish for your data pack
to be compatible with the greater world, do not modify the loot table.
