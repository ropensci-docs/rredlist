# SIS ID latest assessment

Get the latest assessment for a particular taxonomic entity based on its
ID number from the [IUCN Species Information Service
(SIS)](https://www.iucnredlist.org/assessment/sis). Wraps
[`rl_sis()`](https://docs.ropensci.org/rredlist/reference/rl_sis.md) and
[`rl_assessment()`](https://docs.ropensci.org/rredlist/reference/rl_assessment.md).

## Usage

``` r
rl_sis_latest(id, scope = "1", key = NULL, parse = TRUE, ...)
```

## Arguments

- id:

  (integer) The SIS ID of the taxonomic entity to look up.

- scope:

  (character) An optional scope (see
  [`rl_scopes()`](https://docs.ropensci.org/rredlist/reference/rl_scopes.md))
  to filter the results by. The default, "1", returns the latest global
  assessment. If no assessments exist for the specified `scope`, the
  latest assessment across all scopes is returned. If `NULL`, the latest
  assessment across all scopes is returned.

- key:

  (character) An IUCN API token. See
  [`rl_use_iucn()`](https://docs.ropensci.org/rredlist/reference/rl_use_iucn.md).

- parse:

  (logical) Whether to parse the output to list (`FALSE`) or, where
  possible, data.frame (`TRUE`). Default: `TRUE`.

- ...:

  Includes the following arguments related to the wait time between
  request retries if a "Too Many Requests" error is received from the
  API (see
  [HttpClient()\$retry()](https://docs.ropensci.org/crul/reference/HttpClient.html)
  for more details):

  - `pause_base`, `pause_cap`, and `pause_min`: basis, maximum, and
    minimum for calculating wait time for retry

  - `times`: the maximum number of times to retry

  - `onwait`: a callback function if the request will be retried and a
    wait time is being applied

  Also supports any [curl
  options](https://jeroen.r-universe.dev/curl/reference/curl_options.html)
  passed to the GET request via
  [HttpClient](https://docs.ropensci.org/crul/reference/HttpClient.html).

## Value

A list unless using a function with a trailing underscore, in which case
json as character string is returned.

## References

API docs at <https://api.iucnredlist.org/>.

## See also

Assessments by taxa:
[`rl_class()`](https://docs.ropensci.org/rredlist/reference/rl_class.md),
[`rl_family()`](https://docs.ropensci.org/rredlist/reference/rl_family.md),
[`rl_kingdom()`](https://docs.ropensci.org/rredlist/reference/rl_kingdom.md),
[`rl_order()`](https://docs.ropensci.org/rredlist/reference/rl_order.md),
[`rl_phylum()`](https://docs.ropensci.org/rredlist/reference/rl_phylum.md),
[`rl_sis()`](https://docs.ropensci.org/rredlist/reference/rl_sis.md),
[`rl_species()`](https://docs.ropensci.org/rredlist/reference/rl_species.md),
[`rl_species_latest()`](https://docs.ropensci.org/rredlist/reference/rl_species_latest.md)

## Examples

``` r
if (FALSE) { # \dontrun{
# Get latest assessment for species
ex1 <- rl_sis_latest(id = 9404)
ex1$stresses
} # }
```
