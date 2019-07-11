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
