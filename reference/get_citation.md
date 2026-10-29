# Retrieve all references pertaining to the networks collection or individual network

Retrieve all references pertaining to the networks collection or
individual network

## Usage

``` r
get_citation(x)

# S3 method for class 'mgNetwork'
get_citation(x)

# S3 method for class 'mgNetworksCollection'
get_citation(x)
```

## Arguments

- x:

  an object of class `mgNetworksCollection` or `mgNetworks`.

## Value

Bibtex entries as a character vector.

## Methods (by class)

- `get_citation(mgNetwork)`: Get BibTeX entries for the publication
  associated to the network.

- `get_citation(mgNetworksCollection)`: Get BibTeX entries for the
  publication associated to the networks.

## Examples

``` r
# \donttest{
# network collection
lagoon_net_collection <- get_collection(search_datasets("lagoon"))
#> Found 2 datasets.
get_citation(lagoon_net_collection)
#> [1] "@article{Zetina_Rej_n_2003, doi = {10.1016/s0272-7714(02)00410-9}, url = {https://doi.org/10.1016%2Fs0272-7714%2802%2900410-9}, year = 2003, month = {aug}, publisher = {Elsevier {BV}}, volume = {57}, number = {5-6}, pages = {803--815}, author = {Manuel J. Zetina-Rejón and Francisco Arreguí-Sánchez and Ernesto A. Chávez}, title = {Trophic structure and flows of energy in the Huizache{\textendash}Caimanero lagoon complex on the Pacific coast of Mexico},journal = {Estuarine, Coastal and Shelf Science}}"
#> [2] "@article{Dexter_1947, doi = {10.2307/1948658}, url = {https://doi.org/10.2307%2F1948658}, year = 1947, month = {feb}, publisher = {Wiley}, volume = {17}, number = {3}, pages = {261--294}, author = {Ralph W. Dexter}, title = {The Marine Communities of a Tidal Inlet at Cape Ann, Massachusetts: A Study in Bio-Ecology}, journal = {Ecological Monographs}}"                                                                                                                                                        
# individual network
mg_18 <- get_network_by_id(18)
get_citation(mg_18)
#> [1] "@article{article, author = {Mosquin, Theodore and Martin, J. E. H.}, year = {1967}, pages = {201-205}, title = {Observations on the pollination biology of plants on Melville Island, N.W.T., Canada}, journal = {Canadian Field Naturalist}, volume = {81}}"
# }
```
