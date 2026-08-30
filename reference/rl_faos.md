# FAO marine fishing region assessment summary

Return assessments for a given marine fishing region as defined by the
Food and Agriculture Organization (FAO) of the United Nations (e.g.,
Pacific - northwest, Arctic Sea). More details are available here:
<https://www.fao.org/fishery/en/area>.

## Usage

``` r
rl_faos(
  code = NULL,
  key = NULL,
  parse = TRUE,
  all = TRUE,
  page = 1,
  quiet = FALSE,
  ...
)

rl_faos_(code = NULL, key = NULL, all = TRUE, page = 1, quiet = FALSE, ...)
```

## Arguments

- code:

  (character) The code of the FAO region to look up. If not supplied, a
  list of all FAO regions will be returned.

- key:

  (character) An IUCN API token. See
  [`rl_use_iucn()`](https://docs.ropensci.org/rredlist/reference/rl_use_iucn.md).

- parse:

  (logical) Whether to parse the output to list (`FALSE`) or, where
  possible, data.frame (`TRUE`). Default: `TRUE`.

- all:

  (logical) Whether to retrieve all results at once or not. If `TRUE` we
  do the paging internally for you and bind all of the results together.
  If `FALSE`, only a single page of results will be retrieved.

- page:

  (integer/numeric) Page to get if `all` is `FALSE`. Default: 1. Each
  page returns up to 100 records. Paging is required because it's too
  much burden on a server to just "get all the data" in one request.

- quiet:

  (logical) Whether to suppress progress for multi-page downloads or
  not. Default: `FALSE` (that is, give progress). Ignored if
  `all = FALSE`.

- ...:

  Includes the following filters that are supported by the API endpoint
  (refer to the [API
  docs](https://api.iucnredlist.org/api-docs/index.html) for more
  information):

  - `year_published`: (integer) Set this to return only assessments from
    a given year.

  - `latest`: (logical) Set this to `TRUE` to return only the latest
    assessment for each taxon.

  - `scope_code`: (integer) Set this to return only assessments from a
    particular
    [scope](https://docs.ropensci.org/rredlist/reference/rl_scopes.md)
    (e.g., `1` for Global, `2` for Europe). This is similar to the
    `region` argument of the old Red List API and old versions of
    rredlist.

  Also includes the following arguments related to the wait time between
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

Assessments by geographic regions:
[`rl_countries()`](https://docs.ropensci.org/rredlist/reference/rl_countries.md),
[`rl_realms()`](https://docs.ropensci.org/rredlist/reference/rl_realms.md),
[`rl_scopes()`](https://docs.ropensci.org/rredlist/reference/rl_scopes.md)

## Examples

``` r
if (FALSE) { # \dontrun{
# Get a list of all scopes
rl_faos()
# Get assessment summary for the Arctic Sea FAO region
rl_faos(code = "18")
} # }
```
