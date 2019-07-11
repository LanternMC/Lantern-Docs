# Dimension Ticks

Minecraft assigns each dimension its own portion of every game tick. First the
Overworld is processed, and then The End, and finally The Nether. In each of
these dimension-specific ticks, various events happen that a data pack may wish
to modify. However, data packs alone are limited to the very beginning of a game
tick (`#minecraft:tick` or `schedule`), and therefore may not be able to
perfectly detect events from a dimension tick before they influence the world.

Back when command blocks were used instead of data packs, this was hardly an
issue to consider. Nearly all events happen in the Overworld, where the command
blocks were, and command blocks actually run at the perfect time within the
dimension-specific ticks. Unfortunately, it is impossible for data packs to
replicate this once-ubiquitous timing without relying on a command block.

Therefore, Lantern includes a repeating command block in each forceloaded chunk,
so that data packs may simply hook into the tag(s) for the dimensions in which
they need to run functions in. The tags available are listed in this table:

|             Tag              | Dimension  |
|:----------------------------:|:----------:|
| `#lantern.1:tick_overworld`  | Overworld  |
| `#lantern.1:tick_the_nether` | The Nether |
|  `#lantern.1:tick_the_end`   | The End    |

There is an additional tag--`#lantern.1:tick_dimension`. This tag runs each time
one of the above tags runs, making it useful if your data pack has a single
function that needs to run with the dimension-specific timing for every
dimension.

Dimension ticks can be disabled, as they do cause a slight amount of runtime
overhead, and serve a rather niche purpose. Read the [Distributing Lantern] page
to learn how to disable this feature.

[Distributing Lantern]: https://lanternmc.com/docs/06-00-distributing-lantern/
