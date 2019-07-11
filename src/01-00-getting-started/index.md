# Getting Started

To start working with Lantern, download the latest [unbundled release] and place
it in your world's `datapacks` folder. This method is perfect for learning how
Lantern works, but is not suitable for distributing Lantern to end users.

When you depend on Lantern, rather than using the `#minecraft:load` tag to
initialize your data packs, you use `#lantern.1:resolve`. The function called
by this tag is responsible for checking Lantern's major version (as multiple
versions of Lantern may attempt to load at once).

Here is an example of a data pack that uses Lantern's tag:

```js
// #lantern.1:resolve
{
    "values": [
        "#example:resolve"
    ]
}
```

```bash
# example:resolve
execute if score lantern lantern.versions matches 1 run function example:initialize
```

```bash
# example:initialize
scoreboard players set example lantern.versions 1
say example data pack initialized!
```

The point of this process is to allow data packs to validate that the Lantern
features they were built to expect are indeed supported. As an example,
`example:initialize` can safely assume that the forceloaded chunks exist
and have blocks in the locations they should be.

In `example:initialize`, you may note that an `example` version was set on the
scoreboard. This is good practice even if no other data packs depend on yours,
as it allows functions called from `#minecraft:tick` or advancement triggers to
confirm your data pack's successful initialization.

The version resolution process will be revisted on [a later page].

[unbundled release]: https://github.com/lanternmc/lantern/releases
[a later page]: https://lanternmc.com/docs/05-00-version-resolution/
