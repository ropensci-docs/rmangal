# Query datasets

Identify relevant datasets using a keyword or a custom query. If the
`query` is a character string, then all character columns in the table
are searched and the entries for which at least one partial match was
found are returned. Alternatively, a named list can be used to look for
an exact match in a specific column (see Details section).

## Usage

``` r
search_datasets(query, ...)
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

An object of class `mgSearchDatasets`, which basically is a `data.frame`
object including all datasets corresponding to the query. For each
dataset entry, the networks and the original reference are attached.

## Details

If `query` is a named list, the name used should be one of the
following:

- `id`: unique identifier of the dataset

- `name`: name of the dataset

- `date`: date (`YYYY-mm-dd`) of the corresponding publication

- `description`: a brief description of the dataset

- `ref_id`: the Mangal identifier of the dataset

Note that for lists with more than one element, only the first element
is used, the others are ignored. Examples covering custom queries are
provided below.

## References

- <https://mangal.io/#/>

- <https://mangal-interactions.github.io/mangal-api/#datasets>

## Examples

``` r
# \donttest{
# Return all datasets (takes time)
# all_datasets <- search_datasets("")
# all_datasets
# class(all_datasets)
# Search with keyword
mg_lagoon <- search_datasets(query = "lagoon")
#> Found 2 datasets.
# Search with a custom query (specific column)
mg_kemp <- search_datasets(query = list(name = "kemp_1977"))
#> Found 1 dataset.
mg_16 <- search_datasets(query = list(ref_id = 16))
#> Found 1 dataset.
# }
```
