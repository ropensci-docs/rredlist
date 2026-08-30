# Get the Red List version

Returns the current version number of the IUCN Red List of Threatened
Species

## Usage

``` r
rl_version(key = NULL, ...)
```

## Arguments

- key:

  (character) An IUCN API token. See
  [`rl_use_iucn()`](https://docs.ropensci.org/rredlist/reference/rl_use_iucn.md).

- ...:

  Curl options passed to
  [HttpClient](https://docs.ropensci.org/crul/reference/HttpClient.html).

## Value

Red List version as character string.

## See also

Red List information and statistics:
[`rl_api_version()`](https://docs.ropensci.org/rredlist/reference/rl_api_version.md),
[`rl_citation()`](https://docs.ropensci.org/rredlist/reference/rl_citation.md),
[`rl_sp_count()`](https://docs.ropensci.org/rredlist/reference/rl_sp_count.md)

## Examples

``` r
if (FALSE) { # \dontrun{
rl_version()
} # }
```
