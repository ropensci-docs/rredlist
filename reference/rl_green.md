# Green Status assessment summary

List all Green Status assessments.

## Usage

``` r
rl_green(key = NULL, parse = TRUE, ...)

rl_green_(key = NULL, ...)
```

## Arguments

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

Assessments for specific sets of taxa
[`rl_comp_groups()`](https://docs.ropensci.org/rredlist/reference/rl_comp_groups.md),
[`rl_extinct()`](https://docs.ropensci.org/rredlist/reference/rl_extinct.md),
[`rl_extinct_wild()`](https://docs.ropensci.org/rredlist/reference/rl_extinct_wild.md),
[`rl_growth_forms()`](https://docs.ropensci.org/rredlist/reference/rl_growth_forms.md)

## Examples

``` r
if (FALSE) { # \dontrun{
# Get list of Green Status assessments
rl_green()
} # }
```
