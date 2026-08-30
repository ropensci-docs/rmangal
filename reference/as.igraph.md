# Coerce `mgNetworksCollection` or `mgNetwork` objects to `igraph` objects.

Coerce `mgNetworksCollection` or `mgNetwork` objects to `igraph`
objects.

## Usage

``` r
# S3 method for class 'mgNetwork'
as.igraph(x, ...)

# S3 method for class 'mgNetworksCollection'
as.igraph(x, ...)
```

## Arguments

- x:

  either a `mgNetworksCollection` or a `mgNetwork` object.

- ...:

  currently ignored.

## Value

An object of class `igraph` for a `mgNetwork` object and a list of
`igraph` objects for `mgNetworksCollection`.

## Methods (by class)

- `as.igraph(mgNetwork)`: Convert `mgNetwork` objects to `igraph`
  objects.

- `as.igraph(mgNetworksCollection)`: Convert `mgNetworksCollection`
  objects to a list of `igraph` objects.
