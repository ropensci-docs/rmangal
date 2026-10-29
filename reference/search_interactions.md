# Query interactions

Search for specific interactions using a keyword or a specific type of
interactions (e.g. mutualism). If the `query` is a character string,
then all character columns in the table are searched and the entries for
which at least one partial match was found are returned. Alternatively,
a named list can be used to look for an exact match in a specific column
(see Details).

## Usage

``` r
search_interactions(query, type = NULL, expand_node = FALSE, ...)
```

## Arguments

- query:

  either a character string including a single keyword or a named list
  containing a custom query (see details section below). Note that if an
  empty character string is passed, then all available entries are
  returned.

- type:

  a `character` one of the interactions type available (see details).
  Note that `query` is ignored if `type` is used.

- expand_node:

  a logical. Should the function returned extra information pertaining
  to nodes? Default is set to `FALSE`, which means that only the Mangal
  IDs of nodes are returned.

- ...:

  Additional arguments passed to
  [`rmangal_request()`](https://docs.ropensci.org/rmangal/reference/rmangal_request.md),
  including the argument `cache` that allows requests caching.

## Value

An object of class `mgSearchInteractions`, i.e. a `data.frame` object
including interactions. All networks in which interactions are involved
are also attached to the `data.frame`.

## Details

Names of the list should match one of the column names within the table.
For the `interaction` table, those are:

- `id`: unique identifier of the interaction;

- `attr_id`: identifier of a specific attribute;

- `direction`: edge direction ("directed", "undirected" or "unknown");

- `network_id`: Mangal network identifier;

- `node_from`: node id which the interaction originates;

- `node_to`: node to which the interaction goes;

- `type`: use argument `type` instead.

Note that for lists with more than one element, only the first element
is used, the others are ignored. The type of interactions (argument
`type`) currently available are the following

- "competition";

- "amensalism";

- "neutralism";

- "commensalism";

- "mutualism";

- "parasitism";

- "predation";

- "herbivory";

- "symbiosis";

- "scavenger";

- "detritivore".

## References

- <https://mangal.io/#/>

- <https://mangal-interactions.github.io/mangal-api/#taxonomy>

## Examples

``` r
# \donttest{
df_inter <- search_interactions(type = "competition")
#> `type` used, `query` ignored.
#> Found 12 interactions
# Get all networks containing competition
competition_networks <- get_collection(df_inter)
df_net_926 <- search_interactions(list(network_id = 926))
#> Found 34 interactions
# }
```
