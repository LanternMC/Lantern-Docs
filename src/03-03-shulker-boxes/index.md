# Shulker Boxes

```text
-30000000 0 8882
```

```text
-30000000 0 8883
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

Lantern replaces the `minecraft:yellow_shulker_box`'s loot table, and provides
two different yellow shulker boxes. The shulker box at `-30000000 0 8882` is
free for any use, while the shulker box at `-3000000000 0 8883` must be used
only for its first slot (`Slot:0b` / `container.0`).

To funnel the contents of one of the shulker boxes, you must use `loot`'s `mine`
subcommand with a provided tool of `minecraft:air{drop_contents:1b}`. For
example, to give yourself the contents of the `-30000000 0 8882` shulker box,
use the following command:

```bash
loot give @s mine -30000000 0 8882 minecraft:air{drop_contents:1b}
```
