# Changelog

## rmangal 2.2.2

CRAN release: 2026-01-21

- Fix vcr loading and skip tests if missing.

## rmangal 2.2.1

- Fix URLs to avoid CRAN notes.

## rmangal 2.2.0

- Expose core functions
  [`rmangal_request()`](https://docs.ropensci.org/rmangal/reference/rmangal_request.md)
  and
  [`rmangal_request_singleton()`](https://docs.ropensci.org/rmangal/reference/rmangal_request.md).
- [`print.mgNetworksCollection()`](https://docs.ropensci.org/rmangal/reference/get_network_by_id.md)
  gains an argument `n` to control the number of networks displayed.
- The option `rmangal.verbose` controls the verbosity of the package
  (see [\#116](https://github.com/ropensci/rmangal/issues/116)).
- The core of the client has been rewritten using `httr2`, `httr` and
  `memoise` has been removed from the dependency list. The new function
  [`rmangal_request()`](https://docs.ropensci.org/rmangal/reference/rmangal_request.md)
  is now the main request function using `httr2` (see
  [\#106](https://github.com/ropensci/rmangal/issues/106)).

## rmangal 2.1.3

CRAN release: 2023-03-30

- Remove `USAboundaries` and `taxize` from the list of ‘Suggested’
  packages (see
  [\#114](https://github.com/ropensci/rmangal/issues/114)).

## rmangal 2.1.2

CRAN release: 2023-01-27

- Fixtures are now written in JSON (see
  [\#112](https://github.com/ropensci/rmangal/issues/112)).

## rmangal 2.1.1

CRAN release: 2022-05-15

- [`inherits()`](https://rdrr.io/r/base/class.html) is now used to test
  classes.
- `purrr` is no longer listed as an imported package.
- Add lintr workflow to automatically check stylistic errors.
- Summary method for `mgNetwork` objects now reports nodes and properly
  (see [\#108](https://github.com/ropensci/rmangal/issues/108)).

## rmangal 2.1.0

CRAN release: 2021-11-24

- All examples are within the `\donttest` tag (see
  [\#100](https://github.com/ropensci/rmangal/issues/100)).
- [`get_collection()`](https://docs.ropensci.org/rmangal/reference/get_collection.md)
  methods always return an object of class `mgNetworksCollection` (see
  [\#100](https://github.com/ropensci/rmangal/issues/100)).
- [`get_network_by_id()`](https://docs.ropensci.org/rmangal/reference/get_network_by_id.md)
  gains an argument `force_collection` to force the class collection
  (see [\#100](https://github.com/ropensci/rmangal/issues/100)).
- Vignette now precomputed (see
  [\#100](https://github.com/ropensci/rmangal/issues/100)).
- Tests now use `vcr` (see
  [\#100](https://github.com/ropensci/rmangal/issues/100)).
- Travis and Appveyor removed, use GitHub Actions (see
  [\#100](https://github.com/ropensci/rmangal/issues/100)).
- [`avail_type()`](https://docs.ropensci.org/rmangal/reference/avail_type.md)
  is no longer exported.

## rmangal 2.0.2

CRAN release: 2020-10-13

- Fix a minor bug in
  [`search_datasets()`](https://docs.ropensci.org/rmangal/reference/search_datasets.md)
  related to absent networks attached on a dataset (see
  [\#97](https://github.com/ropensci/rmangal/issues/97) and
  [\#98](https://github.com/ropensci/rmangal/issues/98)).
- Update Travis CI environment test (`travis.yml`).

## rmangal 2.0.1

- Fix a minor bug in the print method for `mgNetwork` objects see
  [\#94](https://github.com/ropensci/rmangal/issues/94).
- Fix broken URIs in README.
- Remove `mapview` from vignette (CRAN issue with missing PhantomJS).

## rmangal 2.0.0

CRAN release: 2019-10-03

- Revisions see
  <https://github.com/ropensci/software-review/issues/332>;
- Add summary method \[#87\].
- `mg_to_igraph` is now
  [`as.igraph()`](https://r.igraph.org/reference/as.igraph.html).
- [`search_references()`](https://docs.ropensci.org/rmangal/reference/search_references.md)
  has been rewritten \[#85\].
- Vignette now includes examples to use `tidygraph` and `ggraph`.
- `geom` column has been removed from `mgSearchInteractions` objects.
- `sf` features are only used in
  [`search_networks_sf()`](https://docs.ropensci.org/rmangal/reference/search_networks.md)
  and when argument `as_sf` is set to `TRUE` \[#89\].
- Query with spatial (`sf`) objects are handle in `query_networks_sf()`
  that is now exported.

## rmangal 1.9.0.9000

- Version submitted to ROpenSci for review;
- Added a `NEWS.md` file to track changes to the package.
