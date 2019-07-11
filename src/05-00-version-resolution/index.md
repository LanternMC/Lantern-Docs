# Version Resolution

For simple data packs, confirming the versions of any dependencies in
`#lantern.1:resolve` is sufficient for the data pack to load. However, some
data packs, such as Lantern itself, have more complex loading processes. For
example, a data pack made to be bundled with other data packs should be aware
that multiple versions of the same data pack may be loaded at once. In this
case, only one version of the pack should be allowed to load.

A data pack aware of multiple versions would look like this:

```js
// #lantern.1:resolve
{
    "values": [
        "#example:enumerate",
        "#example:resolve"
    ]
}
```

```js
// #example:enumerate
{
    "values": [
        "example:v1/enumerate"
    ]
}
```

```js
// #example:resolve
{
    "values": [
        "example:v1/resolve"
    ]
}
```

```bash
# example:v1/enumerate
execute if score lantern lantern.versions matches 1 unless score example lantern.versions matches 1.. run scoreboard players set example lantern.versions 1
```

```bash
# example:v1/resolve
execute if score example lantern.versions matches 1 run function example:v1/initialize
```

```bash
# example:v1/initialize
say example data pack initialized!
```

In simple cases, this `example` data pack functions identically to the example
on the [Getting Started] page. However, the difference is that it will not
initialize if a conflicting future version is present at the same time. Instead,
the conflicting future version would be the one to initialize.

[Getting Started]: https://lanternmc.com/docs/01-00-getting-started/
