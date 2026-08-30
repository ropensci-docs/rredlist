# Retrieve a list of assessments

Get the full details for a list of IUCN Red List assessments. This is a
wrapper for
[`rl_assessment()`](https://docs.ropensci.org/rredlist/reference/rl_assessment.md)
that allows you to retrieve multiple assessments at once.

## Usage

``` r
rl_assessment_list(ids, key = NULL, wait_time = 0.5, quiet = FALSE, ...)
```

## Arguments

- ids:

  (integer) A vector of unique identifiers of the assessments.

- key:

  (character) An IUCN API token. See
  [`rl_use_iucn()`](https://docs.ropensci.org/rredlist/reference/rl_use_iucn.md).

- wait_time:

  (numeric) The number of seconds to wait between queries. The default
  is 0.5 seconds, which is recommended by IUCN to avoid timeouts.

- quiet:

  (logical) If `TRUE`, suppresses the progress bar.

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

A list with each element representing the response of
[`rl_assessment()`](https://docs.ropensci.org/rredlist/reference/rl_assessment.md).

## Examples

``` r
if (FALSE) { # \dontrun{
# Get assessment details for multiple assessments
ex1 <- rl_assessment_list(ids = c(166290968, 136250858))
} # }
```
