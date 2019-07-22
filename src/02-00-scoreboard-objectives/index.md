# Scoreboard Objectives

Lantern adds four scoreboard objectives, shown in the following table. The first
two objectives mainly aid version resolution, while the other two are mainly for
runtime data storage and calculations.

|   Objective Name   |                  Purpose                   | Persistent |
|:------------------:|--------------------------------------------|:----------:|
| `lantern.versions` | Track versions of loaded data packs        |     No     |
| `lantern.flags`    | Store basic (boolean) configuration flags  |     No     |
| `lantern.const`    | Define constants used in calculations      |     No     |
| `lantern.global`   | Store arbitrary data that survives reloads |    Yes     |

`lantern.versions` and `lantern.flags` are guaranteed to be available during
version resolution, regardless of whether the expected Lantern version loaded
successfully. However, `lantern.global` and `lantern.const` must not be relied
on without confirming that `lantern lantern.versions` is 1.

`lantern.const` is not strictly for constant values; its precise purpose is to
store values that are finalized during or soon after version resolution and do
not require information from previous reloads. This means that it can also be
used for dynamic settings, not just hardcoded values.

## Temporary Globals

Fake players prefixed with `#` on the `lantern.global` objective are considered
temporary, and data packs may reset or overwrite these values without
restriction. This provides an easy way to perform calculations without needing
to fully namespace every involved variable.

```
execute store result score #result lantern.global run ...
```

## Numeric Constants

Creating a fully namespaced fake player for every numeric constant, no matter
how simple, would quickly prove tedious. Instead, simply name the constant by
its value with a `$` prefix, like this:

```
scoreboard players set $10000 lantern.const 10000
```
