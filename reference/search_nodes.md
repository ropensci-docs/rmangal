# Query nodes

Search for networks by querying the nodes table. If the `query` is a
character string, then all character columns in the table are searched
and the entries for which at least one partial match was found are
returned. Alternatively, a named list can be used to look for an exact
match in a specific column (see Details section)

## Usage

``` r
search_nodes(query, ...)
```

## Arguments

- query:

  either a character string including a single keyword or a named list
  containing a custom query (see details section below). Note that if an
  empty character string is passed, then all available entries are
  returned.

- ...:

  Additional arguments passed to
  [`rmangal_request()`](https://docs.ropensci.org/rmangal/reference/rmangal_request.md),
  including the argument `cache` that allows requests caching.

## Value

An object of class `mgSearchNodes`, which basically is a `data.frame`
object including taxa that are matching the query and corresponding
information. All networks in which taxa are involved are also attached
to the `data.frame`.

## Details

Names of the list should match one of the column names within the table.
For the `nodes` table, those are:

- `id`: unique identifier of the nodes;

- `original_name`: taxonomic name as in the original publication;

- `node_level`: either population, taxon or individual;

- `network_id`: Mangal network identifier.

Note that for lists with more than one element, only the first element
is used, the others are ignored. An example is provided below.

## References

- <https://mangal.io/#/>

- <https://mangal-interactions.github.io/mangal-api/#nodes>

## See also

[`search_taxonomy()`](https://docs.ropensci.org/rmangal/reference/search_taxonomy.md)

## Examples

``` r
# \donttest{
res_acer <- search_nodes("Acer")
res_926 <- search_nodes(list(network_id = 926))
# }
```
