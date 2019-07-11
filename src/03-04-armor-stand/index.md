# Armor Stand

```text
cb-0-0-0-1
```

The NBT tags of entities can be useful for certain calculations, so Lantern
provides an armor stand with a UUID of `cb-0-0-0-1` for all data packs to use.
So long as data packs avoid killing this entity and ensure that it is returned
to the forceloaded chunk when they are not using it, there are no restrictions
on the use of `cb-0-0-0-1`.

The `HandItems` may be useful for computational loot tables, as `loot ... fish`
can take the `mainhand` or `offhand` of the current executor as arguments, and
loot tables have been experimentally suggested as a viable alternative to
command-based NBT checking.
