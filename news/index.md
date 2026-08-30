# Changelog

## rredlist (development version)

## rredlist 1.1.1

CRAN release: 2025-09-04

#### MINOR IMPROVEMENTS

- Users can now specify multiple elements to extract with
  [`rl_assessment_extract()`](https://docs.ropensci.org/rredlist/reference/rl_assessment_extract.md)
  ([\#77](https://github.com/ropensci/rredlist/issues/77))

#### BUG FIXES

- Fixed a bug when trying to extract assessment components containing
  NULL values
- Fixed the vignettes directory to properly include rendered figures

## rredlist 1.1.0

CRAN release: 2025-07-27

#### NEW FEATURES

- Added
  [`rl_assessment_list()`](https://docs.ropensci.org/rredlist/reference/rl_assessment_list.md)
  which is a wrapper for
  [`rl_assessment()`](https://docs.ropensci.org/rredlist/reference/rl_assessment.md)
  that allows you to retrieve multiple assessments at once
  ([\#71](https://github.com/ropensci/rredlist/issues/71)).
- Added
  [`rl_assessment_extract()`](https://docs.ropensci.org/rredlist/reference/rl_assessment_extract.md)
  which can be used to extract a given element from each of a list of
  assessments, such as the output of
  [`rl_assessment_list()`](https://docs.ropensci.org/rredlist/reference/rl_assessment_list.md)
  ([\#71](https://github.com/ropensci/rredlist/issues/71)).

#### MINOR IMPROVEMENTS

- Added a `scope` argument to
  [`rl_sis_latest()`](https://docs.ropensci.org/rredlist/reference/rl_sis_latest.md)
  and
  [`rl_species_latest()`](https://docs.ropensci.org/rredlist/reference/rl_species_latest.md)
  to filter the results to a specific scope. The default scope is “1”
  (i.e., global).

#### BUG FIXES

- Fixed
  [`rl_sis_latest()`](https://docs.ropensci.org/rredlist/reference/rl_sis_latest.md)
  and
  [`rl_species_latest()`](https://docs.ropensci.org/rredlist/reference/rl_species_latest.md)
  so that, in the event that no assessment has been officially
  identified as the latest assessment, they will return the most
  recently published assessment (based on the year that the assessment
  was published) ([@jeffreyhanson](https://github.com/jeffreyhanson),
  [\#69](https://github.com/ropensci/rredlist/issues/69)).

## rredlist 1.0.0

CRAN release: 2025-01-31

This new major version of `rredlist` tracks the development of the IUCN
Red List API. **The API has been upgraded to v4 and this R package has
been updated accordingly.** Note that nearly all functionality of the
package has changed:

- Most functionality now revolves around retrieving individual or lists
  of assessments rather than species
- Functions have been added, removed, and renamed accordingly; all
  existing endpoints of the new API are covered
- The structure of the returned data for most functions has changed,
  reflecting the change in the structure of the API

**Users will need to generate a new API key to use the new version of
the API (see
[`rl_use_iucn()`](https://docs.ropensci.org/rredlist/reference/rl_use_iucn.md)).**

**This package no longer supports v3 of the IUCN Red List API.** Older
versions of the package may be installed if the old version of the API
is needed.

#### Other major changes and additions

- Switched from performing a single GET call to retrying the GET call if
  it is rejected or takes too long
- Several old functions that are no longer supported by the new API have
  been deprecated and may be removed in a future release of rredlist
- Improved the user friendliness of rl_use_iucn()
- Improved type checking of arguments for all functions
- Added a progress bar for multi-page queries
- Improved error status code handling and reduced overall query download
  overhead
- rl_citation() now returns a bibentry and prints a BibTeX entry
- Added IUCN color palette scales for ggplot2
- Added a new vignette demonstrating the use of rredlist within various
  research pipelines
- Added a new vignette demonstrating benchmarking of rredlist

## rredlist 0.7.1

CRAN release: 2022-11-11

William Gearty is now the maintainer of rredlist

## rredlist 0.7.0

CRAN release: 2020-10-29

#### MINOR IMPROVEMENTS

- vignette added, but only available on the docs site
  ([\#24](https://github.com/ropensci/rredlist/issues/24))
- when testing, if a iucn redlist key not found, set a dummy key
  ([\#41](https://github.com/ropensci/rredlist/issues/41))
- readme improvements
  ([\#42](https://github.com/ropensci/rredlist/issues/42))
- change base url for Red List API to https from http

## rredlist 0.6.0

CRAN release: 2020-01-28

#### MINOR IMPROVEMENTS

- note in docs about how result may differ in website vs. in this
  package through the API
  ([\#35](https://github.com/ropensci/rredlist/issues/35))
- fail with useful message when NA’s passed to parameters in package
  functions ([\#38](https://github.com/ropensci/rredlist/issues/38))

## rredlist 0.5.0

CRAN release: 2018-07-19

#### NEW FEATURES

- gains new function `rl_use_iucn` to help with API key setup
  ([\#31](https://github.com/ropensci/rredlist/issues/31)) by
  [@maelle](https://github.com/maelle)
- gains new functions `rl_comp_groups` and `rl_comp_groups_` to
  interface with the comprehensive groups API route
  ([\#26](https://github.com/ropensci/rredlist/issues/26))
- `rl_sp` gains two new parameters: `all` (logical) to toggle getting
  all results or not, if selected we do paging internally; `quiet`
  parameter (logical) suppresses progress
  ([\#29](https://github.com/ropensci/rredlist/issues/29))

#### MINOR IMPROVEMENTS

- mention `redlistr` package in README to help users decide which
  package to use for which use cases
  ([\#30](https://github.com/ropensci/rredlist/issues/30))
- now using `webmockr` and `vcr` to do unit test caching
  ([\#33](https://github.com/ropensci/rredlist/issues/33))
  ([\#34](https://github.com/ropensci/rredlist/issues/34))

## rredlist 0.4.0

CRAN release: 2017-08-26

#### NEW FEATURES

- Gains new functions
  [`rl_growth_forms()`](https://docs.ropensci.org/rredlist/reference/rl_growth_forms.md)
  and
  [`rl_growth_forms_()`](https://docs.ropensci.org/rredlist/reference/rl_growth_forms.md).
  added tests for them as well
  ([\#20](https://github.com/ropensci/rredlist/issues/20)) thanks
  [@stevenpbachman](https://github.com/stevenpbachman)

#### MINOR IMPROVEMENTS

- Now using markdown documentation
  ([\#22](https://github.com/ropensci/rredlist/issues/22))
- Fixed many man files which for `region` parameter described requiring
  a taxonomic name - fixed to describe accurately. Also improved docs in
  general ([\#21](https://github.com/ropensci/rredlist/issues/21))
- Added the options for `category` parameter in
  [`rl_sp_category()`](https://docs.ropensci.org/rredlist/reference/rl_sp_category.md)
  function
- Added in docs for `rl_sp_country` how to get acceptable country codes
  to pass to `country` parameter
- Added to package level manual file `?rredlist-package` a note from the
  IUCN Redlist API documentation about that they suggest using taxonomic
  names instead of IDs because IDs can change through time

## rredlist 0.3.0

CRAN release: 2017-01-11

#### NEW FEATURES

- New functions `rl_occ_country` and `rl_occ_country_` for getting
  country occurrences by species name or ID
  ([\#13](https://github.com/ropensci/rredlist/issues/13))
- Replaced `httr` with `crul`. Please note this only affects use of curl
  options. See `crul` docs for how to use curl options
  ([\#14](https://github.com/ropensci/rredlist/issues/14))

#### MINOR IMPROVEMENTS

- User agent string like
  `r-curl/2.3 crul/0.2.0 rOpenSci(rredlist/0.3.0)` sent in all requests
  now to help IUCN API maintainers know how often requests come from R
  and this package
  ([\#19](https://github.com/ropensci/rredlist/issues/19))
- Taxon names are now given back in `rl_threats` - we didn’t do anything
  in the package - the API now gives the names back and adds them in a
  column ([\#10](https://github.com/ropensci/rredlist/issues/10))
- Type checking all parameter inputs now both in terms of class and
  length - with helpful error messages on fail
  ([\#17](https://github.com/ropensci/rredlist/issues/17))
- Simplify package codebase by having single internal function for a
  suite of half a dozen or so functions that have similar pattern
  ([\#18](https://github.com/ropensci/rredlist/issues/18))
- Removed `key` parameter from
  [`rl_version()`](https://docs.ropensci.org/rredlist/reference/rl_version.md)
  and
  [`rl_citation()`](https://docs.ropensci.org/rredlist/reference/rl_citation.md)
  as API key not required for those methods
- More thorough test suite

## rredlist 0.2.0

CRAN release: 2016-10-15

#### NEW FEATURES

- New methods added to get historical assessments:
  [`rl_history()`](https://docs.ropensci.org/rredlist/reference/rl_history.md)
  and
  [`rl_history_()`](https://docs.ropensci.org/rredlist/reference/rl_history.md)
  ([\#8](https://github.com/ropensci/rredlist/issues/8))

#### MINOR IMPROVEMENTS

- Fixed description of what `rl_common_names` does. In addition,
  clarified description of what other functions do as well, whenever it
  was unclear ([\#12](https://github.com/ropensci/rredlist/issues/12))

#### BUG FIXES

- Some API tokens were being blocked, fixed now
  ([\#7](https://github.com/ropensci/rredlist/issues/7))
- On some operating systems (at least some versions of Windows), queries
  that included taxonomic names weren’t being processed correctly. It is
  fixed now ([\#11](https://github.com/ropensci/rredlist/issues/11))

## rredlist 0.1.0

CRAN release: 2016-01-26

#### NEW FEATURES

- Released to CRAN.
