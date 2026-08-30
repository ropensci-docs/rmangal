# Combine Mangal networks

Combine `mgNetworksCollection` and `mgNetwork` objects into a
`mgNetworksCollection` object.

## Usage

``` r
combine_mgNetworks(...)
```

## Arguments

- ...:

  objects of class `mgNetworksCollection` or `mgNetwork` or a list of
  objects of these classes.

## Value

An object of class `mgNetworksCollection`.

## Examples

``` r
# \donttest{
mg_random_1071 <- get_collection(c(1071))
mg_random_1074 <- get_collection(c(1074))
combine_mgNetworks(mg_random_1071, mg_random_1074)
#> 
#> ── Network Collection ──
#> 
#> 2 networks in collection
#> 
#> ── Network #1071 
#> • Dataset: #75
#> • Description: structure of local anemonefish-anemone networks across the
#> Manado region of Sulawesi, Indonesia, Bajo
#> • Size: 4 edges, 6 nodes
#> • Taxonomic IDs coverage for nodes:
#> ITIS: 100%, BOLD: 83%, EOL: 100%, COL: 100%, GBIF: 100%, NCBI: 100%
#> • Published in reference # DOI: 10.1007/s10641-010-9606-0
#> 
#> ── Network #1074 
#> • Dataset: #75
#> • Description: structure of local anemonefish-anemone networks across the
#> Manado region of Sulawesi, Indonesia, Fukui
#> • Size: 6 edges, 7 nodes
#> • Taxonomic IDs coverage for nodes:
#> ITIS: 100%, BOLD: 86%, EOL: 100%, COL: 100%, GBIF: 100%, NCBI: 100%
#> • Published in reference # DOI: 10.1007/s10641-010-9606-0
# }
```
