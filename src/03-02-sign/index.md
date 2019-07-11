# Sign

```text
-30000000 0 8881
```

Text components are a must-have for any data pack that wishes to display styled
or translated text to the end user. Additionally, they are the only way to
display dynamic values such as `score`, `selector`, and `nbt`. However, these
more advanced text components do not work in every case--notably, they fail with
item names, entity names, and container names.

In the few contexts where advanced text components are allowed, they are
immediately translated into simple components. If a data pack places an advanced
text component into one of these contexts, it could then copy the simplified
text component to any other location (so long as it can be reached with
`data modify`).

Lantern provides a sign at `-30000000 0 8881` so that data packs can use the
`Text1` - `Text4` tags for advanced text component resolution. Note that the
execution context is completely ignored by signs, so `@s` will not work.
