# Get count of species in the Red List

Returns a count of the number of unique species which have assessments.

## Usage

``` r
rl_sp_count(key = NULL, ...)

rl_sp_count_(key = NULL, ...)
```

## Arguments

- key:

  (character) An IUCN API token. See
  [`rl_use_iucn()`](https://docs.ropensci.org/rredlist/reference/rl_use_iucn.md).

- ...:

  Curl options passed to
  [HttpClient](https://docs.ropensci.org/crul/reference/HttpClient.html)

## Value

An integer representing the number of unique species represented within
the IUCN database.

## References

API docs at <https://api.iucnredlist.org/>.

## See also

Red List information and statistics:
[`rl_api_version()`](https://docs.ropensci.org/rredlist/reference/rl_api_version.md),
[`rl_citation()`](https://docs.ropensci.org/rredlist/reference/rl_citation.md),
[`rl_version()`](https://docs.ropensci.org/rredlist/reference/rl_version.md)

## Examples

``` r
if (FALSE) { # \dontrun{
# Get count of species with assessments
rl_sp_count()
} # }
```
