# Resolution Tags

Lantern offers two tags to assist with version resolution. The first is
`#lantern.1:resolve`, which suffices for nearly every use. Data packs can check
for dependencies and then initialize themselves, or expose themselves as
dependencies for other data packs to use. However, there are some features that
may be augmented if processing is done after all *dependent* packs have been
initialized.

It is for these features that Lantern offers the `#lantern.1:post_resolve` tag,
which runs immediately after the `#lantern.1:resolve` tag. Post-resolution is a
time for library data packs to use values given by their dependent packs to aid
in an extended initialization process. For example, Lantern waits until
post-resolution to determine whether dimension tags will be enabled, as it is
only then when one can be sure that all data packs communicated their
preference.
