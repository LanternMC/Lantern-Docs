# Ordering

Lantern's version resolution process gives the data pack developer full control
over dependency management. However, Minecraft itself has no mechanism to ensure
that a dependency will load and initialize before your own data pack. This has
lead to packs exposing their own tags that run when they successfully load,
which fragments the code of your own data pack, especially if you rely on
multiple libraries that use this approach.

There is another way to ensure that dependencies load before dependent
packs--placing the entries in `#lantern.1:resolve` for the dependency above the
entries for the dependent pack. If this sounds familiar, it is because this is
exactly what is recommended when [bundling] data packs together.

Guaranteeing load order is technically possible without bundling, however it
requires you to provide your own, empty function tags for every dependency you
have. Keep this method in mind, because although bundling is great for many
practical use cases, it does not make sense for every data pack.

**Note that the ordering only works in the way described above. You cannot
reliably execute before or in the middle of a dependency's tags, however you
*can* force your data pack's execution to occur afterwards!**

[bundling]: https://lanternmc.com/docs/05-02-bundling/
