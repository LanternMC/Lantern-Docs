# Forceloaded Chunks

For each of the three dimensions in Minecraft, Lantern forceloads the chunk at
`-30000000 0 8880`. The following table gives a brief overview of the blocks in
this chunk:

|      Position      |     Block     |          Purpose          |
|:------------------:|---------------|---------------------------|
| `-30000000 0 8880` | [Lectern]     | Arbitrary data storage    |
| `-30000000 0 8881` | [Sign]        | Text component resolution |
| `-30000000 0 8882` | [Shulker Box] | General item manipulation |
| `-30000000 0 8883` | [Shulker Box] | Single item manipulation  |
| `-30000000 0 8884` | [Dropper]     | Advanced loot table usage |

Additionally, an [armor stand] with a UUID of `cb-0-0-0-1` is placed in the
Overworld's chunk.

All positions in these chunks with a Y of 0 or 1 are reserved by Lantern for
future use. Other data packs may freely use positions with greater Y values, but
there is no guarantee that blocks placed in those positions will persist for any
period.

The next five pages will expand upon the roles of each of the forceloaded
utilities listed above.

[Lectern]: https://lanternmc.com/docs/03-01-lectern/
[Sign]: https://lanternmc.com/docs/03-02-sign/
[Shulker Box]: https://lanternmc.com/docs/03-03-shulker-boxes/
[Dropper]: https://lanternmc.com/docs/03-04-bow-dropper/
[armor stand]: https://lanternmc.com/docs/03-05-armor-stand/
