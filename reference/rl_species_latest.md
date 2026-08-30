# Species latest assessment

Get the latest assessment for a particular species (i.e., Latin
binomial) or subspecies/variety/subpopulation (i.e., Latin trinomial).
Wraps
[`rl_species()`](https://docs.ropensci.org/rredlist/reference/rl_species.md)
and
[`rl_assessment()`](https://docs.ropensci.org/rredlist/reference/rl_assessment.md).

## Usage

``` r
rl_species_latest(
  genus,
  species,
  infra = NULL,
  subpopulation = NULL,
  scope = "1",
  key = NULL,
  parse = TRUE,
  ...
)
```

## Arguments

- genus:

  (character) The genus name of the species to look up.

- species:

  (character) The species epithet of the species to look up.

- infra:

  (character) An optional name of the subspecies or variety to look up.

- subpopulation:

  (character) An optional name of the geographically separate
  subpopulation to look up.

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

## Details

Geographically separate subpopulations of a species are defined as those
populations that are so isolated from others of the same species that it
is considered extremely unlikely that there is any genetic interchange.
In general, listings of such subpopulations are restricted to those that
have been isolated for a long period of time.

Assessments of subspecies, varieties, and geographically separate
subpopulations must adhere to the same standards as for species
assessments. However, these assessments are only included provided there
is a global assessment of the species as a whole.

Infraspecific ranks such as formas, subvarieties, cultivars, etc are not
included in the Red List.

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
[`rl_sis_latest()`](https://docs.ropensci.org/rredlist/reference/rl_sis_latest.md),
[`rl_species()`](https://docs.ropensci.org/rredlist/reference/rl_species.md)

## Examples

``` r
if (FALSE) { # \dontrun{
# Get latest assessment for species
ex1 <- rl_species_latest(genus = "Fratercula", species = "arctica")
ex1$stresses

# Get latest assessment for subspecies
ex2 <- rl_species_latest(genus = "Gorilla", species = "gorilla",
                         infra = "gorilla")
ex2$stresses
} # }
```
