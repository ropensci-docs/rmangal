# Retrieve network information, nodes, edges and references for a given set of Mangal network IDs

Summarize mgNetwork properties.

Summarize mgNetworksCollection properties.

## Usage

``` r
get_network_by_id(ids, as_sf = FALSE, force_collection = FALSE)

get_network_by_id_indiv(id, as_sf = FALSE)

# S3 method for class 'mgNetwork'
print(x, ...)

# S3 method for class 'mgNetworksCollection'
print(x, n = 6, ...)

# S3 method for class 'mgNetwork'
summary(object, ...)

# S3 method for class 'mgNetworksCollection'
summary(object, ...)
```

## Arguments

- ids:

  a vector of Mangal identifier for networks (`integer`).

- as_sf:

  a logical. Should networks metadata be converted into an sf object?
  Note that to use this feature `sf` must be installed.

- force_collection:

  a logical. Should the output to be of class `mgNetworksCollection`
  even if it includes only one network.

- id:

  a single network identifier (`integer`).

- x:

  an object of class `mgNetwork` or `mgNetworksCollection`.

- ...:

  ignored.

- n:

  maximum number of networks to display.

- object:

  object of class `mgNetwork` or `mgNetworksCollection`.

## Value

A `mgNetwork` object includes five data frames:

- network: includes all generic information on the network (if
  `as_sf=TRUE` then it is an object of class `sf`);

- nodes: information pertaining to nodes (includes taxonomic
  information);

- interactions: includes ecological interactions and their attributes;

- dataset: information pertaining to the original dataset;

- reference: details about the original publication.

A summary method is available for objects of class `mgNetwork` object
and returns the following network properties:

- the number of nodes;

- the number of edges;

- the connectance;

- the linkage density;

- the degree (in, out an total) and the eigenvector centrality of every
  nodes.

## Functions

- `get_network_by_id_indiv()`: Retrieve an individual network by its
  identifier.

## Examples

``` r
# \donttest{
net18 <- get_network_by_id(id = 18)
net18_c <- get_network_by_id(id = 18, force_collection = TRUE)
nets <- get_network_by_id(id = c(18, 23))
# }
```
