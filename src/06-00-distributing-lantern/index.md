# Distributing Lantern

At this point, you should have a fairly good understanding of what Lantern
offers, as well as an understanding of the version resolution process. Now you
may be wondering how to distribute Lantern alongside your data pack.

For many data packs, [bundling] is a recommendation. It's good practice, and
makes it easier for end users. However, for Lantern, bundling is a *requirement*
of distribution. This is because of the version resolution process--if your data
pack goes through version resolution, and then Lantern is unloaded, your data
pack may very likely be in an invalid state. The scoreboards suggest that
Lantern or any other dependencies were initialized, but this is only because
they were not cleared on reload.

To package your data pack for release, take Lantern's `data` folder from the
`master` branch of the GitHub repository, merge it with your own `data` folder,
and handle any function tag conflicts as described on the [bundling] page.

## Configuring Dimension Tags

The dimension tags offered by Lantern are an optional feature, although they are
enabled by default. To avoid them running in cases in which they are not
required, bundle Lantern with your data pack and delete the following file:

```text
data/lantern.1/functions/flags/enable_dimension_tags.mcfunction
```

[bundling]: https://lanternmc.com/docs/05-02-bundling/
