# Get a collection of networks

Retrieve a set of networks based on the results of one of the
`search_*()` function. The function also accepts a numeric vector of
Mangal network IDs.

## Usage

``` r
get_collection(x, ...)

# Default S3 method
get_collection(x, ...)

# S3 method for class 'mgSearchDatasets'
get_collection(x, ...)

# S3 method for class 'mgSearchNetworks'
get_collection(x, ...)

# S3 method for class 'mgSearchReferences'
get_collection(x, ...)

# S3 method for class 'mgSearchNodes'
get_collection(x, ...)

# S3 method for class 'mgSearchTaxonomy'
get_collection(x, ...)

# S3 method for class 'mgSearchInteractions'
get_collection(x, ...)
```

## Arguments

- x:

  `numeric` vector of Mangal network IDs or an object returned from any
  `search_*()` function.

- ...:

  arguments to be passed on to
  [`get_network_by_id()`](https://docs.ropensci.org/rmangal/reference/get_network_by_id.md).

## Value

Returns a object of class `mgNetworksCollection` which is a collection
(actually, a list) of `mgNetwork` objects
[`get_network_by_id()`](https://docs.ropensci.org/rmangal/reference/get_network_by_id.md)).

## Methods (by class)

- `get_collection(default)`: Get a collection of networks (default).

- `get_collection(mgSearchDatasets)`: Get a collection of networks from
  a `mgSearchDatasets` object.

- `get_collection(mgSearchNetworks)`: Get a collection of networks from
  a `mgSearchNetworks` object.

- `get_collection(mgSearchReferences)`: Get a collection of networks
  from a `mgSearchReferences` object.

- `get_collection(mgSearchNodes)`: Get a collection of networks from a
  `mgSearchNodes` object.

- `get_collection(mgSearchTaxonomy)`: Get a collection of networks from
  a `mgSearchTaxonomy` object.

- `get_collection(mgSearchInteractions)`: Get a collection of networks
  from a `mgSearchInteractions` object.

## See also

[`search_datasets()`](https://docs.ropensci.org/rmangal/reference/search_datasets.md),
[`search_interactions()`](https://docs.ropensci.org/rmangal/reference/search_interactions.md),
[`search_networks()`](https://docs.ropensci.org/rmangal/reference/search_networks.md),
[`search_nodes()`](https://docs.ropensci.org/rmangal/reference/search_nodes.md),
[`search_references()`](https://docs.ropensci.org/rmangal/reference/search_references.md),
[`search_taxonomy()`](https://docs.ropensci.org/rmangal/reference/search_taxonomy.md).

## Examples

``` r
# \donttest{
mg_2 <- get_collection(c(1076:1077))
mg_anemone <- get_collection(search_networks(query = "anemone%"))
#> Found 16 networks.
# }
```
