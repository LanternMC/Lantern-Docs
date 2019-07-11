# Lantern

[Lantern] is a data pack library that provides forceloaded chunks and slightly
adjusts the data pack loading process. Lantern provides a very small API--the
bare minimum required to use the forceloaded chunks effectively.

Lantern offers the following features:

 - Load hooks that allow your data pack to verify the version of Lantern or other dependencies. 
 - Various scoreboard objectives used to hold global variables and data pack metadata.
 - A forceloaded chunk in each dimension, each containing a lectern, sign, and shulker box.
 - A permanent armor stand entity useful for computational loot tables and other calculations.
 - (Disableable) Per-dimension tick hooks required for certain entity-related operations.

This documentation serves as both a guide on the correct usage of Lantern and a
reference of its various features. However, it is not a guide to 1.14 commands
or the internal workings of data packs; the reader is expected to possess an
intermediate to advanced understanding of these concepts.

[Lantern]: https://github.com/lanternmc/lantern
