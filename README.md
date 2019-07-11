# Lantern Documentation

This repository holds the source files for [Lantern]'s documentation.

The documentation can be viewed in compiled form at
[https://lanternmc.com/docs/][docs].

## Building

To build the Lantern documentation, install [mdBook] and [mdbook-html-taco],
then run `mdbook build` in this repository. Note that if you wish to host the
documentation elsewhere, you will need to change the `book.toml` to change the
root path and replace any absolute links in the book with your own.

## License

The Lantern documentation is licensed under the [MIT license].

### Contribution

Unless you explicitly state otherwise, any contributions intentionally submitted
for inclusion in the Lantern documentation by you shall be licensed as MIT,
without any additional terms or conditions.

[Lantern]: https://github.com/lanternmc/lantern
[docs]: https://lanternmc.com/docs/
[mdBook]: https://github.com/rust-lang-nursery/mdBook
[mdbook-html-taco]: https://github.com/alluet/mdbook-html-taco
[MIT license]: https://github.com/lanternmc/lantern-docs/blob/master/LICENSE
