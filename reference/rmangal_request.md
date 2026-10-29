# Low-level request function for the Mangal API

These functions send a request to a specified endpoint of the Mangal
API.

## Usage

``` r
rmangal_request(endpoint, query = NULL, limit = 100, cache = FALSE, ...)

rmangal_request_singleton(endpoint, id, cache = FALSE, ...)
```

## Arguments

- endpoint:

  A character string specifying the API endpoint to query. Must be one
  of the endpoints listed in
  [`rmangal_endpoints()`](https://docs.ropensci.org/rmangal/reference/rmangal_endpoints.md).

- query:

  Either a character string for a keyword search, or a named list for
  custom queries. If `NULL`, all records are returned.

- limit:

  An integer specifying the maximum number of results per page. Default
  is 100.

- cache:

  Logical or character. If `TRUE`, results are cached in a temporary
  directory. If a character string, it specifies the cache directory. If
  `FALSE` (default), no caching is used. See
  [`httr2::req_cache()`](https://httr2.r-lib.org/reference/req_cache.html)
  for further details about caching in this context.

- ...:

  Additional arguments (currently ignored).

- id:

  An integer or character specifying the unique identifier of the
  resource to retrieve. Must be a single value.

## Value

An object of class `mgGetResponses` containing the response body and the
raw HTTP response(s).

An object of class `mgGetResponses` containing the response body and the
raw HTTP response.

## Functions

- `rmangal_request()`: Send a request to a specified endpoint of the
  Mangal API and returns all matching results.

- `rmangal_request_singleton()`: Retrieves a single resource by its ID
  from a specified endpoint of the Mangal API.

## Examples

``` r
# \donttest{
# Search for networks with keyword "insect"
result <- rmangal_request("network", query = "insect", limit = 10)

# Custom query for a specific dataset
result <- rmangal_request("network", query = list(dataset_id = 19))
# }
# \donttest{
# Retrieve network with ID 5013
result <- rmangal_request_singleton("network", id = 5013)
# }
```
