# Lectern

```text
-30000000 0 8880
```

Items in Minecraft have a special NBT compound called `tag`. This NBT tag can
contain any other NBT tags, even values that Minecraft would never itself read.
Therefore, item NBT is a useful tool for storing long-term data and applying
transformations on NBT meant for another location.

This is why Lantern provides a forceloaded lectern--lecterns do not tick, have
very low serialization overhead, and can store exactly one item. Therefore,
the lectern's `Book.tag` is the best option for your arbitrary NBT storage
needs.

All data packs that use Lantern are free to modify the `Book.tag` of the lectern
at `-30000000 0 8880`, so long as they do not delete or overwrite `Book.tag`
completely. It is, however, highly recommended that data packs add their
namespace to the NBT path they choose to use. An `example` data pack would
modify `Book.tag.example` to avoid conflicting with other data packs.

The lectern provided by Lantern cannot resolve text components. Use [the sign]
instead.

## Provided Tags

Lantern currently only provides one tag of its own within the lectern.

`Book.tag.lantern.Dimension` contains an `int` corresponding to the dimension
the lectern is in. This allows data packs to confirm their current dimension
without using an entity's `Dimension` tag. The value of this tag is `0` for the
Overworld, `-1` for The Nether, and `1` for The End.

[the sign]: https://lanternmc.com/docs/03-02-sign/
