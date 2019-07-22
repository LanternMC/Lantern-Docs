# Bow Dropper

```
-30000000 0 8884
```

Sometimes, one may wish to evaluate a loot table to obtain a numeric result (for
example, a value based on the current biome, which is otherwise opaque to
commands). The easiest way to do this is setting an NBT tag containing the
desired result on the generated item. However, to avoid having to check NBT, one
can instead generate multiple unstackable items and use `execute store` to count
how many were created.

The issue with the unstackable item approach is that one is required to use
`loot spawn`, as the `result` of `loot replace` or `loot insert` is limited by
the number of slots available. This results in unnecessary item entities being
spawned, which makes the approach rather difficult to justify.

There is, however, a strange workaround that allows `loot insert` to function
just as well as `loot spawn`. The way it works is an implementation detail--just
know that if you make a loot table that drops bows and `loot insert` into the
block at `-30000000 0 8884`, the `result` you get will be the number of bows
dropped, even though the dropper has no room for them.

Overall, this bow dropper fills a small niche, but including it in Lantern does
not introduce extra overhead, and it is a useful tool for projects that use
computational loot tables.

**The bow dropper must not be modified unless the modification is done with
`loot insert`!**
