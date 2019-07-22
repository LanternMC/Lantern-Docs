# Armor Stand

```text
cb-0-0-0-1
```

The NBT tags of entities can be useful for certain calculations, so Lantern
provides an armor stand with a UUID of `cb-0-0-0-1` for all data packs to use.
Data packs may use `cb-0-0-0-1` for whatever they want, so long as they return
the entity to a forceloaded chunk once they are done, and refrain from killing
it.

The `HandItems` may be useful for computational loot tables, as `loot ... fish`
can take the `mainhand` or `offhand` of the current executor as arguments, and
loot tables have been experimentally suggested as a viable alternative to
command-based NBT checking.
