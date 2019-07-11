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

The lectern provided by Lantern is incapable of resolving text components.
[The sign] should be used instead.

[The sign]: https://lanternmc.com/docs/03-02-sign/
