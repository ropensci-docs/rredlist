# Get the citation for the Red List API

Full acknowledgement and citation needs to be given for using the API.
Use this function to get the full citation for the current version of
the Red List API. More details are available here:
<https://api.iucnredlist.org/>.

## Usage

``` r
rl_citation(key = NULL, ...)
```

## Arguments

- key:

  (character) An IUCN API token. See
  [`rl_use_iucn()`](https://docs.ropensci.org/rredlist/reference/rl_use_iucn.md).

- ...:

  Curl options passed to
  [HttpClient](https://docs.ropensci.org/crul/reference/HttpClient.html).

## Value

Red List citation as a [bibentry](https://rdrr.io/r/utils/bibentry.html)
object.

## See also

Red List information and statistics:
[`rl_api_version()`](https://docs.ropensci.org/rredlist/reference/rl_api_version.md),
[`rl_sp_count()`](https://docs.ropensci.org/rredlist/reference/rl_sp_count.md),
[`rl_version()`](https://docs.ropensci.org/rredlist/reference/rl_version.md)

## Examples

``` r
if (FALSE) { # \dontrun{
rl_citation()
} # }
```
