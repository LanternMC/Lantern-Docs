# Bundling

When a data pack has dependencies, it can quickly become a burden for the user
to manage and install all of them. This is why it can be useful to merge the
dependencies with the final data pack ZIP before you distribute your data pack
to your users.

Not all data packs are made to support this, and most that claim to support
bundling will break if another data pack bundles the dependency. The use of
version resolution features as described on the previous page combined with
including the version number in the actual folder names, however, can make
bundling work gracefully, even when multiple data packs bundle different
versions of the same dependency.

To bundle a data pack, simply merge its `data` folder with your data pack's
`data` folder. There should not be any conflicts, unless your dependency makes
use of the same function tags that you make use of. To resolve these conflicts,
place the entries of your dependency *above* your own entries in each affected
function tag.

Bundling can be tedious and error-prone when done manually. However, there is
not currently a general-purpose tool to bundle compatible data packs. In the
near future, Lantern will publish a standard for data packs that can be used to
make the version resolution and bundling processes much simpler.
