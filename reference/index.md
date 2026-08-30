# Package index

## Explore database

Explore the content of each datatables and return `mgSearch*` objects

- [`search_datasets()`](https://docs.ropensci.org/rmangal/reference/search_datasets.md)
  : Query datasets
- [`search_interactions()`](https://docs.ropensci.org/rmangal/reference/search_interactions.md)
  : Query interactions
- [`search_networks()`](https://docs.ropensci.org/rmangal/reference/search_networks.md)
  [`search_networks_sf()`](https://docs.ropensci.org/rmangal/reference/search_networks.md)
  : Query networks
- [`search_nodes()`](https://docs.ropensci.org/rmangal/reference/search_nodes.md)
  : Query nodes
- [`search_references()`](https://docs.ropensci.org/rmangal/reference/search_references.md)
  : Query references
- [`search_taxonomy()`](https://docs.ropensci.org/rmangal/reference/search_taxonomy.md)
  : Query taxonomy
- [`avail_type()`](https://docs.ropensci.org/rmangal/reference/avail_type.md)
  : List interactions type contained in mangal-db

## Retrieve networks

Get networks ( `mgNetwork` or `mgNetworksCollection`) from `search_*`
functions

- [`get_collection()`](https://docs.ropensci.org/rmangal/reference/get_collection.md)
  : Get a collection of networks
- [`get_network_by_id()`](https://docs.ropensci.org/rmangal/reference/get_network_by_id.md)
  [`get_network_by_id_indiv()`](https://docs.ropensci.org/rmangal/reference/get_network_by_id.md)
  [`print(`*`<mgNetwork>`*`)`](https://docs.ropensci.org/rmangal/reference/get_network_by_id.md)
  [`print(`*`<mgNetworksCollection>`*`)`](https://docs.ropensci.org/rmangal/reference/get_network_by_id.md)
  [`summary(`*`<mgNetwork>`*`)`](https://docs.ropensci.org/rmangal/reference/get_network_by_id.md)
  [`summary(`*`<mgNetworksCollection>`*`)`](https://docs.ropensci.org/rmangal/reference/get_network_by_id.md)
  : Retrieve network information, nodes, edges and references for a
  given set of Mangal network IDs
- [`get_citation()`](https://docs.ropensci.org/rmangal/reference/get_citation.md)
  : Retrieve all references pertaining to the networks collection or
  individual network

## Analyze networks

Analyze or manipulate `mgNetwork` or `mgNetworksCollection`

- [`as.igraph(`*`<mgNetwork>`*`)`](https://docs.ropensci.org/rmangal/reference/as.igraph.md)
  [`as.igraph(`*`<mgNetworksCollection>`*`)`](https://docs.ropensci.org/rmangal/reference/as.igraph.md)
  :

  Coerce `mgNetworksCollection` or `mgNetwork` objects to `igraph`
  objects.

- [`combine_mgNetworks()`](https://docs.ropensci.org/rmangal/reference/combine_mgNetworks.md)
  : Combine Mangal networks

## Core functions

Internation functions that handle API calls

- [`rmangal_endpoints`](https://docs.ropensci.org/rmangal/reference/rmangal_endpoints.md)
  : Mangal API's endpoints
- [`rmangal_request()`](https://docs.ropensci.org/rmangal/reference/rmangal_request.md)
  [`rmangal_request_singleton()`](https://docs.ropensci.org/rmangal/reference/rmangal_request.md)
  : Low-level request function for the Mangal API
