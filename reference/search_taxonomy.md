# Query taxonomy

Search network by taxon names and unique taxonomic identifiers. This
function offers the opportunity to retrieve taxon based on (i) known
identifier such as the taxonomic serial number (TSN), GBIF ID etc. or
(ii) text search using partial match. Have a look at the list of
arguments to see the complete list of identifiers accessible. If any
unique identifier argument is used (i.e. tsn etc.), then `query` is
ignored. Moreover, if several taxonomic identifiers are specified, then
only the first one is considered.

## Usage

``` r
search_taxonomy(
  query,
  tsn = NULL,
  gbif = NULL,
  eol = NULL,
  col = NULL,
  bold = NULL,
  ncbi = NULL,
  ...
)
```

## Arguments

- query:

  a character string including a single keyword. Note that if an empty
  character string is passed, then all datasets available are returned.

- tsn:

  a `numeric`. Unique taxonomic identifier from Integrated Taxonomic
  Information System (\<itis.gov\>).

- gbif:

  a `numeric`. Unique taxonomic identifier from Global Biodiversity
  Information Facility (\<www.gbif.org\>).

- eol:

  a `numeric`. Unique taxonomic identifier from Encyclopedia of Life
  (\<eol.org\>).

- col:

  a `numeric`. Unique taxonomic identifier from Catalogue of Life
  (<https://www.catalogueoflife.org>).

- bold:

  a `numeric`. Unique taxonomic identifier from Barcode of Life
  (<https://boldsystems.org/>).

- ncbi:

  a `numeric`. Unique taxonomic identifier from National Center for
  Biotechnology Information (<https://www.ncbi.nlm.nih.gov>).

- ...:

  Further arguments passed to
  [`rmangal_request()`](https://docs.ropensci.org/rmangal/reference/rmangal_request.md),
  including the argument `cache` that allows requests caching.

## Value

An object of class `mgSearchTaxonomy`, which is a `data.frame` including
all taxa matching the query.

## Details

Taxon names of the `taxonomy` table were validated with TNRS (see
<https://tnrs.biendata.org>) and/or GNR (see
<https://resolver.globalnames.org/>). The taxon names in this table
might not be the taxon name documented in the original publication. In
order to identify relevant networks with the original name, use
[`search_nodes()`](https://docs.ropensci.org/rmangal/reference/search_nodes.md).

The validation of taxon names was performed by an automated procedure
and if there is any doubt, the original names recorded by authors should
be regarded as the most reliable information. Please report any issue
related to taxonomy at
<https://github.com/mangal-interactions/contribute/issues/new/choose/>.

## References

- <https://mangal.io/#/>

- <https://mangal-interactions.github.io/mangal-api/#taxonomy>

## See also

[`search_nodes()`](https://docs.ropensci.org/rmangal/reference/search_nodes.md)

## Examples

``` r
# \donttest{
search_taxonomy("Acer")
#> Found 5 taxa involved in 5 networks
#>     id     original_name node_level network_id taxonomy_id
#> 1 2629      Acer negundo      taxon         19           2
#> 2 2630  Acer saccharinum      taxon         19           3
#> 3 8895 Acer shirasawanum      taxon        948        3117
#> 4 8923 Acer ukurunduense      taxon        948        3144
#> 5 8930    Acer japonicum      taxon        948        3151
#>                 created_at               updated_at taxonomy.id
#> 1 2019-02-22T18:48:49.433Z 2019-02-22T18:48:49.433Z           2
#> 2 2019-02-22T18:48:49.465Z 2019-02-22T18:48:49.465Z           3
#> 3 2019-02-25T20:52:53.654Z 2019-02-25T20:52:53.654Z        3117
#> 4 2019-02-25T20:52:54.835Z 2019-02-25T20:52:54.835Z        3144
#> 5 2019-02-25T20:52:55.175Z 2019-02-25T20:52:55.175Z        3151
#>       taxonomy.name taxonomy.ncbi taxonomy.tsn taxonomy.eol taxonomy.bold
#> 1      Acer negundo          4023        28749       583069        100987
#> 2  Acer saccharinum         75745        28757       583072        101028
#> 3 Acer shirasawanum         66216           NA      5613162        485602
#> 4     Acer caudatum        290844           NA      2888949        102168
#> 5    Acer japonicum         47966       837855      2888970        448667
#>   taxonomy.gbif                     taxonomy.col taxonomy.rank
#> 1       3189866 90203e29e2f59e5754167f89b9eba3cc       species
#> 2       3189837 1582ed5db846e241f3e18da418a2a477       species
#> 3       7263086 25b4371fbbdc5b1cd43fad895050cc05       species
#> 4       7263099 1211e426bdec174da9a7526348c26fb9       species
#> 5       8010851 3388e995334d5638aeb11ef84f98b319       species
#>        taxonomy.created_at      taxonomy.updated_at
#> 1 2019-02-21T21:17:12.585Z 2019-06-14T15:20:36.273Z
#> 2 2019-02-21T21:17:12.637Z 2019-06-14T15:20:36.328Z
#> 3 2019-02-22T00:31:49.729Z 2019-06-14T15:24:56.217Z
#> 4 2019-02-22T00:31:52.729Z 2019-06-14T15:24:57.854Z
#> 5 2019-02-22T00:31:53.328Z 2019-06-14T15:24:58.251Z
# Retrieve higher classification
tsn_acer <- search_taxonomy("Acer")$taxonomy.tsn
#> Found 5 taxa involved in 5 networks
# }
```
