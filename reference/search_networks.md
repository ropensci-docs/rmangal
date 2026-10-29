# Query networks

Search over all networks using a keyword, a custom query or a spatial
object If the `query` is a character string, then all character columns
in the table are searched and the entries for which at least one partial
match was found are returned. Alternatively, a named list can be used to
look for an exact match in a specific column (see 'Details' section).

## Usage

``` r
search_networks(query, ...)

search_networks_sf(query_sf, ...)
```

## Arguments

- query:

  either a character string including a single keyword or a named list
  containing a custom query (see details section below), or a spatial
  object (see the description of `query_sf`). Note that if an empty
  character string is passed, then all networks available are returned.

- ...:

  Further arguments passed to
  [`rmangal_request()`](https://docs.ropensci.org/rmangal/reference/rmangal_request.md),
  including the argument `cache` that allows requests caching.

- query_sf:

  a spatial object of class `sf` used to search in a specific
  geographical area.

## Value

An object of class `mgSearchNetworks`, which is a `data.frame` object
with all networks information.

## Details

Names of the list should match one of the column names within the table.
For the `networks` table, those are

- id: unique identifier of the network;

- all_interactions: false interaction can be considered as real false
  interaction

- dataset_id: the identifier of the dataset;

- public: network publicly available;

Note that for lists with more than one element, only the first element
is used, the others are ignored. An example is provided below.

## Functions

- `search_networks_sf()`: Search networks within a spatial object passed
  as an argument. Note that `sf` must be installed to use this function.

## References

- <https://mangal.io/#/>

- <https://mangal-interactions.github.io/mangal-api/#networks>

## Examples

``` r
# \donttest{
mg_insect <- search_networks(query = "insect%")
#> Found 14 networks.
# Retrieve the search results
nets_insect <- get_collection(mg_insect)
# Spatial query
if (requireNamespace("sf", quietly = TRUE)) {
  area <- sf::st_read(system.file("shape/nc.shp", package = "sf"))
  networks_in_area <- search_networks_sf(area)
  plot(networks_in_area)
} else {
  cli::cli_warn("Package sf is missing")
}
#> Reading layer `nc' from data source 
#>   `/github/home/R/x86_64-pc-linux-gnu-library/4.6/sf/shape/nc.shp' 
#>   using driver `ESRI Shapefile'
#> Simple feature collection with 100 features and 14 fields
#> Geometry type: MULTIPOLYGON
#> Dimension:     XY
#> Bounding box:  xmin: -84.32385 ymin: 33.88199 xmax: -75.45698 ymax: 36.58965
#> Geodetic CRS:  NAD27

# Retrieve network ID 5013
net_5013 <- search_networks(query = list(id = 5013))
#> Found 1 network.
# Network(s) of dataset ID 19
mg_19 <- search_networks(list(dataset_id = 19))
#> Found 1 network.
# }
```
